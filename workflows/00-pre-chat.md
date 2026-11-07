# Workflow 0: Pre-chat Form

**Goal:** Collect useful context *before* the customer reaches the AI agent, so the bot can route urgent cases quickly.

## Fields
| Field | Type | Required | Options / Validation |
|---|---|---|---|
| First name | Text | Yes | 2–40 letters |
| Registered mobile number | Phone | Yes | Sri Lankan format `07XXXXXXXX` (demo) |
| What do you need help with? | Dropdown | Yes | My card is lost · My card was stolen · I see a transaction I don't recognise · I want to dispute a charge · Check my replacement card · Other question |
| Card type | Dropdown | Yes | Debit · Credit · Not sure |
| Last 4 digits of card | Text | No | Exactly 4 digits (`^\d{4}$`) |
| Is this urgent? | Radio | Yes | Yes, I'm worried someone is using my card · No |

## Security notice (shown on the form)
> 🔒 Lanka Trust Bank will **never** ask for your full card number, PIN, CVV or OTP. Never share them in this chat.

## Routing after pre-chat
| Pre-chat answer | First thing the bot does |
|---|---|
| Lost / Stolen | Starts the **Lost/Stolen Card Report** workflow |
| Unrecognised transaction **and** urgent = Yes | Starts the **Suspicious Transaction** workflow and offers an instant freeze |
| Dispute | Starts the **Transaction Dispute** workflow |
| Replacement | Starts the **Replacement Status** workflow |
| Other | Greets the user and answers from the KB |

## Greeting (personalised)
> Hi {first_name}, I'm CardGuard, Lanka Trust Bank's card security assistant. I can see you need help with **{issue}**. Let's sort it out together, it only takes a minute.
