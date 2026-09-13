---
name: daily-work-session
description: "Run Michael's recurring work session with automatic Outlook cleanup, Teams-first triage, contextual Jira lookup, item actions, and a same-chat 21:30 memory recap. Use for morning updates, daily triage, Inbox review, queue refreshes, 'next' requests, and housecleaning."
---

# Daily Work Session

Start by protecting the day's memory recap and removing confirmed Inbox noise, then run one concise decision queue in source order: Teams first and Outlook second. Use Jira only to enrich items that point to Jira work. Preserve unresolved work throughout the chat and move through one meaningful item at a time.

## Operating modes

### Start or refresh

For a new daily session:

1. Read [connectors.md](references/connectors.md) and [housecleaning.md](references/housecleaning.md). If a required capability fails because access is missing, expired, or insufficient, read [authentication.md](references/authentication.md) and recover only that integration.
2. Read [memory.md](references/memory.md) and ensure one same-chat recap is scheduled for 21:30 Europe/Copenhagen that day. Do not duplicate an existing recap.
3. Perform the authorized startup cleanup against the actual Outlook Inbox. Archive only confirmed noise, verify the result, and leave uncertain or protected mail untouched.
4. Read [teams.md](references/teams.md) and [interaction.md](references/interaction.md). Review the full unhandled Teams scope without a current-date filter and present the first meaningful item.
5. After the Teams stage is exhausted, read [outlook.md](references/outlook.md), refresh the Inbox, and review the retained mail.
6. Read [jira.md](references/jira.md) only when a Teams or Outlook item refers to Jira work or needs Jira context.

When Michael explicitly asks to `refresh` during an active session, first rerun the same narrow, verified Inbox cleanup, then refresh the relevant current source. Preserve handled and deferred identifiers. Internal source refreshes used to verify actions or advance stages do not trigger cleanup.

### Continue the session

Use [interaction.md](references/interaction.md) for `next`, `done`, `skip`, deferred work, drafting, sending, and queue refreshes. Keep handled message IDs, issue keys, and chat identifiers in conversation state so items are not repeated.

### Houseclean

Read [housecleaning.md](references/housecleaning.md) before any mailbox mutation. Starting a daily session or Michael explicitly asking to `refresh` authorizes only its narrow confirmed-noise cleanup. Any broader cleanup requires Michael's explicit scope. Protect unresolved communication and verify the final Inbox.

### Scheduled start

Use [automation.md](references/automation.md) when configuring or running the workday start. The scheduled daily start carries the narrow authorization to archive confirmed Inbox noise and to create the one-time same-chat memory recap. It authorizes no other mutation.

## Invariants

- Outlook means the actual Inbox folder. Include unread messages from every date and read messages retained for follow-up.
- Teams means all accessible unreviewed direct chats, direct requests in group chats, and mentions regardless of the day received. Use unread or last-read markers when available and a minimum seven-day safety scan so missed workdays are covered.
- Never treat a current-day query as complete source coverage. State the earliest date or marker actually inspected when a connector limits history.
- Prioritize direct requests, approvals, deadlines, commercial decisions, security risks, and operational incidents. Suppress marketing, newsletters, routine reports, duplicates, and stale notifications.
- A machine sender does not make an item noise when it represents real work or risk.
- After each authorized cleanup, keep triage read-only until Michael authorizes a specific action.
- Work through Teams before Outlook. Do not run a standalone Jira pass during normal daily triage.
- Query Jira when a surfaced Teams or Outlook item references an issue, project, sprint, or Jira-managed commitment and current Jira data affects the decision.
- Schedule the memory recap only on a new daily-session start, never on `refresh`.
- Never archive unread human mail that may need Michael's answer without explicit instruction.
- Resolve ambiguous recipients before sending. Never add a manual email signature.
- Include a direct action link when listing approvals, preferably the specific approval; otherwise include the correct approval application.
- Refresh the relevant live source after Michael handles an item manually.
- Do not resurface handled items unless their status or contents materially change.
- An unavailable integration must not block healthy sources. Report partial coverage and resume the failed source after authentication succeeds.
