# Workflow 2: Suspicious Transaction Check

**Intent:** `suspicious_transaction`
**Type:** Process workflow (decision tree) + Action + Escalation

## Steps
1. **Instant protection first**
   > Let's protect your money first. Shall I **freeze your card** right now while we check? You can unfreeze it any time.
   (buttons: `Yes, freeze it` / `No, keep it active`)
   - Yes → **ACTION: Freeze card**
2. **Do you recognise the merchant?** (buttons: `I've never heard of it` / `I know the merchant, but the amount or charge is wrong`)
3. **Branch A: Merchant unknown (likely fraud)**
   - Ask: amount (number), date (date picker), number of unknown transactions (`1` / `2–5` / `More than 5`)
   - **Risk rules:**
     - Amount > LKR 100,000 **or** more than 1 transaction **or** the user shared an OTP/PIN → **HIGH RISK**
     - Otherwise → **MEDIUM RISK**
   - HIGH → **ACTION: Block card permanently** → **Escalation** to a Fraud Specialist with summary
   - MEDIUM → Block card → open fraud dispute → reference `LTB-DP-XXXXXX` → offer a callback
4. **Branch B: Merchant known, charge wrong** → hand over to the **Transaction Dispute** workflow (merchant dispute)
5. **Confirmation summary** with the reference and next steps (temporary credit within 5 business days if eligible)

## Never
- Ask for an OTP, PIN, CVV or full card number
- Promise a refund. Say "may be eligible for a temporary credit".
