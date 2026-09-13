# Contextual Jira lookup

## Scope

During normal daily triage, do not run a standalone Jira backlog pass. Query Jira only when a surfaced Teams or Outlook item:

- names an issue key, project, sprint, epic, or board;
- refers to a commitment that is managed in Jira;
- requires current Jira status, ownership, due date, or recent updates to make a decision.

Fetch only the context needed for that item, then return to the Teams or Outlook queue.

If Michael explicitly requests a Jira review, resolve the authenticated Jira user and review open work that is:

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

## Browser authentication

Use the connected Jira or Atlassian integration first. If it is disconnected or expired, follow [authentication.md](authentication.md).

Use browser authentication only when Michael explicitly asks to use the Jira site or when the approved connector flow opens it. Reuse an existing Microsoft work session when Jira offers Microsoft sign-in. If interactive sign-in is required, pause for Michael to complete it in the provider-owned page.

## Presentation

Include issue key, summary, status, assignee, due date, last meaningful update, and a direct Jira link. Explain the decision or next action; do not merely repeat Jira's status.
