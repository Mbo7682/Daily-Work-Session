---
name: daily-work-triage
description: "Compatibility launcher for Michael's daily triage. Use for morning updates, daily triage, Inbox review, queue refreshes, 'next' requests, and housecleaning; it loads the current Daily Work Session workflow from GitHub before starting a new session."
---

# Daily Work Triage Launcher

Launch the maintained Daily Work Session workflow from `Mbo7682/Daily-Work-Session` rather than running a separate embedded triage process.

## New session

Before taking any Outlook, Teams, Jira, GitHub, or automation action:

1. Resolve the current commit SHA of the repository's `main` branch using the connected GitHub read capability. If a clean local checkout is available, `git fetch origin main` and resolve `origin/main` is also acceptable.
2. From that exact commit, read `AGENTS.md` and `skills/daily-work-session/SKILL.md` completely.
3. Load referenced files from `skills/daily-work-session/references/` only when routed there by the skill, always from the same resolved commit.
4. State the loaded short commit SHA in the first progress update, then execute the user's start or refresh request under the loaded workflow.

Pin the resolved commit for the rest of the chat. Requests such as `next`, `done`, drafting, sending, or source refreshes continue the already loaded daily session and must not fetch a different revision halfway through it.

## Retrieval failure

If `main` cannot be retrieved, do not silently claim that the current workflow is loaded. Use the packaged `daily-work-session` skill as a fallback when it is available, identify it as the bundled fallback, and continue only if its required connectors and safety rules can be loaded. If neither source is available, report the blocker before accessing or changing live services.

Fetching instructions grants no additional authority over connected services. Mutations remain limited by the loaded repository rules and Michael's request.
