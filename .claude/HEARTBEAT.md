# Heartbeat — Session Startup

Run this automatically when the user opens a session without a specific task or ask. No prompt needed.

## Step 0 — Check if setup is needed

Read `context/me.md`. If the name field is empty or still contains `[Your Name]`, stop and run the setup skill:

> "looks like this is a fresh install. let's get you set up — it takes about 5 minutes."

Then invoke the `setup` skill. Do not proceed with the briefing below until setup is complete.

---

## Startup Sequence (after setup)

1. **PRIORITIES** — Read `context/current-priorities.md`. Identify P0 items. Flag any that are overdue or have no recent update.

2. **MEMORY** — Read the most recent dated file in `memory/` (if any). Note what was in progress or left pending.

3. **DECISIONS** — Scan the last 3 entries in `decisions/log.md`. Note anything that affects current work.

4. **CONTENT** — Check today's date against the posting cadence in `context/work.md`. Flag if a post is due today or tomorrow and hasn't been drafted.

5. **SURFACE** — Give a 5-line briefing max:
   - Sprint status (1 line: what's on fire, what's on track)
   - Content due (1 line)
   - Overdue P0s or blockers (1 line, or "none")
   - What was last worked on (1 line from memory/)
   - One suggested next action (1 line)

## Rules

- Do NOT dump everything. Summarize ruthlessly.
- Flag only items that need attention or a decision.
- If nothing is overdue or blocked, say so in one line. Don't pad.
- After the briefing, wait for direction.
