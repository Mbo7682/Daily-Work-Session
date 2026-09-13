# Authentication recovery

Use this recovery flow only after a required capability fails because access is missing, disconnected, expired, or insufficient. Do not interrupt a healthy run with proactive authentication checks beyond the smallest read-only capability test.

## Recovery order

1. Identify the failed service, attempted capability, and failure type. Separate authentication failure from missing plugin, missing permission, provider outage, throttling, and unsupported capability.
2. If the relevant plugin or connector is installed, ask Michael to use its native **Connect** or **Reconnect** flow. Resume only after a harmless read-only call confirms access.
3. If no suitable plugin is installed, use plugin management when available to find and suggest the exact provider integration. Do not claim it is installed or connected until verified.
4. If the active environment supports provider sign-in or device login, start it when Michael is present and let him complete authentication in the provider-owned page.
5. If the integration requires a PAT or similar secret, use its secure configuration field, a protected environment variable, or another non-persisted runtime input.
6. After recovery, retry the smallest read-only operation first, then resume the failed source without repeating completed sources or external mutations.

Keep reusable credentials out of persisted chat transcripts, task prompts, repository files, and logs.

Request only the permissions required for the workflow. If authentication succeeds but authorization is insufficient, name the missing capability and ask for the narrowest additional scope or administrator action.

## Platform fallbacks

### Outlook and Teams

1. Use the available Microsoft 365, Outlook, or Teams connected capability.
2. On disconnect or expiry, use its Connect/Reconnect flow and Microsoft Entra sign-in.
3. Where an approved local Microsoft client supports device login, Michael may complete that flow in Microsoft's browser page.
4. Do not substitute mailbox-wide search, copied exports, or guessed Teams coverage for a failed connector.

Outlook and Teams may recover independently. Failure of one must not suppress the other.

### Jira

1. Use the connected Jira or Atlassian capability.
2. Reconnect through the provider flow. Reuse Microsoft work sign-in only when Jira itself offers it.
3. If a PAT is required by the Jira integration, use its secure configuration or runtime-secret input.
4. Browser use requires Michael's explicit site intent or an approved connector handoff. Pause for provider sign-in when needed.

### GitHub

1. Use the connected GitHub integration with read/write access to `Mbo7682/Michaels-memory`.
2. Reconnect the GitHub integration when access is expired or missing.
3. In a local interactive environment, `gh auth login` with GitHub's browser/device flow is an acceptable fallback.
4. If using a PAT through secure configuration or runtime input, give it no broader repository scope than required.

During an unattended 21:30 recap, do not launch interactive recovery. Follow `$capture-memory`'s `VAULT WRITE` fallback and report that GitHub was not updated.

### Automations

Use the native scheduling capability. If it is unavailable because of workspace policy, plan eligibility, or missing permission, name that blocker. Do not substitute a hidden operating-system scheduler or create a standalone task when the required behavior is a same-chat recap.

## Failure report

State only:

- the unavailable service and capability;
- whether the cause is known;
- the exact Connect, Reconnect, device-login, secure-secret, or administrator action required;
- which sources were still completed;
- whether a minimal read-only retry succeeded.
