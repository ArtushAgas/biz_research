---
description: Run the deep research pipeline (competition, supply, legal, judge) on ONE idea brief and publish the scored report
argument-hint: <slug or idea brief to deep-dive>
---

Deep-dive one idea. Idea or brief: $ARGUMENTS

The idea brief is the text above, or the candidate with that slug from today's screening. Get today's date.

1. **Independent research, in parallel.** In a single message, invoke `competition-analyst`, `supply-sourcing` and `legal-czech`. Give each ONLY the full idea brief (legal-czech also reads `profile.md`). Do not pass any agent another agent's output. Include the screening findings (prices, margin anchor, flags) in the brief as "screen notes" so they are not rediscovered from scratch.
2. **Judge.** Invoke `venture-judge` with the brief and the full text of all three reports. It returns the scored decision report, plus a reshaped-variant score when material. Ask it to resolve disagreements between reports with primary sources.
3. **Persist.**
   - Write `reports/<YYYY-MM-DD>-<slug>.md`.
   - Append one line to `ideas-log.md`: `date | slug | category | score (variant) | verdict | capex EUR | report path`.
4. **Publish.** Load the `artifact-design` skill, build a private HTML artifact from the report (verdict banner, score breakdown, tables, 30-day validation plan, sources), publish it, and record the URL in `state/artifacts.json` under `daily`.
5. Return: idea, verdict, score, capital, hours/week, the 3 main reasons, the artifact link and the data gaps to close first.
