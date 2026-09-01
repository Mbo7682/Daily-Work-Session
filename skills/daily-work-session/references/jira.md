# Jira triage

## Scope

Resolve the authenticated Jira user and review open work that is:

- assigned to Michael and overdue;
- assigned to Michael and recently updated;
- assigned to Michael and blocked;
- explicitly awaiting Michael's decision, review, or approval.

Use concrete current work rather than dumping the historical backlog. Treat generic project-template reminders as low priority unless recent context makes them real deliverables.

## Suggested queries

Adapt field and status names to the site:

```text
assignee = currentUser() AND statusCategory != Done
AND (due <= now() OR updated >= -7d)
ORDER BY priority DESC, due ASC, updated DESC
```

```text
assignee = currentUser() AND status = Blocked
AND statusCategory != Done
ORDER BY updated DESC
```

If the API returns old issues because they have an ancient due date, rank by actual current relevance and report the stale backlog separately only when it needs cleanup.

## Presentation

Include issue key, summary, status, assignee, due date, last meaningful update, and a direct Jira link. Explain the decision or next action; do not merely repeat Jira's status.

