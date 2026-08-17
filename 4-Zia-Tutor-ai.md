# Zia Tutor AI 
*A beginner-friendly guide to the personal AI tutor*

Source: [The AI Agent Factory](agentfactory.panaversity.org/docs/ecosystem/zia-tutor-ai)

---

## 1. What it is

Zia Tutor AI is a personal learning agent built as a **digital twin** of Zia Khan — Founder of Panaversity, co-author of this book, a CPA/CMA with three master's degrees.

It combines four things a normal AI chatbot does not have:
- The governed knowledge of the **Agent Factory System of Record**
- Zia Khan's actual teaching identity, method, and personality
- Your **persistent learning record** — what you studied, what you understood, what's next
- Your **personal profile** — your goals, background, and how you like to learn (yours to see and change anytime)

---

## 2. It lives inside the AI you already use

No separate app to install, no new interface to learn. You add one connector and one skill in claude.ai, and your existing AI agent becomes the tutor's runtime.

---

## 3. One narrow purpose, on purpose

Zia Tutor AI exists for exactly one thing: **helping you gain the expertise to build AI Workers and Digital FTEs, and become a Forward Deployed Engineer.**

It's called a **vertical personal AI agent for education** — it doesn't try to manage your whole life, just this one learning journey, in depth. It can:
- Greet you by name
- Remember where you stopped
- Continue across sessions and weeks
- Teach in the right sequence for you
- Check you understood the last concept before moving on
- Ground every lesson in the governed book content instead of guessing

---

## 4. Two roles in one system

| Role | What it means |
|---|---|
| **For the learner** | A personal tutor guiding your individual progress |
| **For the Agent Factory** | The **reference expert twin** — proof that a real expert's knowledge and teaching method can be encoded as an agent |

---

## 5. Three records working together

| Record | What it holds |
|---|---|
| **Knowledge Record** | The System of Record — what to teach |
| **Learner Record** | Your goal, progress, what you understood, your next step |
| **Identity Record** | Zia's voice, principles, explanations, and teaching method |

Together, these make something a plain chatbot with a system prompt can't fake: a tutor that's grounded, recognizable, and continuous across sessions.

---

## 6. Why it matters

First-generation AI tools gave everyone access to *answers*. Zia Tutor AI is the next generation: a personal agent that knows who you are, what you're trying to achieve, what you already know, where you're struggling, and what to study next.

---

## 7. How to set it up (about 2 minutes)

**Step 1 — Add the connector**
1. In claude.ai, open **Connectors** (under Customize) → **Add custom connector**.
2. Name: `Zia Tutor AI`. MCP Server URL: `https://zia-tutor-ai.panaversity.org/mcp`
3. Under **Advanced settings**, OAuth Client ID: `zia-tutor-ai`. Leave Client Secret empty.
4. Click **Add**, then find it in your list, click **Connect**, sign in with a Panaversity account, and approve.
5. Set **Tool permissions** to **Always allow** for both groups — otherwise Claude asks permission on almost every reply.

**Step 2 — Add the skill**
1. Download the `zia-tutor-ai.zip` skill file from the page.
2. In claude.ai, open **Skills** (under Customize) → **Add** → **Upload a skill**.
3. Drop in the zip file *without unzipping it first*.

**Step 3 — Start learning**
Type `/zia-tutor-ai` in any chat. Zia greets you by name and picks up where you left off.

> ⚠️ **Reminder for free-tier students:** if they're not on Claude Pro, they can only add one custom connector total — connect Zia Tutor AI directly rather than the raw System of Record connector (see the previous notes file).

---
by _Dua Fatima khan_