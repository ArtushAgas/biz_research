# Usage log
Token use of subagents per pipeline run, as reported by each agent's completion notice (the harness figure, input plus output). Orchestrator (main session) tokens are NOT visible and are not included, so real totals are higher. Tool uses are the agents' own tool calls.

## 2026-10-28 run 3: /daily-idea, 5 candidates, screen only (no deep dive)
| Stage | Agents | Tokens | Tool uses |
|---|---|---|---|
| Scout (screen mode) | 1 | 83,094 | 22 |
| Screeners | 5 | 153,817 (28,353 / 31,464 / 30,951 / 31,782 / 31,267) | 69 |
| **Total subagents** | 6 | **236,911** | **91** |

## 2026-10-28 run 4: /daily-idea, 10 candidates, deep dive on the top one (grounds maintenance, 57)
| Stage | Agents | Tokens | Tool uses |
|---|---|---|---|
| Scout (screen mode, 10 candidates) | 1 | 122,339 | 45 |
| Screeners | 10 | 322,536 (28.8k-41.9k each) | 144 |
| Stage 1 subtotal | 11 | 444,875 | 189 |
| Deep dive: competition-analyst | 1 | 180,699 | 90 |
| Deep dive: supply-sourcing | 1 | 161,255 | 102 |
| Deep dive: legal-czech | 1 | 204,365 | 75 |
| Deep dive: venture-judge | 1 | 63,003 | 17 |
| Stage 2 subtotal | 4 | 609,322 | 284 |
| **Total subagents** | 15 | **1,054,197** | **473** |

## Reading
- A screen-only run with 5 candidates cost about 237k subagent tokens; 10 candidates cost about 445k (roughly 1.9x); adding one deep dive cost about 609k more (about 1.4x the 10-candidate screen).
- Per screener about 29k-42k tokens; per deep-dive researcher 161k-204k; the judge about 63k.
- The two runs together: about 1.29M subagent tokens, plus the orchestrator.
- The earlier browser harvest and NEN research ran in the main session and are not itemised here.
