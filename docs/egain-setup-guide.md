# eGain Build Checklist

A step-by-step order for building CardGuard in eGain once you have hackathon access. Menu names may differ slightly from the hackathon tutorial, so follow the tutorial for the exact clicks.

## Hackathon requirements → where they live in this repo
| Rule requirement | Repo file |
|---|---|
| Knowledge-based AI Agent | `knowledge-base/*.md` |
| Published experience | `docs/agent-persona.md` |
| Pre-chat workflow | `workflows/00-pre-chat.md` |
| Escalation workflow (≥ 2 options) | `workflows/05-escalation.md` |
| Process workflow tied to an intent | `workflows/01–04`, `intents/intents.md` |
| Actions | Block/Freeze card, Create dispute, Lookup status |
| Validation | `demo/test-cases.md` |

## Build order
1. **Get access:** Register on Devpost and get eGain workspace access (check email, the Updates tab and Discord).
2. **Create the AI Agent** "CardGuard" and paste the persona from `docs/agent-persona.md`.
3. **Upload the knowledge:** Add the 5 articles from `knowledge-base/` as authorized content. Test 5–10 questions in *Test AI Agent*.
4. **Create the intents** from `intents/intents.md` with their sample utterances.
5. **Build the pre-chat form** (`workflows/00-pre-chat.md`).
6. **Build the process workflows** in this order (the most valuable first):
   1. Lost/Stolen Card (01)
   2. Suspicious Transaction (02)
   3. Escalation (05)
   4. Dispute (03)
   5. Replacement Status (04), if there's time
7. **Add Actions:** Block/Freeze card, Create dispute, Lookup status. Use demo or mock responses that return reference numbers.
8. **Connect each intent** to its workflow.
9. **Customise the look:** name, avatar, colours, welcome message and quick replies.
10. **Publish** and wait up to 5 minutes, then test with the public demo link.
11. **Run every test** in `demo/test-cases.md` both in Test AI Agent **and** on the published link.
12. **Record** the 1-minute video (`demo/demo-script.md`) and **submit** on Devpost.

## Time plan (deadline: check Devpost, around Nov 12–15, 2026)
| Day | Goal |
|---|---|
| Day 1 | Access, agent, knowledge base, intents |
| Day 2 | Pre-chat + Lost/Stolen + Suspicious workflows |
| Day 3 | Escalation + Dispute + Actions, then publish |
| Day 4 | Testing, polish, video, submission |
