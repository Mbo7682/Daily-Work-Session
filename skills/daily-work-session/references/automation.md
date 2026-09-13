# Scheduled workday start

The scheduled run should open a fresh daily chat and invoke the skill. Use the current local weekday and date in the title rather than copying a stale date from the schedule definition.

Recommended start prompt:

```text
Use $daily-work-session to start Michael's daily work session. First create or confirm one one-time recap for 21:30 Europe/Copenhagen inside this chat using $capture-memory, without duplicating an existing task. Then clean the actual Outlook Inbox by archiving only confirmed noise under the skill's startup authorization, verify the result, and protect all unresolved or uncertain mail across every received date. Triage all accessible unreviewed Teams direct chats, relevant group-chat requests, and mentions without a current-date filter, using unread or last-read markers plus at least a seven-day safety scan. Then review every unread Inbox message regardless of date plus retained follow-up mail. Query Jira only when a surfaced Teams or Outlook item needs Jira context. Present one meaningful item at a time and report any source-history limit precisely.
```

The scheduled run must:

- use the live local date;
- never limit Outlook or Teams collection to that date;
- create or confirm the one-time 21:30 Europe/Copenhagen recap inside the newly created daily chat using [memory.md](memory.md);
- complete partial source coverage if one connector is temporarily unavailable;
- archive only confirmed Outlook Inbox noise and verify the result;
- make no other mailbox, Teams, Jira, approval, or calendar changes;
- continue to Teams if cleanup is unavailable or cannot classify mail safely, and report the limitation;
- keep the created chat available for `next`, drafting, actions, refreshes, and later scoped housecleaning;
- avoid creating duplicate schedules from inside the run.

When authentication requires interactive input, an unattended scheduled run should name the required connection action instead of waiting. Continue every healthy source and leave the failed source ready for a minimal read-only retry after Michael reconnects it.

The no-duplicate rule permits the single dated recap task defined in `memory.md`. It prohibits creating another 09:00 workday-start schedule or multiple recap tasks for the same chat and date.
