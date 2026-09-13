# Daily Work Session

Reusable Codex plugin for Michael's daily work session across Outlook, Teams, and Jira.

The plugin starts each day by scheduling a 21:30 Europe/Copenhagen memory recap inside the daily chat and archiving confirmed Outlook Inbox noise. It then catches up Teams without a current-date filter before reviewing every unread Inbox message across all dates plus retained email. An explicit `refresh` repeats the safe cleanup before refreshing the active queue. Jira is queried only when a surfaced item needs current context.

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
        |-- authentication.md
        |-- connectors.md
        |-- housecleaning.md
        |-- interaction.md
        |-- jira.md
        |-- memory.md
        |-- outlook.md
        `-- teams.md
```

## Design

- **Plugin:** packages the workflow for installation and discovery.
- **Skill:** routes recap scheduling, startup cleanup, Teams-first triage, email review, contextual Jira lookup, refreshes, and item actions.
- **Rules:** `AGENTS.md` and the skill invariants protect live communication and data.
- **References:** source-specific procedures are loaded only when needed.
- **Connectors:** Outlook, Teams, Jira, GitHub, and Automations are capabilities, not embedded credentials. Failed integrations use provider reconnection, device login, or secure runtime configuration.

## Primary invocation

```text
Use $daily-work-session to start Michael's daily work session. Schedule one recap for 21:30 Europe/Copenhagen inside this chat using $capture-memory, without duplicating an existing task. Then clean the actual Outlook Inbox by archiving only confirmed noise. Triage all accessible unreviewed Teams work without a current-date filter, using unread or last-read markers plus at least a seven-day safety scan. Review every unread Inbox message regardless of date plus retained follow-up mail, and query Jira only when a surfaced item needs current context. Present one meaningful item at a time and report any source-history limit precisely.
```
