# Inbox housecleaning

Housecleaning is a live mailbox mutation. Starting a daily work session or Michael explicitly asking to `refresh` is standing authorization to archive confirmed noise from the actual Inbox using the rules below. Any broader cleanup still requires Michael's explicit authorization.

## Startup scope

Without asking for confirmation, every daily start or explicit `refresh` may archive only messages that are clearly noise after inspecting enough content to classify them, such as marketing, newsletters, routine reports without consequence, superseded duplicates, and completed automated FYIs.

Always protect:

- unread human mail that may need Michael's answer;
- approvals, expiries, failures, security findings, capacity warnings, deployment gates, and other operational risk;
- unresolved or waiting-on-others threads;
- messages deliberately retained for follow-up;
- anything uncertain.

The cleanup authorization does not permit deleting, marking read, replying, forwarding, approving, rejecting, or changing Teams or Jira. Internal refreshes used to verify a completed action or advance between sources do not trigger cleanup. If the Inbox cannot be classified safely, leave it unchanged and continue with the active triage stage.

## Build the sets

Create exact identifier sets before moving anything:

- **Protect:** unread human mail that may need an answer, approvals, unresolved risks, retained business threads, waiting-on-others threads, and anything Michael explicitly says to keep.
- **Archive:** clear noise, completed threads, superseded duplicates, handled FYIs, and items Michael explicitly marks done.
- **Uncertain:** leave untouched and report for later review.

An instruction such as “keep X and archive the rest” authorizes only the resolved Inbox scope. Protect X by exact message ID rather than subject text alone.

## Execute safely

1. Re-resolve the actual Inbox and refresh it immediately before the move.
2. Recheck every archive candidate against the Protect set.
3. Archive in small, non-overlapping batches. Never delete.
4. Respect provider throttling. Wait for an explicit cooldown and retry the failed subset once; do not start a second overlapping cleanup.
5. Refresh the actual Inbox after processing.
6. Report verified archived, retained, uncertain, and failed counts.

Keep the cleanup report brief, then continue directly to the active triage stage.

Do not report “complete” from requested-operation counts. Completion means the live Inbox was verified after the moves.
