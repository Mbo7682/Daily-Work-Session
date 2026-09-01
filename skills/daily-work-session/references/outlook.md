# Outlook triage

## Collection

1. Resolve the folder whose type/path is the actual Inbox.
2. Page through the entire Inbox, not only today's mail and not a mailbox-wide search.
3. Include:
   - every unread Inbox message regardless of age;
   - read messages flagged, pinned, or clearly retained for follow-up;
   - unresolved business threads intentionally left in the Inbox.
4. If pin state is unavailable, say so briefly and use flags plus retained Inbox threads.
5. Fetch full message or thread content before making a recommendation when the preview is incomplete.

## Classification

- **Awaiting Michael:** direct question, approval, deadline, decision, signature, action, or incident ownership.
- **Waiting on others:** Michael has acted and another person owes the next step.
- **Useful update:** material context with no current action.
- **Noise:** marketing, newsletters, routine reports, superseded duplicates, and informational system messages without consequence.

Automated senders remain actionable when they represent approval requests, access expiry, failed flows, security findings, depleted capacity, deployment gates, expiring certificates, or service suspension.

## Dedupe and threads

- Group duplicate notifications by underlying action, environment, deployment, invoice, or issue.
- Prefer the newest complete message in a thread, but retain older content when it changes the decision.
- Do not interpret `read` as `handled`. A read message deliberately retained in the Inbox remains a follow-up candidate.

## Presentation

- Lead with the question or required action.
- Include sender, concrete dates, amounts, deadlines, material risk, and the relevant Inbox deeplink.
- When listing an approval, include its direct action link. If unavailable, include the correct approval application link.
- Keep facts separate from inference when the message does not confirm ownership or legitimacy.

