# Daily Work Session rules

These rules apply to every agent working in this repository or running its workflow.

## Live-service safety

- Starting a daily session or Michael explicitly asking to `refresh` authorizes only the automatic Inbox noise cleanup defined in `skills/daily-work-session/references/housecleaning.md`. All other triage work begins read-only.
- Do not send, reply, forward, approve, reject, archive, delete, mark read, flag, pin, or edit an issue unless Michael explicitly authorizes that action.
- The start-and-refresh authorization covers only confirmed noise in the actual Inbox. It never covers uncertain mail, human mail that may need an answer, approvals, risks, retained follow-ups, or any non-Outlook action.
- Authorization is scoped to the named item or clearly described batch. Never infer permission for adjacent items.
- Resolve ambiguous recipients before sending. Prefer the sender or recipients from the source thread over directory guesses.
- Never add a manual email signature. Outlook adds it automatically.
- Never store credentials, API tokens, session links, tenant secrets, or message contents in this repository.
- Follow `skills/daily-work-session/references/authentication.md` for failed integrations. Prefer provider sign-in or device login and keep reusable credentials out of persisted chat and repository content.
- Attempt authentication recovery only after a required capability fails. Continue all unaffected sources while the failed integration waits for recovery.

## Inbox protection

- Query the actual Outlook Inbox, not a mailbox-wide search.
- Include all unread Inbox mail regardless of date, plus read mail deliberately retained for follow-up.
- Never archive an unread human message that may require Michael's answer unless he explicitly says to archive it.
- Treat automated alerts as meaningful when they represent approvals, expiries, failures, capacity, vulnerabilities, or operational risk.
- Housecleaning uses Archive, never Delete, and must be verified against the live Inbox before reporting counts.

## Interaction

- After the opening Inbox cleanup, work through Teams first and Outlook second.
- Never limit Teams or Outlook collection to the current date. Catch up work that arrived on missed days before presenting the current queue.
- Do not run a standalone Jira pass during normal daily triage. Query Jira only when a Teams or Outlook item refers to Jira work or Jira context is required to decide the item.
- Present one meaningful item at a time after the opening overview.
- State the question or decision first, then the essential facts and a recommendation.
- `next` advances past handled items. `done`, `sorted`, or an equivalent manual-action statement requires a relevant refresh before relying on the previous queue.
- Do not resurface handled items unless new information materially changes them.
- Keep communication with Michael concise. Match a recipient's established language only in the outgoing message.

## Memory recap

- Every new daily session must schedule one one-time recap for 21:30 Europe/Copenhagen inside that same chat.
- Reuse or preserve an existing recap task for the same chat and local date; never create a duplicate during refreshes or restarts.
- The recap invokes `$capture-memory` against `Mbo7682/Michaels-memory` and saves only durable decisions, commitments, owners, deadlines, project changes, lessons, and open threads from the chat context.
- Never store copied Outlook, Teams, or Jira content, secrets, authentication material, or transient triage detail in memory.
- If scheduling fails, continue triage and report the missing recap precisely.

## Repository changes

- Keep the skill entrypoint concise and route detailed procedures to `references/`.
- Validate both the skill and plugin after material changes.
- Preserve connector portability; use capability descriptions rather than hard-coded personal credentials or tenant-specific MCP configuration.
