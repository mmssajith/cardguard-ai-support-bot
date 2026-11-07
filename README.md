# CardGuard: AI Lost Card & Fraud Support Bot

> An AI support agent for banks that helps customers **report lost or stolen cards**, **flag suspicious transactions**, and **reach a human fraud specialist** quickly, with the full context passed along.

Built for the Devpost hackathon **[Build, Demo, and Take Home a Working AI Support Bot](https://build-a-working-ai-support-bot.devpost.com/)** using the **eGain** platform.

---

## The problem

When a card goes missing or a strange charge shows up, customers panic. Typically they:

- Wait on hold for a long time to reach the bank's hotline
- Have to repeat the same details to several agents
- Don't know what to do in the meantime (block the card? change the PIN? file a dispute?)

Every minute of delay is a minute a fraudster can keep using the card. Banks lose money, and customers lose trust.

## The solution

**CardGuard** is a 24/7 AI support bot that:

1. **Answers questions** about card security, disputes, chargebacks and replacement timelines, grounded in the bank's own policy documents.
2. **Guides the customer step by step** through urgent tasks, such as temporarily blocking a card, reporting it lost or stolen, or disputing a transaction.
3. **Escalates intelligently** to a human fraud specialist for high-risk cases, with a structured summary so the customer never has to repeat themselves.

---

## Key features

| Feature | Description |
|---|---|
| Pre-chat triage | Collects the issue type (lost, stolen, suspicious charge, general question), card type and a risk-level hint before the conversation starts |
| Safe verification | Verifies the user with **non-sensitive** questions only. It never asks for a full card number, PIN, CVV or OTP |
| Card block workflow | Guided process to temporarily freeze or permanently block a card, then confirm and log the incident |
| Lost / stolen report | Captures when and where the card was last used and the delivery address for a replacement, and issues a reference number |
| Transaction dispute | Collects merchant, amount and date, explains the chargeback process and timelines |
| Grounded answers | Answers come only from the bank's knowledge base (FAQs, card T&Cs, dispute policy) |
| Knowledge-gap handling | When the answer isn't in the knowledge base, the bot says so clearly and offers a human handoff instead of guessing |
| Smart escalation | Auto-escalates on high-risk signals: confirmed fraud, large amounts, account takeover, distressed sentiment or repeated failures |
| Context handoff | The human agent receives a summary: issue type, steps already done, reference number and transcript |
| Multilingual (stretch goal) | English, Sinhala and Tamil support |

---

## Conversation flows

```
                 ┌──────────────────┐
                 │  Pre-chat form   │  issue type · card type · urgency
                 └────────┬─────────┘
                          ▼
                 ┌──────────────────┐
                 │ Intent detection │
                 └────────┬─────────┘
     ┌──────────────┬─────┴────────┬──────────────────┐
     ▼              ▼              ▼                  ▼
 Lost/stolen   Suspicious txn   Card question    "Talk to a human"
     │              │              │                  │
     ▼              ▼              ▼                  │
 Verify user    Verify user    KB-grounded answer     │
     │              │              │                  │
 Block card     Fraud risk?    Answer found? ──No──┐  │
     │           │       │         │Yes            │  │
 Replacement    Low     High       ▼               ▼  ▼
 + ref number    │       │     Resolved      ┌───────────────┐
     │       Dispute     └────────────────▶ │ Human fraud   │
     ▼        flow                           │ specialist    │
 Resolved        │                           │ (+ summary)   │
                 ▼                           └───────────────┘
              Resolved
```

### Escalation triggers

- The customer reports **unauthorized transactions they did not make**
- The disputed amount is above a set threshold
- Signs of **account takeover** (changed phone or email, unknown logins)
- Negative or distressed sentiment
- Two or more failed attempts to resolve, or the customer explicitly asks for a human

---

## Intents

| Intent | Example utterances |
|---|---|
| `report_lost_card` | "I lost my debit card", "Can't find my credit card" |
| `report_stolen_card` | "My wallet was stolen", "Someone took my card" |
| `block_card` | "Freeze my card", "Block my card now" |
| `suspicious_transaction` | "There's a charge I don't recognise", "I didn't make this payment" |
| `dispute_transaction` | "I want to dispute a charge", "Merchant charged me twice" |
| `replacement_status` | "When will my new card arrive?" |
| `card_security_faq` | "How do I stay safe from phishing?", "Will the bank ever ask for my OTP?" |
| `talk_to_agent` | "I want to speak to someone", "Connect me to a human" |

---

## Built with

- **[eGain](https://www.egain.com/)**: AI agent, knowledge hub, intents, process workflows, pre-chat and escalation
- Sample knowledge base: a fictional bank's card FAQs, dispute policy and security guidelines (see `/knowledge-base`)

> **Note:** CardGuard uses a **fictional bank** ("Lanka Trust Bank") and demo data only. No real customer data, card numbers or banking systems are involved.

---

## Repository structure (planned)

```
cardguard-ai-support-bot/
├── README.md
├── knowledge-base/        # Sample FAQs, policies and articles for grounding
├── workflows/             # Process workflow designs (block, report, dispute)
├── intents/               # Intent definitions and sample utterances
├── docs/                  # Architecture diagrams and screenshots
└── demo/                  # Demo script and video link
```

---

## Demo

- **Live agent:** _coming soon_
- **Demo video:** _coming soon_

### Demo script (2–3 minutes)

1. **Happy path:** The customer lost their card, verifies, blocks it, orders a replacement and gets a reference number.
2. **Knowledge gap:** The customer asks something outside the knowledge base, and the bot admits it doesn't know and offers a human.
3. **High-risk escalation:** The customer reports unknown transactions, and the bot blocks the card and hands off to a fraud specialist with a full summary.

---

## Security and privacy principles

- Never collect a full card number, PIN, CVV, OTP or password in chat
- Use masked identifiers only (e.g. the last 4 digits)
- Remind customers that the bank will never ask for an OTP or PIN
- All data in this project is synthetic

---

## Roadmap

- [ ] Set up the eGain workspace and knowledge base
- [ ] Define intents and sample utterances
- [ ] Build the pre-chat form
- [ ] Build the block card, lost/stolen and dispute workflows
- [ ] Configure escalation rules and agent handoff
- [ ] Add knowledge-gap fallbacks
- [ ] Publish the agent and record the demo
- [ ] (Stretch) Sinhala and Tamil support

---

## Judging criteria alignment

| Criterion | How CardGuard addresses it |
|---|---|
| Customer & business value | Cuts fraud losses and hotline load, and resolves urgent issues faster |
| Functionality & reliability | Grounded answers, tested workflows, graceful fallbacks |
| Effective use of eGain | Intents, process workflows, pre-chat and smart escalation, beyond basic Q&A |
| Creativity & CX | Calm, guided experience for a stressful moment, context-rich handoff |

---

## Author

**Sajith** ([@mmssajith](https://github.com/mmssajith))

## License

MIT
