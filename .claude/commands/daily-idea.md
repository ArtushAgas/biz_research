---
description: Run the daily two-stage Prague business-idea pipeline (screen 5 candidates, deep-dive the best if it clears the bar), update the idea radar and notify
argument-hint: [optional category/theme override, or "deep: <slug>" to deep-dive a logged candidate]
---

Run today's two-stage pipeline. Optional override from the user: $ARGUMENTS

## Stage 0: prepare
Read `CLAUDE.md`, `profile.md`, `ideas-log.md`, `screened-ideas.md`. Get today's date. Choose today's category by rotation over `digital-saas, b2b-services, ecommerce-import, local-physical, trade-regulated`: count the DISTINCT dates in `screened-ideas.md`, take that number modulo 5. A category or theme in `$ARGUMENTS` or the profile's "Weekly theme" overrides rotation. If `$ARGUMENTS` starts with "deep:", skip Stage 1 and go straight to Stage 2 for that logged candidate.

## Stage 1: screen (cheap, broad)
1. Invoke `idea-scout` in **screen mode** with the category. It returns 5 candidate briefs.
2. In a single message invoke 5 `idea-screener` agents in parallel, one per candidate, each given ONLY its own candidate brief.
3. Rank candidates by preliminary score. Append one line per candidate to `screened-ideas.md`: `date | slug | category | screen score | outcome | main reason`. Outcome is `deep-dive` for the winner if it goes on, otherwise `dropped`.

## Decision gate
Run Stage 2 on the top candidate if ANY of these holds:
- its screen score is 55 or higher;
- no deep dive was logged in `ideas-log.md` within the last 7 days (weekly deep dive: take the top candidate even if it scored lower, and say so in the notification);
- the user forced it with "deep:".
Otherwise skip Stage 2 and say why.

## Stage 2: deep dive
Follow `.claude/commands/deep-dive.md` for the chosen candidate (brief plus screen notes). It writes the report, the log line and the artifact.

## Stage 3: radar and notify
1. Regenerate the **Idea Radar** index artifact: one private HTML page listing every idea in `ideas-log.md` (deep-dived: score, verdict, capital, artifact link) and `screened-ideas.md` (screened: score, outcome, main reason), sortable by score and category, newest first, with today's screen results highlighted. Load the `artifact-design` skill first. Publish it: if `state/artifacts.json` has an `index` URL, publish to that URL; otherwise publish new and record the URL under `index`.
2. Send one PushNotification (plain text, under 200 characters). Deep-dive day: idea name, verdict, score, link. Screen-only day: "Screened 5 <category> ideas; best <name> <score>, no deep dive" and the Idea Radar link. If something failed, say what failed.
3. Commit all changed files; push to origin main (if main is refused, push to `daily/<date>` and say so).

## Final reply
State the category, the 5 candidates with screen scores, whether Stage 2 ran and why, the artifact links, anything that failed, and data gaps worth closing.
