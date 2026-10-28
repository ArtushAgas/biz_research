---
description: Harvest opportunity signals (complaints, needs, working models abroad, idea publications) into the opportunity backlog and source register
argument-hint: [full | weekly]  (default weekly)
---

Harvest opportunity signals. Mode: $ARGUMENTS (default `weekly`).

1. Read `CLAUDE.md`, `profile.md`, `opportunities.md`, `sources.md`, `ideas-log.md`, `screened-ideas.md`. Get today's date.
2. Choose source groups (see `.claude/agents/pain-miner.md`):
   - `full`: all five groups A, B, C, D, E.
   - `weekly`: three groups, rotating so each group runs at least every two weeks; favour groups whose signals produced the highest screen scores in `sources.md`.
3. In a single message invoke one `pain-miner` agent per chosen group, in parallel, each with its group letter and the mode.
4. Merge results:
   - Drop duplicates of existing backlog lines and of ideas already in `ideas-log.md` / `screened-ideas.md`. Merge near-duplicates into one line and raise its strength when several independent sources report the same pain.
   - Give each new line the next id for its group (A-001, B-001, ...), status `new`, and append to `opportunities.md` in the backlog line format.
   - Add or update sources in `sources.md` (reachable, usefulness, signals found).
5. Commit and push the changed files (if main is refused, push to `harvest/<date>`).
6. Reply with: signals added per group, the 10 strongest new signals, the most useful and the blocked sources, and anything that failed.
