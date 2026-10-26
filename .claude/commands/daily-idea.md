---
description: Run the daily Prague business-idea research pipeline (scout, competition, supply, legal, judge) and publish the report
argument-hint: [optional category or theme override]
---

Run today's business-idea pipeline. Optional override from the user: $ARGUMENTS

1. **Prepare.** Read `profile.md` and `ideas-log.md`. Choose today's category by rotation: count existing lines in `ideas-log.md`, take that number modulo 5 over `digital-saas, b2b-services, ecommerce-import, local-physical, trade-regulated`. A category or theme in `$ARGUMENTS` or the profile's "Weekly theme" overrides rotation. Get today's date.

2. **Scout.** Invoke the `idea-scout` agent with the category and the instruction to read `profile.md` and `ideas-log.md`. It returns the idea brief. If the brief violates the budget, part-time or veto constraints, send it back once.

3. **Independent research, in parallel.** In a single message, invoke `competition-analyst`, `supply-sourcing` and `legal-czech`. Give each ONLY the full idea brief (legal-czech also reads `profile.md`). Do not pass any agent another agent's output.

4. **Judge.** Invoke `venture-judge` with the idea brief and the full text of all three reports. It returns the scored decision report.

5. **Persist.**
   - Write the report to `reports/<YYYY-MM-DD>-<slug>.md`.
   - Append one line to `ideas-log.md`: `date | slug | category | score | verdict | capex EUR | report path`.

6. **Publish.** Load the `artifact-design` skill, build a private HTML artifact from the report (verdict banner, score breakdown, tables, sources), and publish it with the Artifact tool. Then create or update the index artifact (all ideas, sortable by score/category) at the URL in `state/artifacts.json`, and record URLs there. If artifact publishing is unavailable in this environment, say so and leave the report file as the deliverable.

7. **Commit** the new files if this is a git repository.

8. **Reply** with: idea name, verdict, score, capital needed, hours/week, the 3 main reasons, the artifact link, and any data gaps the owner should check first.
