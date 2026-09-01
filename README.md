# Daily Work Session

Reusable Codex plugin for Michael's daily work triage across Outlook, Teams, and Jira.

The plugin starts each day with a read-only refresh, merges the three sources into one concise priority queue, and keeps the chat usable as an item-by-item work session. It also defines the safety rules for replies, approvals, recipient resolution, and Inbox housecleaning that were learned through real use.

## Structure

```text
.
|-- .codex-plugin/plugin.json
|-- AGENTS.md
`-- skills/daily-work-session/
    |-- SKILL.md
    |-- agents/openai.yaml
    `-- references/
        |-- automation.md
        |-- connectors.md
        |-- housecleaning.md
        |-- interaction.md
        |-- jira.md
        |-- outlook.md
        `-- teams.md
```

## Design

- **Plugin:** packages the workflow for installation and discovery.
- **Skill:** routes morning triage, refreshes, `next`, actions, and housecleaning.
- **Rules:** `AGENTS.md` and the skill invariants protect live communication and data.
- **References:** source-specific procedures are loaded only when needed.
- **Connectors:** Outlook, Teams, and Jira are capabilities, not embedded credentials. Never commit secrets or tenant-specific tokens.

## Primary invocation

```text
Use $daily-work-session to start Michael's daily work triage. Refresh the actual Outlook Inbox across all unread dates plus retained follow-up mail, review Teams direct chats and mentions, and review Jira work that is assigned, overdue, blocked, or recently updated. Merge the results into a concise priority queue, make no state changes, present the first meaningful item, and keep the thread ready for item-by-item work throughout the day.
```

