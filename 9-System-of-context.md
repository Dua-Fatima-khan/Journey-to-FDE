# The System of Context: Connecting the Records to Real Work

*A beginner-friendly guide to connecting your knowledge to a real company*

Source: [The AI Agent Factory](agentfactory.panaversity.org/docs/ecosystem/system-of-context)

---

## 1. The core idea

**A System of Record decides what's true. A System of Context decides what arrives.**

Your Vertical System of Record knows the profession's rules. It knows nothing about this specific customer's actual contract, this morning's delivery, the running balance, or the message where a manager explained a decision nobody wrote down. The Worker needs BOTH to finish real work.

Skip this layer and you get: a brilliant graduate on day one, holding a perfect textbook, in a building where nobody has shown them the filing cabinet.

---

## 2. The QuickBooks example (clearest illustration)

QuickBooks is a popular accounting software platform developed by Intuit. QuickBooks holds every transaction and balance perfectly. Ask it whether a lease *should* have been classified as a finance lease it has nothing to say. That was never its job.

**QuickBooks is authoritative about what was recorded. Your record is authoritative about whether it should have been recorded that way.** Both are needed. Neither replaces the other.


---

## 3. Three layers, three jobs

| Layer | Its question | Its job |
|---|---|---|
| **Systems of Record** (both kinds) | What is officially true? | Govern facts, rules, versions, permissions |
| **System of Context** | What's relevant right now? | Connect, route, retrieve, filter, assemble |
| **Human or AI Worker** | What should be done? | Reason, decide within authority, act |

**Key rule:** the System of Context sits ABOVE the records in *access* (it can see across them). It never sits above them in *authority* (it can never outrank them).

---

## 4. The one law: authority never moves

> **The System of Context carries authority. It never holds it.**

When a Worker cites something, the citation points back to the real record  never to the connecting layer's copy. Think of a delivery driver: the parcel belongs to the sender, never the driver.

---

## 5. The model itself is not a source

A language model can answer fluently and even correctly  but it has no version, no owner, no way to be corrected when a rule changes. Plausible ≠ provable.

**Three quiet ways a model becomes a fake source:**
1. **The gap fill** — retrieval finds nothing, model answers from vague memory anyway
2. **The drifting paraphrase** — restating a rule loses an exact threshold
3. **Unmanaged model memory** — facts persist across sessions with no owner or version

**What the model IS for:** the middle 80% — applying the reflex, drafting, spotting conflicts, explaining its reasoning. Never being the source of truth.

**The test that settles any doubt:** *Can a reviewer rebuild this conclusion from the record, without asking the model?* If no — the model was the source, and the answer isn't defensible.

---

## 6. Authority is scoped, not one ladder

A company may run SEVERAL Vertical Systems of Record at once (sales, accounting, HR  each built by different people). Route by **profession first** a sales rule must never answer an accounting question, even if it retrieves well against it.

⚠️ Never merge two professions' records into one corpus. A blended page can't be cited in either profession.

---

## 7. Three questions, three paths

| The question | Where it goes |
|---|---|
| What is the rule? | Retrieval from the governed Vertical/Agent Factory SoR |
| What is the number? | A LIVE typed query to the system that owns it |
| What did people say about this case? | Retrieval from customer's own material  as supporting evidence only, never as the rule |

---

## 8. What can be indexed vs. what must be asked live

| Info type | Rule |
|---|---|
| **Working context** (emails, chat) | Index freely |
| **Governed knowledge** | Can be indexed for discovery, but must be CONFIRMED against the real record before relying on it |
| **Current state** (balances, approvals) | NEVER indexed — always fetched live |

**Golden rule:** if a stale value could change the conclusion, a payment, or a filing... fetch it live.

---

## 9. Permission comes before the model, always

Forbidden content must NEVER even enter the model's context. Hiding it after the fact isn't real hiding  a hidden passage inside the model's context is not hidden.

⚠️ **Bigger than privacy:** in regulated professions, a permission failure doesn't just leak information  it quietly invalidates the entire access review the firm's controls depend on.

---

## 10. Conflict is a result, not a failure

When two sources disagree, NEVER blend them into one smooth sentence nobody actually said.

Three honest outcomes:
1. **Resolved by scope** — both sources are right, they're answering different questions
2. **Resolved by authority** — the hierarchy says clearly which wins
3. **Escalated** — a named human decides, with the evidence already organized

---

## 11. The eight invariants (memorize these)

1. Authority never moves
2. Relevance is not authority
3. Permission is inherited, never invented — enforced before the model
4. Freshness is decided per field (index / discover / query live)
5. Provenance travels with every item
6. Conflict is preserved, never blended
7. The ungoverned never silently becomes governed
8. Discovery is not confirmation

---

## 12. When you DON'T need one

Don't build this layer until your thin slice is finished and a Worker already cites it. If the record plus the company's existing systems already answer everything the outcome needs, you don't need this layer building it too early can waste months.

You DO need one when "why was it done this way" lives outside every governed system  audit firms with 20 years of working papers, legal practices with old case files.

---

## 13. Why this matters for your goal

This is literally the difference between being hired once and being kept as a client. The Vertical SoR is what makes you worth *hiring*. Actually connecting your knowledge to a real client's messy real-world systems is what makes you worth *keeping* and it's ongoing paid work, not a one-time build.

---
by _Dua Fatima khan_