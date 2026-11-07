# Workflow 4: Replacement Card Status

**Intent:** `replacement_status`
**Type:** Process workflow + Action (lookup)

## Steps
1. Ask for the reference number (format `LTB-LS-XXXXXX`), or offer `I don't have it`
   - Validate the format; on an invalid format, re-ask once, then offer a callback
   - `I don't have it` → ask for the last 4 digits of the old card plus confirmation of the registered mobile number
2. **ACTION: Lookup status** (demo data):
   | Ref ends with | Status returned |
   |---|---|
   | `1` – `3` | Card printed, dispatching soon |
   | `4` – `6` | Out for delivery, expected {date} |
   | `7` – `9` | Delivered, activate in LTB Mobile → Cards → Activate |
   | `0` | Delayed → offer escalation |
3. Show the status, plus the tip to add the card to a digital wallet now
4. Delayed or more than 10 days since request → offer a **callback** or **live specialist**
