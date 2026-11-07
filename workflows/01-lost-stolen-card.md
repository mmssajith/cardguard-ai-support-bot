# Workflow 1: Lost / Stolen Card Report

**Intents:** `report_lost_card`, `report_stolen_card`
**Type:** Process workflow + Action (block card)

## Steps
1. **Empathise and reassure**
   > I'm sorry to hear that. Don't worry, we'll secure your card right now.
2. **Lost or stolen?** (buttons: `Lost` / `Stolen`), skipped if already known from pre-chat
3. **Confirm card**: "Is this your {card_type} card ending in {last4}?" (buttons: `Yes` / `No, a different card`)
   - If last4 is unknown, ask for it, validating 4 digits only.
   - ⚠️ If the user types 12–19 digits, don't store them. Reply: *"For your safety, please don't share your full card number. I only need the last 4 digits."*
4. **Freeze or block?**
   - Lost → offer: `Freeze temporarily (I might find it)` / `Block permanently`
   - Stolen → recommend **Block permanently**
5. **ACTION: Block/Freeze card**: call the demo action → returns reference `LTB-LS-XXXXXX`
6. **Any unknown transactions?** (buttons: `Yes` / `No` / `Not sure`)
   - `Yes` → jump to **Escalation workflow** (high risk) with context
7. **Replacement card** (block only): `Standard (5–7 days, free)` / `Branch pickup (2–3 days)` / `Express (1–2 days, LKR 1,000)` / `No replacement`
8. **Confirmation summary**
   > ✅ Your card ending in {last4} has been **{blocked/frozen}**.
   > Reference: **{ref}**
   > Replacement: **{option}**, arriving in {timeline}.
   > Tip: update any subscriptions with your new card once it arrives.
9. **Stolen only:** suggest filing a police report.
10. **Close:** "Is there anything else I can help with?"

## Error handling
- Action fails → "I couldn't complete that right now. For your safety, please call our 24-hour hotline **+94 11 000 0000 (demo)** or I can connect you to a specialist now." → Escalation
- User stops replying for 2 minutes → send a reminder that includes the hotline number
