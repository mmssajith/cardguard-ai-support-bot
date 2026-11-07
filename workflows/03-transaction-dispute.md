# Workflow 3: Transaction Dispute

**Intent:** `dispute_transaction`
**Type:** Process workflow + Action (create dispute)

## Steps
1. **Reason** (buttons): `Charged twice` · `Wrong amount` · `Paid but not received` · `Cancelled but still charged` · `I didn't make this transaction`
   - `I didn't make this transaction` → redirect to **Suspicious Transaction** workflow
2. **Eligibility check:** "When did the transaction happen?" (date)
   - More than 60 days ago → explain the 60-day limit → offer a **callback** (a specialist may still help)
3. **Contacted the merchant?** (`Yes` / `No`)
   - No → recommend contacting the merchant first, but allow the user to continue anyway
4. **Details:** merchant name, amount, currency (`LKR` / `USD` / `Other`)
5. **High-value check:** amount > LKR 100,000 → **Escalation** to a Disputes Specialist
6. **ACTION: Create dispute** → reference `LTB-DP-XXXXXX`
7. **Evidence:** "You can email receipts to **cardcare@lankatrustbank.example (demo)** with your reference in the subject line."
8. **Summary:** reference, expected timeline (30–45 days), card stays active
