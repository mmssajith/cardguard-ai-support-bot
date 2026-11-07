# CardGuard Intents

Each intent maps to either a **knowledge answer** (KB) or a **process workflow** (WF). Paste the sample utterances into eGain when creating each intent.

| # | Intent | Routes to | Priority |
|---|---|---|---|
| 1 | `report_lost_card` | WF: Lost/Stolen Card Report | Urgent |
| 2 | `report_stolen_card` | WF: Lost/Stolen Card Report | Urgent |
| 3 | `freeze_or_block_card` | WF: Freeze / Block Card | Urgent |
| 4 | `suspicious_transaction` | WF: Suspicious Transaction Check | Urgent |
| 5 | `dispute_transaction` | WF: Transaction Dispute | Normal |
| 6 | `replacement_status` | WF: Replacement Status | Normal |
| 7 | `card_security_faq` | KB: Card Security FAQ | Normal |
| 8 | `phishing_scam_report` | KB + Escalation | High |
| 9 | `talk_to_agent` | Escalation workflow | — |

---

## 1. report_lost_card
- I lost my card
- I can't find my debit card
- I think I dropped my credit card somewhere
- My card is missing
- I misplaced my card yesterday
- lost card
- I left my card at a restaurant

## 2. report_stolen_card
- My wallet was stolen
- Someone stole my card
- My bag was snatched with my cards in it
- I was pickpocketed
- My card has been stolen

## 3. freeze_or_block_card
- Block my card
- Freeze my card now
- Can you stop my card
- I want to cancel my card
- Temporarily lock my card
- Unfreeze my card

## 4. suspicious_transaction
- There's a transaction I don't recognise
- I didn't make this payment
- Someone used my card
- I got an SMS for a purchase I didn't make
- Unknown charge on my account
- Money was taken from my card

## 5. dispute_transaction
- I want to dispute a charge
- The merchant charged me twice
- I was charged the wrong amount
- I paid but never received my order
- I cancelled my subscription but still got charged
- How do I get a chargeback

## 6. replacement_status
- Where is my new card
- When will my replacement card arrive
- Track my card delivery
- I haven't received my new card

## 7. card_security_faq
- Will the bank ask for my OTP
- What is the difference between freeze and block
- How do I turn on transaction alerts
- Can I use my card abroad
- Am I liable for fraud

## 8. phishing_scam_report
- Someone called me pretending to be the bank
- I got a suspicious SMS with a link
- I shared my OTP with someone
- I think I clicked a scam link

> If the user says they **shared their OTP/PIN**, treat it as high risk → freeze the card → escalate immediately.

## 9. talk_to_agent
- I want to talk to a person
- Connect me to an agent
- Human please
- Can I speak to someone
- Call me back
