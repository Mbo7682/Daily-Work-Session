# Session interaction

## Source sequence

After verified Inbox cleanup, build and work the queue in stages:

1. Teams direct chats, direct questions in group chats, and mentions;
2. Outlook Inbox mail retained after cleanup;
3. Jira details only when a surfaced Teams or Outlook item points to Jira work.

Do not delay the Teams stage while building a complete cross-service overview. When Teams has no further meaningful items, say so briefly and move directly to Outlook. Jira is supporting context, not its own daily-triage stage.

Within each source, prefer this order:

1. urgent operational or security risk;
2. action or approval due today;
3. human question awaiting Michael;
4. commercial or contractual decision;
5. blocked or overdue work;
6. retained follow-up and useful updates.

State cleanup results and the actual Teams coverage boundary briefly, then present the first meaningful Teams item. When Outlook begins, confirm that the actual Inbox was checked across all unread dates plus retained follow-up mail.

## One-item loop

For each item provide:

- who or what it concerns;
- the question, decision, or action;
- only the facts that affect the choice;
- a recommendation;
- a direct source/action link when available.

Interpret common responses:

- **next:** mark the current item handled for this session and show the next unresolved item.
- **done / sorted / handled manually:** refresh the relevant source, then advance.
- **skip / leave / wait:** retain the item as deferred and advance without changing it.
- **draft / reply / forward / message:** prepare or perform only the requested communication and resolve recipients first.
- **refresh:** first run the narrow verified Inbox cleanup, then rebuild the relevant live queue while preserving the session's handled and deferred identifiers.

When advancing between sources, refresh the destination source without treating that automatic transition as Michael's `refresh` command. When Michael asks to refresh, Inbox cleanup is implicit.

If a Teams or Outlook item names a Jira issue, project, sprint, or Jira-managed commitment, fetch only the Jira context needed for that item. Return to the current source queue after the item is handled or deferred.

## Communication rules

- Present the actual question rather than a generic summary.
- Keep messages concise and natural; avoid adding context the recipient already has from the thread.
- Match the recipient's established language or Michael's explicit direction.
- Never add a manual email signature.
- After sending or editing, report the exact action and recipient. Do not claim success until the tool confirms it.
