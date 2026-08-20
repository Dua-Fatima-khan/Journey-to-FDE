# The Four Layers: Prompt, Context, Harness, Loop 
*A beginner-friendly, complete guide — this is where the real-world build journey actually starts and it's gonna be lengthy but worth it.*

Source: [The AI Agent Factory] (agentfactory.panaversity.org/docs/four-layers-crash-course)

---

## 0. The story that opens this topic

An agent runs for **forty minutes**, spends **fifty dollars**, and produces nothing usable. You check the log: it tried the same three things over and over, just changing a few words each time.

**What does almost everyone change?** The prompt. It's the first thing people look at, and the only thing editable in ten seconds. So they rewrite it, run it again  and watch it waste another forty minutes doing the same thing.

**The prompt was never the problem.** Nothing in that system was ever built to notice the run had stopped making progress so nothing ever stopped it. The real fix was about eleven words, in a completely different file, on a layer most people can't even name.

This topic gives you those names. There are four: **Prompt, Context, Harness, Loop.**

> They are NOT four skills you choose between, and NOT four steps you climb.
> They are **four containers, each one inside the next**, and each one does a different job.

Once you can see them, "my agent is broken" stops being a mystery and becomes a question with an address: **which layer broke?**

---

## 1. Why these words are confusing everywhere else

This is a very young field, and the vocabulary arrived in the wrong order.

- At first there was only ONE layer anyone could touch: you typed a message, read the reply. "Prompt engineering" meant the whole skill, because the prompt was the whole surface.
- Then tools grew fast. Coding agents added a permissions file, a rules file, hooks... a whole new layer around the model. Then schedules and routines arrived another layer, around that one.
- Nobody agreed on names as this happened. **"Harness" is the most confused word of all** most online writing squashes the harness and the loop into one thing. Some writing uses "harness" for something even bigger: the whole platform (tools + credentials + security).

**Why this actually matters:** a missing permission rule and a missing schedule are two completely different bugs, fixed by different people. One blurry word sends you looking in the wrong place  exactly what happened in the $50 story above.

### Key words — read once, come back when a term feels fuzzy

| Term | Plain-English meaning |
|---|---|
| **Prompt** | The message you send,  the ask, examples, format, role |
| **Context window** | Everything the model can see while writing ONE response. What's not in it is not a fact to the model. |
| **Curator** | Whatever decides what goes into the window, in what order, what gets left out |
| **Beat** | One full turn of an agent: your instruction, then every tool call, until it goes quiet |
| **Harness** | The code around the model that runs one beat |
| **Loop** | The system around the harness that starts beats, judges them, remembers between them |
| **Heartbeat** | Whatever starts a beat, a schedule, an event, a condition |
| **Spine** | State saved outside the model, so the next beat knows what the last one did |
| **Stopping condition** | A testable rule saying the work is finished — chosen and enforced by something OTHER than the maker |
| **Maker-checker** | One agent does the work; a different agent or command checks it |
| **Human gate** | A point where a person decides before the run continues |
| **Sub-agent** | A helper with its own window, doing one job, handing back a summary |
| **Graph** | Many of these stacks wired together — what runs next, what moves along each edge, who checks whom |

---

## 2. The picture: four containers, one inside the next

Imagine four nested boxes:

```
┌───────────────────────────────── LOOP (unit: the whole run) ───────────────────────────────────┐
│  starts beats · judges them · remembers between them                                           │
│  ┌───────────────────────────── HARNESS (unit: one beat) ──────────────────────────────────┐   │
│  │  runs tools · handles errors · enforces proof before ending                             │   │
│  │  ┌───────────────────── CONTEXT (unit: the window) ─────────────────────┐               │   │
│  │  │  query, docs, memory, prior turns, tool results → curator → window   │               │   │
│  │  │      ┌──────────── PROMPT (unit: one model call) ─────────────┐      │               │   │
│  │  │      │  the message you actually send to the model            │      │               │   │
│  │  │      └────────────────────────────────────────────────────────┘      │               │   │
│  │  └──────────────────────────────────────────────────────────────────────┘               │   │
│  │       (also inside harness: the model call, tools, sub-agents)                          │   │
│  └─────────────────────────────────────────────────────────────────────────────────────────┘   │
│       outside stops attached to the loop: success condition · limit · no-progress · checker    │
│       heartbeat starts each beat · spine carries memory between beats                          │
│       human gate & external checker attach to the EDGE of the loop, not inside the harness     │
└────────────────────────────────────────────────────────────────────────────────────────────────┘
```

**The one sentence this whole topic exists to teach — it repeats three more times below, memorize it:**

> **A good prompt fails inside bad context. Good context fails inside a bare harness. A good harness sits idle without a loop.**

Nothing on an inner layer can rescue a missing outer layer. Nothing on an outer layer can rescue a broken inner one.

### Try this yourself (90 seconds) — proves the whole point

1. Open any agent you already use. Give it a small real task with a checkable result (a script, a spreadsheet total, a link).
2. Say: *"Fix this so it works, then tell me when you're done."*
3. **Before trusting the answer, go check it yourself.**

Very often you'll find a confident "done, all fixed!" attached to work that was never actually verified. Not because the model lied — because **nothing in that setup was required to check, and nothing except the model itself decided what "done" meant.** Keep this feeling in mind — Concept 6 explains exactly why it happens.

---

## 3. Part 1 — The Shape

### Concept 1: Containers, not steps

The common (WRONG) picture: that it is a ladder from beginner to expert — prompt for beginners, loop for experts, and you "graduate" upward, thi concept is wrong because it works as a container one layer wrapping another.

**Why it's wrong, and costly:** every beat, even in a loop that's run unsupervised for 6 months, still sends a message to a model. If that message is vague, the loop now produces vague work *faster, on a timer.* You never leave the inner layers behind — you wrap them.

Three wrong beliefs to drop right now:
- **Outer ≠ later.** You don't build these in order. Most of the time you *rent* three of them and own one (see Concept 10).
- **Outer ≠ more important.** A careless prompt inside a beautifully built loop produces bad work on a schedule, with a receipt.
- **These are not four sizes of one thing.** They are four genuinely different objects — Concept 2 tells them apart.

### Concept 2: The unit-of-work test

| Layer | Unit of work | In plain words |
|---|---|---|
| **Prompt** | One model call | What you typed and hit enter on |
| **Context** | The window | Everything the model can see for that one answer: message, files, earlier turns, rules file, tool results |
| **Harness** | One beat | Instruction → tool call → read result → think → another tool call → ... until it goes quiet. All of that is one beat. |
| **Loop** | The whole run | What happens when nobody is typing — what starts a beat, judges it, remembers between beats |

> **The question that survives when vocabulary changes:** whenever someone says "harness" or "context engineering" or "the agent loop," don't argue the word — ask them: **"What unit of work are you talking about? One model call, the window, one beat, or the whole run?"** Then you can translate instead of getting confused.

---

## 4. Part 2 — The Four Layers, One at a Time

### Concept 3: Prompt — unit is one model call

The message you compose: who the model should be, what you want, what good work looks like, examples, and the shape of the answer.

**The craft:** find the ONE weakest ingredient and fix only that. 

Wrong shape → give an example of the right shape. 
<br/>
Wrong tone → name the audience. 
<br/>Rewriting everything at once tells you nothing about what was actually broken.

**Why people over-invest here:** it's the only layer editable in 10 seconds, and the only one that needs no code. Both good things — until something breaks in production, and people reach for what's *easy* to change instead of what actually broke.

**Signature of a broken prompt:** the model clearly understood the task and did roughly the right work — but wrong shape, wrong length, wrong voice, or missing an "obvious" section. Nothing is factually wrong. Just not what you asked for.

### Concept 4: Context — unit is the window

The window is everything the model can see while writing one response.

- A file you didn't attach isn't a fact to the model.
- BUT the model isn't empty when the window is thin — it still carries its training knowledge, and that fills the gap. <br/> **A model missing your document doesn't go blank, it reaches for the most likely thing it already knows, and says that, with the same confidence it would use for the truth.** This is the root of a very common failure.

There's always more material than fits. Something has to choose, that's the **curator**, whether or not you wrote one on purpose.

**Three jobs land on the curator:**
1. **Order** — position changes strength. Important material buried in paragraph nine is a real decision you made, even if you didn't realize it ("lost in the middle" effect).
2. **Compression** — not free. Summarizing 40 pages into 4 means picking what to keep; a dropped exception is gone from the run.
3. **Dropping** — a policy. If you don't set it, your harness sets it for you, at the worst moment, by a rule you never read.

> **The curator test:** point at any document in the window and ask **which rule put it there.** If the honest answer is "the retriever returned it" — you have a search box, not a curator.

**Signature of broken context:** the answer is fluent, confident, and factually wrong — often correct about *something else* (an older file version, a different customer). Confident + wrong + close to something true = the signature.

**Try this (2 min):** ask the same question about a document twice, in two fresh chats — once with the full doc pasted, once with only the first third. The second chat will often still answer confidently, using training knowledge to fill the hole. Same prompt, different answer.

### Concept 5: Harness — unit is one beat

One instruction → the agent reads files, runs a command, reads the error, edits, runs again, then goes quiet. That whole stretch is **one beat**. The harness is the code that runs it.

**Job list:** assemble context, call the model, run whatever tools it asks for, feed results back, handle errors, enforce what the beat must prove before ending, repeat until the model stops asking.

You already use one: Claude Code, OpenCode, Cowork — every permission prompt, every rules file, every automatic pre-commit check is harness.

**Sub-agents — the surprising part.** A sub-agent is *called* like a tool, but it behaves like something much bigger. A tool call returns a plain result. A sub-agent opens **its own window** and runs **its own beat** — a full nested copy of the whole stack.

- **The upside:** 40 documents can be read by a sub-agent and never touch your window — you get back 3 paragraphs instead of 40 pages.
- **The hidden cost:** what comes back is a summary, written with **full confidence, including whatever it got wrong.** You never saw the 40 documents. Neither will anything downstream. How confident it sounds tells you nothing about how well it read.

### Concept 6: The limit that defines the harness ⭐ (the turning point of the whole topic)

A beat can end for many reasons: timeout, token ceiling, error, permission denied, or the model just decides it's done. **None of those proves the work succeeded** — only that the beat ended.

A good harness CAN enforce real checks inside a beat (run a test suite, validate a schema, compare a total) — build these wherever you can. But:

> **A beat can prove that a specific check passed. It cannot decide that passing that check was enough.**

A passing test proves the test passed — not that the test covered what mattered. Somebody must decide what "finished" means BEFORE the run begins.

**Example:** a bank-reconciliation agent proposes 40 matches and reports "statement balances" — but never actually compared the two totals. Every internal signal looks healthy. The claim is still false.

Writing "verify your work" in the prompt does NOT fix this — the model can write "verified" as easily as it writes "done." **The final definition of success must come from outside the work being judged.** That's why it belongs to the next layer out — the Loop.

### Concept 7: Loop — unit is the whole run

The loop supplies what one beat cannot give itself.

- **A heartbeat** starts each beat — a schedule, event, or condition. Without one, YOU are the heartbeat; Your prompt when you stop sending prompts, the work stops.
- **A spine** stores state outside the model, so the next beat knows what the last one did. Example — a simple status file:
  ```
  run: nightly reconciliation, 2026-03-14
  done: pulled 412 payments and 388 open invoices
  in progress: matching pass 3 of 5, 341 matched so far
  needs a person: invoice 4471, two candidates both at 0.52
  budget: 3 beats used of 12
  ```
  Nothing clever here — that's why it works. The next beat resumes from pass 3 instead of restarting.

- **Outside stops** decide if the whole run continues:
  - A **success condition** chosen in advance, proved by a command
  - **Limits** on beats, spending, elapsed time
  - A **no-progress check** — notices repeated attempts with no real change
  - A **separate checker** — the thing that judges the work did not make the work

None of these ask the maker if it's finished. **That's the maker-checker rule in one sentence.**

*(Back to the opening story: the missing part was a no-progress check — not a better prompt. A better prompt changes the words of each failed attempt; it can't make the run notice it's stuck.)*

### Concept 8: The human gate — an exit, not a stop

The stops (Concept 7) are how a run **fails safely.** The gate is how a run **succeeds with help.**

**Key idea: ambiguity is not an error.** Invoice #4471 matches two payments, both scoring 0.52 — that's not a bug, that's what the data actually looks like.

Without a gate, the agent has two bad options:
- **Fail** → throws away 9 passes of legitimate work
- **Guess** → picks one and moves on

**Guessing is the dangerous one.** A crash is loud, you can fix it. A guess is silent — it looks exactly like a correct answer: same format, same confidence, same spot in the report. **Nobody downstream can tell the difference.**

A gate is written **in advance**, triggered by: confidence below a set line, a value above a set limit, or any hard-to-undo action. When it fires, a named person decides (e.g., Ayesha in accounts payable sees both candidates, picks the right one in 20 seconds because she remembers the customer paying twice in March). **Her answer re-enters as new evidence — the run continues from where it paused.**

---

## 5. Part 3 — Using the Map

### Concept 9: Which layer broke? (keep this table visible during debugging)

| What you see | Look here first | What to change |
|---|---|---|
| Output shape/tone wrong, but it understood the task | **Prompt** | Weakest ingredient: examples, instructions, output shape |
| Confident, fluent, and factually wrong | **Context** | The curator: what got in, in what order, what got dropped |
| Reports success it never demonstrated / a failed tool call passes unnoticed | **Harness** | Tools, error handling, what the beat must prove |
| Wrong answers reach a person/system unchecked | **Loop** | The checker, who chose its criteria |
| Never stops, stops too early, or guessed when it should've asked | **Loop** | The stops and the gate |

⚠️ **Two honest notes:**
- This is a **search order**, not a verdict. Failures often cross boundaries — read each row as "look here first."
- **The habit this table exists to break:** most teams debug at the WRONG layer, not from stupidity — the prompt is just the easiest thing to edit under pressure. **Naming the layer out loud, before touching anything, is the whole discipline.** Costs 5 seconds. Saves hours.

### Concept 10: Which layers do you actually own?

You don't build all four every time — often you **rent three and own one.**

| Layer | Mode 1: using a general agent | Mode 2: manufacturing your own worker |
|---|---|---|
| **Prompt** | Mostly yours | Yours, written once, reused |
| **Context** | Partly yours (what you attach/clear) | Yours — you write the curator |
| **Harness** | Rented, partly configurable | Yours |
| **Loop** | Mostly rented | Yours — every stop is something you wrote |

⚠️ **The mistake this table prevents:** reading this in Mode 1 and thinking *"I already do all four, because my tool does all four."* **Your tool does it for ITS OWN work.** The worker you're about to build has no tool doing it for yours. That gap is exactly where a demo turns into a production incident.

**Find out what you rented (4 min) — write your guesses first, THEN check:**
1. When the window fills, what does your harness remove — and does it tell you?
2. When a tool call fails, does it retry, how many times, do you see it?
3. When a run hits its limit mid-task, what happens to the work already done?

---

## 6. Concept 11: Where graphs fit (a graph is NOT a fifth layer)

The four layers describe **one execution path**: one message, one window, one beat, one run.
A **graph** describes a **topology**: what runs next, what moves along each edge, who checks whom.
<br/> The four layers are like node, and a graph is a Topology that shows the connection between your nodes.

> **The four layers describe what happens INSIDE one node. A graph describes what happens BETWEEN nodes.**

A node doesn't have to be an agent it can be a function, a rule, a tool call, a human gate, a measurement, one beat, a whole loop, or a full agent.

**Real example — a 6-node accounts-payable pipeline, only ONE node is an agent:**

| Node | What it is | Type |
|---|---|---|
| Pull | reads payments + invoices into one format | function |
| Route | flags invoices above a value threshold | rule |
| **Match** | proposes matches + confidence scores | **full agent (all 4 layers live here)** |
| Gate | Ayesha decides ambiguous/high-value cases | person |
| Prove | compares matched total vs. statement total | measurement |
| Post | writes accepted matches, sends the rest to review | function |

The **Prove** node sits *outside* Match, can't be skipped by Match, and gets only the values it needs — **the node that made the matches cannot overrule the measurement that judges them.**

⚠️ Token cost mostly lives inside the agentic node(s) — a 6-node graph can cost LESS than a single always-agentic workflow, because 5 of 6 nodes cost almost nothing. Counting boxes tells you nothing about cost; count how often the agentic nodes actually run.

---

## 7. Concept 12: When the framework fights you (read this so you don't over-apply it)

- **Some failures are genuinely two-layer.** A dropping policy discarding old turns is a context decision — but it only causes trouble because the loop lets runs go long enough to fill the window. Both, honestly.
- **Some diagnoses point one place, fixes belong another.** "Reported success it never demonstrated" diagnoses as Harness (a fact about what a beat can know about itself) — but the FIX is usually Loop (an outside success condition). The framework did its job by sending you elsewhere.
- **Some failures are none of the four.** Sometimes the model just can't do the task at the needed quality — no arrangement of containers creates a missing capability. If you've genuinely cleared all four and it's still bad: a stronger model, a smaller task, or a different approach.
- **Not every project needs all four.** A one-time task doesn't need a loop — building one anyway is its own kind of waste.

---

## 8. The Drill — Name the Layer (test yourself before checking answers!)

Try to answer each BEFORE reading the answer below it.

**1.** You asked for a 5-column table. You got 3 excellent, accurate paragraphs instead.
→ **Prompt.** Right work, wrong container. Give an example of the table shape you want.

**2.** Agent confidently says your pricing tier caps at 5,000 requests. Your page says 50,000. It read the page.
→ **Context.** Confident + wrong + close-to-true = the signature. Run the curator test — which rule put that page in, and all of it?

**3.** Overnight run reports "all tests passing." Morning: tests never ran, build is red.
→ **Harness for diagnosis, Loop for the real fix.** Give the beat a hook that actually runs the suite AND refuses to finish without it — but the trustworthy fix is an outside stop, chosen in advance, enforced by something other than the maker.

**4.** A run burns the whole budget in an afternoon; log shows the same 3 approaches repeated with slightly different wording.
→ **Loop.** No no-progress check (and probably no spending limit). This is the opening story.

**5.** 300 invoices processed, "300 matched" reported. A hand-check finds a few silent guesses on ambiguous cases.
→ **Loop — specifically the missing gate.** Nothing malfunctioned; it met genuine ambiguity with no gate, so it guessed. Write triggers in advance and route to a person.

**6.** A sub-agent summarizes 40 tickets cleanly — 2 claims in the summary are wrong.
→ **Harness.** Sub-agents carry full confidence regardless of read quality. Require quotes/IDs/receipts you can check, not conclusions to trust blindly.

**7.** 20 turns in, the agent contradicts a decision you both agreed on early — as if it never happened.
→ **Context.** The window filled, the dropping policy removed the wrong thing. Make key decisions durable OUTSIDE chat history (a rules file, a spec).

**8.** All four layers verified clean on a hard research task. Output is still mediocre.
→ **None of them.** The layers show where things CAN break — they don't create capability. Try a stronger model, a smaller/sharper task, or accept a person is needed here.

### Diagnose your own failure — 3 questions

1. What unit of work went wrong — one model call, the window, one beat, or the whole run?
2. What did you actually change afterward — was it the SAME layer?
3. What would have caught it? Name the mechanism, the layer, who should have chosen the criterion.

---

## 9. What to carry out of here — one line per concept

1. Four containers, nested — not a ladder. Every beat still builds a prompt.
2. Each layer = its unit of work: one call, the window, one beat, the whole run.
3. Prompt = one model call. Fix the weakest ingredient only.
4. Context = the window. A curator always exists — find its rule.
5. Harness = one beat. Sub-agents run a whole nested stack and hand back unearned confidence.
6. A beat can prove a check passed — never that passing was enough.
7. Loop = heartbeat + spine + 4 outside stops, none decided by the maker.
8. The human gate is an exit, not a stop. Ambiguity isn't an error; a guess is worse than a crash.
9. Each layer fails its own recognizable way — name it before fixing anything.
10. Mode 1: you rent three, own one. Mode 2: you own all four.
11. Graphs are not a fifth layer — they describe what happens *between* nodes.
12. The map is a search order, not proof. Some failures cross layers; some aren't any of the four.

### The one sentence worth memorizing

> **A good prompt fails inside bad context. Good context fails inside a bare harness. A good harness sits idle without a loop. So when something breaks, name the layer before you reach for a fix.**

An agent that works in a demo often fails in production because the demo only ever needed the inner layers — the outer ones were never built. **The model was never the problem. The layers around it were missing.**

---

## 10. Why this is the real starting line of your journey

Everything in earlier topics (choosing a vertical, designing its System of Record, connecting it to real work) describes **what** you build. This topic is the first one that describes **how the thing you build actually runs** — and stays trustworthy. A Vertical FDE is paid to make the last 20% work reliably in a real company; that reliability lives exactly in these four layers, especially the harness's proof requirement and the loop's outside stops. This is the skill that turns a working demo into something a client will actually pay to keep running.

---

by _Dua Fatima khan_