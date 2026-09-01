# Scheduled workday start

The scheduled run should open a fresh daily chat and invoke the skill read-only. Use the current local weekday and date in the title rather than copying a stale date from the schedule definition.

Recommended start prompt:

```text
Use $daily-work-session to start Michael's daily work triage. Refresh the actual Outlook Inbox across all unread dates plus retained follow-up mail, review Teams direct chats and mentions, and review Jira work that is assigned, overdue, blocked, or recently updated. Merge the results into a concise priority queue, make no state changes, present the first meaningful item, and keep the thread ready for item-by-item work throughout the day.
```

The scheduled run must:

- use the live local date;
- complete partial source coverage if one connector is temporarily unavailable;
- make no mailbox, Teams, Jira, approval, or calendar changes;
- keep the created chat available for `next`, drafting, actions, refreshes, and later housecleaning;
- avoid creating duplicate schedules from inside the run.

