---
name: daily-work-session
description: "Run Michael's recurring work session across Outlook, Teams, and Jira. Use for morning updates, daily triage, Inbox review, queue refreshes, 'next' requests, item actions, and post-triage housecleaning."
---

# Daily Work Session

Create one concise, live decision queue across Outlook, Teams, and Jira. Begin read-only, preserve unresolved work throughout the chat, and move through one meaningful item at a time.

## Operating modes

### Start or refresh

1. Read [connectors.md](references/connectors.md), then query the live sources.
2. Apply the source procedures in [outlook.md](references/outlook.md), [teams.md](references/teams.md), and [jira.md](references/jira.md).
3. Merge the findings using [interaction.md](references/interaction.md).
4. Give a compact overview and present the first meaningful item. Make no state changes.

### Continue the session

Use [interaction.md](references/interaction.md) for `next`, `done`, `skip`, deferred work, drafting, sending, and queue refreshes. Keep handled message IDs, issue keys, and chat identifiers in conversation state so items are not repeated.

### Houseclean

Read [housecleaning.md](references/housecleaning.md) before any mailbox mutation. Archive only within Michael's explicit scope, protect unresolved communication, and verify the final Inbox.

### Scheduled start

Use [automation.md](references/automation.md) when configuring or running the workday start. A scheduled run starts the queue; it does not authorize mutations.

## Invariants

- Outlook means the actual Inbox folder. Include unread messages from every date and read messages retained for follow-up.
- Prioritize direct requests, approvals, deadlines, commercial decisions, security risks, and operational incidents. Suppress marketing, newsletters, routine reports, duplicates, and stale notifications.
- A machine sender does not make an item noise when it represents real work or risk.
- Keep triage read-only until Michael authorizes a specific action.
- Never archive unread human mail that may need Michael's answer without explicit instruction.
- Resolve ambiguous recipients before sending. Never add a manual email signature.
- Include a direct action link when listing approvals, preferably the specific approval; otherwise include the correct approval application.
- Refresh the relevant live source after Michael handles an item manually.
- Do not resurface handled items unless their status or contents materially change.

