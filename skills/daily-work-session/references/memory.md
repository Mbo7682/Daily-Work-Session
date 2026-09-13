# Same-chat memory recap

## Schedule at daily start

At the start of each new daily work session, use the available scheduling capability to create one one-time task at 21:30 Europe/Copenhagen on the current Denmark date. Attach the task to the current daily chat so it returns with that chat's existing context. Do not create a standalone recap.

Before creating it, check whether this chat already has a recap for the same local date. Reuse the existing task and keep its identifier in conversation state. A `refresh`, reconnection, or repeated skill invocation must not create another recap.

If the session starts after 21:30, do not create a task in the past. Run the recap immediately when Michael closes the session, or report that no automated recap is scheduled.

If scheduling is unavailable or fails, follow [authentication.md](authentication.md) when the failure is access-related, continue the daily triage, and state the failure briefly. Do not claim the recap is protected.

## Recap prompt

Use this durable prompt for the in-chat task:

```text
Use $capture-memory to close today's Daily Work Session from this chat. Review the available chat context and save only durable confirmed decisions, commitments, owners, deadlines, project-status changes, reusable lessons, and unresolved open threads to Mbo7682/Michaels-memory. Deduplicate against canonical notes, update 50 Sessions/Open Threads.md when needed, and create or update 40 Daily/YYYY-MM-DD.md using the Denmark date and accurate source coverage. Do not run a reflection interview. Do not store copied Outlook, Teams, or Jira content, secrets, authentication material, or transient triage details. Keep inferred or uncertain candidates in 00 Inbox/ChatGPT.md. Report Saved, Inbox, Skipped, and Blocked. If nothing qualifies, make no write.
```

The scheduled invocation of `$capture-memory` authorizes only the memory writes governed by that skill and the vault's own rules. It does not authorize any Outlook, Teams, Jira, approval, or calendar action.

If GitHub access is unavailable during the unattended recap, do not start an interactive login. Use `$capture-memory`'s exact `VAULT WRITE` fallback in the chat and report that the repository was not updated.

## Manual close

If Michael says `wrap up`, `close session`, or an equivalent phrase before 21:30, run the same recap immediately. Cancel or pause the pending recap only when the scheduling capability supports doing so safely; otherwise let the later run deduplicate and make no duplicate writes.
