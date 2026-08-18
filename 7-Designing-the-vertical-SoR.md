# Designing the Vertical System of Record
*A beginner-friendly guide to building the corpus from first principles*

Source: [The AI Agent Factory](agentfactory.panaversity.org/docs/ecosystem/designing-the-vertical-sor)

---

## 1. Why the old workflow is the wrong blueprint 

Every profession's current workflow looks the way it does because of **five human-era limits**:

1. Scarce human attention → weekly reports, review batches
2. Scattered information across systems → re-typing the same data
3. Software couldn't understand judgment → everything routed to a person
4. Department silos → handoffs the customer never asked for
5. Managers couldn't see the work → blanket approvals to cover for it

None of that IS the profession. It's the human-only era's answer to human-only limits.

**The core question to ask:** if this profession started today, knowing what AI Workers can do, where would human time actually go?

---

## 2. First principles, applied unevenly

First-principles thinking = break a problem to its bedrock truths, then rebuild from there  instead of just copying what others already do.

But it applies **differently** to the three parts of a System of Record:

| Part | How first principles applies |
|---|---|
| **Corpus** (laws, standards) | The given. Served faithfully, NEVER redesigned. "Rethinking" the tax code just builds a confident wrong-answer machine. |
| **Reflexes** (the "how we do it" procedures) | Rebuilt completely from scratch  every old one carries human workarounds. |
| **Map** (what exists, when to read it) | Redrawn around what a Worker needs  not around old departments. |

---

## 3. Start from the outcome, not the workflow

Before touching the old process, write the **outcome contract**:

| Field | Question |
|---|---|
| Outcome | What completed result must exist? |
| Trigger | What starts the work? |
| Evidence | What must support the result? |
| Acceptance criteria | How does a reviewer judge it complete? |
| Main number + guardrails | What improves, what must not get worse? |
| Forbidden actions | What must the Worker never do? |
| Final authority | Which named human is accountable? |

This becomes the seed of the Worker's future contract of success.

---

## 4. Workflow archaeology

Now study the old process not to copy it, to **dig into it**. Walk five real cases with your expert: one normal, one difficult, one that failed, one that needed escalation, one where an expert caught something a beginner missed.

**Key question:** what do experienced people check that the written procedure never mentions?


---

## 5. The three-bin sort

For every element of the old workflow, ask: **why does this exist?** Only three honest answers:

| Bin | Reason | What happens |
|---|---|---|
| **Bin 1: Law & trust** | Regulator or profession requires it | **Keep it** — becomes an invariant (a rule that stays true no matter what) |
| **Bin 2: Human limits** | Humans forget, tire, can't hold the whole file | **Redesign it** — the purpose survives as Worker capability + a checker |
| **Bin 3: Old technology** | Pre-AI systems couldn't talk to each other | **Delete it** entirely |

**Example (Bin 2):** "A manager reviews every transaction" — the *purpose* (risk control) is Bin 1, keep it. The *mechanism* (review everything) is Bin 2 — redesign so routine cases pass automatic checks, and the manager's attention goes only to real exceptions.

⚠️ **When in doubt, leave it in Bin 1.** Deleting something that turns out to be law is the single boldest failure mode on this whole page.

---

## 6. The source hierarchy

When two sources disagree, the Worker must know which one wins:

1. Current law and regulation
2. Binding professional standards
3. Official regulator interpretations
4. Approved domain policy
5. Your expert's authored procedures
6. Customer-specific policy
7. Historical examples

Every source gets a register entry (publisher, jurisdiction, version, rights basis). **Relevance is not enough — the source must also be applicable** (right jurisdiction, right version).

---

## 7. Two kinds of content, one page

Every page has **two readers**: a human reads it like a book, a Worker cites it like a rulebook.

| Type | What it is | Rule |
|---|---|---|
| **Authority** | Citable content: law, current rates, the expert's method | Passes at least one of: citation test, change test, dispute test |
| **Orientation** | Short plain intro so a human isn't lost | Marked as context — the Worker may read it, but **never cites it** |

**Write for the "day-one junior professional":** simple enough for them to read, exact enough for a reviewer to check, structured enough for a Worker to cite.

---

## 8. Map decisions, not departments

Don't build one agent per department  that just copies the old org chart. Instead, map the **decisions** the outcome actually needs (e.g. for invoice review: is the supplier valid? do amounts agree? is it a duplicate?). Decisions outlive departments and stay reusable across any customer's org structure.

---

## 9. Rules, judgment, and permissions are three different things

| Type | What it is | Example |
|---|---|---|
| **Rule** | Clear if-then, automatic | "Over $500k needs approval" |
| **Judgment** | Needs interpretation, must be supported | "Is this evidence enough?" |
| **Permission** | What the Worker may DO after deciding | Read / recommend / prepare / execute |

**Safe default in regulated work:** the Worker prepares and recommends. A named human approves and acts.

---

## 10. Design exceptions before the normal path

Trust is built at the edges, not the happy path. For each failure shape (missing evidence, conflicting sources, low confidence), define: how it's detected, what the Worker may/must not do, who gets the escalation, what it must contain.

**A useful escalation is a ready-made decision** — not just "I'm unable to continue." It should say what's already been verified and what single thing is still needed.

---

## 11. Rebuild the reflexes, then build one thin slice

Write fresh procedures around the outcome and the Bin-1 invariants — never just convert the old SOP into Markdown (that's still the old process, only faster).

**Build ONE complete outcome first ("thin," not a draft).** Every outcome present must be covered completely — a slice that only handles clean cases isn't thin, it's unfinished. Test it against messy edge cases, with the expert's own reviewers judging the results.

---

## 12. The 8 failure modes (quick checklist)

1. **Document dump** — files + search, no hierarchy or versions
2. **AI-readable SOP** — old procedure just converted to Markdown
3. **Technology first** — database and framework before the outcome
4. **Rules hidden in prompts** — controls that are just sentences, unversioned
5. **Authority before evidence** — Worker allowed to act before it's proven
6. **Happy-path demo** — only clean examples tested
7. **First-principles theater** — deleting Bin 1 because it looked like a habit
8. **Unmarked textbook** — full lessons loaded as citable authority

---

## 13. Why this matters for your own goal

This exact method is what turns "I've chosen a vertical" into a real, sellable, teachable system. The corpus and reflexes designed this way are the actual product you'd sell to a client — and that same sorted, exact material is what you'd teach a student.

---

by _Dua Fatima khan_