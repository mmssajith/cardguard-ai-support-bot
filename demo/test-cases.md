# Test Cases

Run each test in **Test AI Agent** and on the **published demo link**. Tick both columns.

| # | Input / path | Expected result | Test agent | Published |
|---|---|---|---|---|
| T1 | Pre-chat → "My card is lost", urgent = No | Lost/Stolen WF starts, offers freeze vs block | ☐ | ☐ |
| T2 | Lost → Freeze temporarily | Freeze confirmed + `LTB-LS-` ref, no replacement offered | ☐ | ☐ |
| T3 | Stolen → Block → Standard replacement | Block confirmed, ref, 5–7 days, police report tip | ☐ | ☐ |
| T4 | Lost → "Any unknown transactions?" = Yes | Jumps to escalation (HIGH risk) | ☐ | ☐ |
| T5 | User types a 16-digit number | Warns not to share it and asks for the last 4 only | ☐ | ☐ |
| T6 | "I didn't make this payment", LKR 5,000, 1 txn | MEDIUM risk → block → dispute ref → callback offer | ☐ | ☐ |
| T7 | Unknown txns, LKR 150,000 | HIGH risk → block → fraud specialist handoff with summary | ☐ | ☐ |
| T8 | "I shared my OTP with someone" | Freeze card → immediate escalation | ☐ | ☐ |
| T9 | Dispute: charged twice, 10 days ago | Dispute ref `LTB-DP-`, 30–45 days, card stays active | ☐ | ☐ |
| T10 | Dispute: 90 days ago | Explains the 60-day limit, offers a callback | ☐ | ☐ |
| T11 | "Where is my new card?" ref `LTB-LS-000124` | Returns the "Out for delivery" status | ☐ | ☐ |
| T12 | "Will the bank ask for my OTP?" | KB answer: never | ☐ | ☐ |
| T13 | "What's the difference between freeze and block?" | KB answer | ☐ | ☐ |
| T14 | "What's the interest rate on home loans?" (out of scope) | Knowledge-gap message → offers a specialist | ☐ | ☐ |
| T15 | "Talk to a person" | Shows ≥ 2 contact options (chat, hotline, callback, email) | ☐ | ☐ |
| T16 | "This is useless, I'm scared" | Empathetic reply + escalation offer | ☐ | ☐ |
| T17 | Block action fails (simulate) | Shows the hotline + specialist option | ☐ | ☐ |
