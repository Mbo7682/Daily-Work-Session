# Daily Work Session rules

These rules apply to every agent working in this repository or running its workflow.

## Live-service safety

- Begin every triage or refresh read-only.
- Do not send, reply, forward, approve, reject, archive, delete, mark read, flag, pin, or edit an issue unless Michael explicitly authorizes that action.
- Authorization is scoped to the named item or clearly described batch. Never infer permission for adjacent items.
- Resolve ambiguous recipients before sending. Prefer the sender or recipients from the source thread over directory guesses.
- Never add a manual email signature. Outlook adds it automatically.
- Never store credentials, API tokens, session links, tenant secrets, or message contents in this repository.

## Inbox protection

- Query the actual Outlook Inbox, not a mailbox-wide search.
- Include all unread Inbox mail regardless of date, plus read mail deliberately retained for follow-up.
- Never archive an unread human message that may require Michael's answer unless he explicitly says to archive it.
- Treat automated alerts as meaningful when they represent approvals, expiries, failures, capacity, vulnerabilities, or operational risk.
- Housecleaning uses Archive, never Delete, and must be verified against the live Inbox before reporting counts.

## Interaction

- Merge Outlook, Teams, and Jira into one prioritized queue.
- Present one meaningful item at a time after the opening overview.
- State the question or decision first, then the essential facts and a recommendation.
- `next` advances past handled items. `done`, `sorted`, or an equivalent manual-action statement requires a relevant refresh before relying on the previous queue.
- Do not resurface handled items unless new information materially changes them.
- Keep communication with Michael concise. Match a recipient's established language only in the outgoing message.

## Repository changes

- Keep the skill entrypoint concise and route detailed procedures to `references/`.
- Validate both the skill and plugin after material changes.
- Preserve connector portability; use capability descriptions rather than hard-coded personal credentials or tenant-specific MCP configuration.

