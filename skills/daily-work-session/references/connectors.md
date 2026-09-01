# Connected services

Discover available tools by capability. Tool names and connector implementations may differ between sessions.

## Required capabilities

- **Outlook:** resolve the actual Inbox folder; page through messages; fetch full messages and threads; create Inbox deeplinks; reply, forward, archive, and inspect flags only after authorization.
- **Teams:** list recent chats; inspect direct messages and mentions; resolve participants; send only after authorization.
- **Jira:** identify the current user and cloud/site; run JQL; fetch issues; create or edit issues only after authorization.

## Connector rules

- Prefer connected apps or MCP tools for provider resources. Do not replace a connector with browser automation merely because a resource has a URL.
- Never embed access tokens, API keys, tenant secrets, or message-specific authentication links in the repository.
- If a required source is unavailable, complete the other sources and name the missing capability precisely. Do not pretend the unavailable source is clean.
- Treat transient throttling as recoverable: wait for the stated cooldown, reduce page size or request count, and retry once without overlapping operations.
- Do not use mailbox-wide search as a substitute for resolving the Inbox folder.

## Identity and links

- Resolve ambiguous names from the relevant directory and communication history before sending.
- Preserve stable source identifiers in session state: Outlook message and conversation IDs, Teams chat/message IDs, and Jira issue keys.
- Provide direct source links for actionable items. Approval summaries must include the specific action link or the correct approval app link.

