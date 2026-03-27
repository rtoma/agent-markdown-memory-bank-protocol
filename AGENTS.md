# Agents.md

This file should help you / the agent to focus on the work and understand the purpose of this project.

# CRITICAL Memory bank protocol CRITICAL 

You must maintain a "memory bank" in the `.memory-bank/` directory. This is your source of truth.

1. before starting any task
- read `product-context.md` to understand the goal
- read `active-context.md` to see the current focus
- read `system-architecture.md` to ensure patterns are followed

2. during the task
- if you make architectural changes, you MUST update the system-architecture.md immediately

3. after completing the task/session
- add to the `progress.md` what was accomplished, use `## <current timestamp, YYYY-MM-DD HH:MM format>` as header, insert immediately below the `# Journal` header.
- **IMPORTANT**: Execute `date '+%Y-%m-%d %H:%M'` in terminal to get accurate timestamp instead of guessing
- update `active-context.md` with the next logical steps for the next session
- summarize these updates to the user

⚠️ MANDATORY COMPLETION CHECKLIST ⚠️
Before ending ANY response after making code changes, you MUST:
[ ] Append changes to `.memory-bank/progress.md` with current timestamp
[ ] Update `.memory-bank/active-context.md` if focus/architecture changed
[ ] Confirm to user that memory bank has been updated

If you skip this checklist, the session is INCOMPLETE.

# CRITICAL Todo workflow CRITICAL

If developer suggest to pick up the next todo item, check the 'Next Steps (unsorted)' section in `.memory-bank/active-context.md` file and recommend top 3 of best items to pick up.

