# Inbox housecleaning

Housecleaning is a live mailbox mutation and requires explicit authorization.

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

Do not report “complete” from requested-operation counts. Completion means the live Inbox was verified after the moves.

