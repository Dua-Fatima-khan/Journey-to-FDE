# Agent Factory System of Record
*A beginner-friendly guide to the SoR connector*
Source: [The AI Agent Factory](agentfactory.panaversity.org/docs/ecosystem/system-of-record)

---

## 1. What it is

The Agent Factory System of Record (SoR) is the whole book, turned into something an AI agent can query directly. Its content is chunked, embedded, and served over a protocol called **MCP**.

Connect any AI agent Claude, ChatGPT, Claude Code, or a custom agent and it now answers **from the actual book**, instead of guessing from whatever it vaguely remembers from training.

---

## 2. Why it's trustworthy

- **Grounded, not guessing.** The agent cites the exact section it pulled the answer from.
- **Fails closed.** If the source is unreachable, it says "I can't answer"  it never makes something up to fill the gap.
- **Stays live.** It re-reads the book every time a new version publishes, so it never goes out of date. It's not a copy of the book  it *is* the book, made retrievable.

---

## 3. Why this matters for the bigger picture

This connector is **Layer 1** of the whole business model  the "SoR kernel." The exact same component that serves this book is what you'll eventually build for your *own* vertical: an accounting-standards SoR, a clinical-protocols SoR, a tax-filing-in-Pakistan SoR.


---

## 4. How to connect it 

1. In claude.ai, go to **Settings → Connectors → Add custom connector**.
2. Name: `Agent Factory System of Record`
   MCP Server URL: `https://sor.panaversity.org/mcp`
3. Open **Advanced settings**, paste OAuth Client ID: `zia-tutor-ai`. Leave Client Secret empty.
4. Click **Add**, find it in your connectors list, click **Connect**, and approve access.
5. Test it: ask Claude — *"Use the Agent Factory System of Record and explain what AI actually is."*

> ⚠️ **Important note for students not on Claude Pro:** free accounts can only add **one** custom connector total. Since Zia Tutor AI already reads from this same System of Record internally, don't use your one slot on the raw SoR connector connect **Zia Tutor AI directly** instead. You get the source *and* the teacher in one connection.

---

## 5. What differentiates it from Zia Tutor AI

This is the key distinction to teach clearly students often confuse the two.

| | Agent Factory SoR (this connector) | Zia Tutor AI |
|---|---|---|
| **What it is** | A grounded, queryable library | A teacher built *on top of* the same library |
| **Answers accurately?** | Yes | Yes |
| **Remembers you?** | No | Yes — keeps a Learner Record |
| **Has a teaching method?** | No — it just answers what's asked | Yes — decides what to teach next, when to quiz you |
| **Has a teaching voice?** | No | Yes — carries the author's actual voice and principles |

In one line: **the SoR is the trustworthy source of truth; Zia Tutor AI is the teacher who uses that source to actually teach you.** Connecting to the raw SoR alone gets you correct answers, not a course.

---
by _Dua Fatima khan_