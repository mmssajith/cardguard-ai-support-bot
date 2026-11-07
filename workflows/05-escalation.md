# Workflow 5: Escalation to a Human

**Intents:** `talk_to_agent`, plus automatic triggers from the other workflows
**Rule requirement:** at least **two** escalation/contact options, using demo contact details.

## Automatic triggers
| Trigger | Source |
|---|---|
| Unauthorized transactions, HIGH risk | Suspicious Transaction WF |
| Amount > LKR 100,000 | Dispute / Suspicious WF |
| User shared an OTP/PIN, or account takeover signs | Phishing intent |
| Block/freeze action failed | Any WF |
| No answer found in the KB twice in a row | Knowledge-gap fallback |
| Negative sentiment (e.g. "this is useless", "I'm scared") | Sentiment |
| User asks for a human | `talk_to_agent` |

## Options shown to the user
> I'll get you to the right person. How would you like to continue?

1. 💬 **Chat with a Fraud Specialist now** (live handoff, 24/7)
2. 📞 **Call the 24-hour Card Hotline:** +94 11 000 0000 (demo)
3. 🔁 **Request a callback**: collect preferred time (`Within 2 hours` / `Tomorrow morning` / `Tomorrow evening`)
4. ✉️ **Email:** cardcare@lankatrustbank.example (demo), for documents

For HIGH risk, option 1 is shown first and highlighted.

## Handoff summary (passed to the agent)
```
Customer: {first_name} | Mobile: {mobile_masked}
Issue: {issue_type} | Card: {card_type} ****{last4}
Risk level: {LOW|MEDIUM|HIGH}
Actions completed: {card frozen/blocked, dispute created}
Reference(s): {refs}
Customer said: "{last_user_message}"
Transcript: attached
```

## Knowledge-gap fallback message
> I'm not certain about that, and I don't want to give you wrong information about your money. Would you like me to connect you with a specialist who can help?
