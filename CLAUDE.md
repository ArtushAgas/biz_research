# Prague Business-Idea Researcher

Daily pipeline that researches ONE business idea for Prague/Czechia and ends with a scored verdict. Run it with `/daily-idea`.

## Ground rules (apply to every agent)
- Read `profile.md` first: budget ceiling (100k EUR, lower is better), part-time owner, two existing s.r.o. (one VAT payer, one not), veto list.
- Report language is English. Search in Czech, English and the language of the source market (PL, HU, DE, FR, ...). Include Czech search terms and original-language names in findings.
- Every figure is tagged **[sourced: URL, date]** or **[estimate: assumption]**. Never present an estimate as a fact. "Unknown / could not verify" is an acceptable answer and is better than a guess.
- Prefer primary sources: CZSO, Eurostat, ARES, Justice.cz, official statistics of other countries, laws (zakonyprolidi.cz / e-Sbírka), supplier price lists, live shop prices. Then reputable press and industry reports. Avoid SEO listicles unless nothing else exists.
- Prices: record currency, VAT included or excluded, date seen, and URL. Convert to EUR and CZK at a stated rate.
- The competition, supply and legal agents work independently from the same idea brief and must not read each other's reports.
- Legal findings are a research summary, not legal advice. Regulated goods (tobacco, CBD, construction products, vehicles) must be flagged for lawyer/accountant verification.
- Markets: prioritise Czech and EU sources, but use global ones too. A business that does not exist in Czechia is not a bad idea by default; state why it is probably absent and judge that reason.
- Idea sourcing: `/harvest` fills `opportunities.md` (complaints, needs, working models abroad, idea publications, owner ideas) and `sources.md` (which sources were useful). The scout builds daily candidates from that backlog.
- Public contracts (B2G): for EVERY idea, scouted, screened or deep-dived, also evaluate the public-contract channel (NEN, VVZ, TED, Registr smluv): does the public sector buy this, how much, how often, who wins, and can a small part-time owner bid. Follow the `public-contract-lens` skill; "not applicable" and "not verified" are acceptable answers, a guess is not. NEN is also an idea source: skim it for what the state buys repeatedly (see `browser-harvest-playbook`).
- Two-stage flow: `/daily-idea` screens 5 candidates (scout in screen mode + 5 parallel `idea-screener` agents), then runs `/deep-dive` (competition, supply, legal, judge) only on a candidate that clears the gate. See `.claude/commands/daily-idea.md`.
- Browser harvest: `/harvest-browser` uses the owner's Chrome extension for sites that block fetching; recipes, URL patterns and known failures are in `.claude/skills/browser-harvest-playbook/SKILL.md`. NEN (public tenders) is a priority source.
- Files: full reports in `reports/YYYY-MM-DD-<slug>.md`; one line per deep-dived idea in `ideas-log.md`; one line per screened candidate in `screened-ideas.md`; artifact URLs (including the Idea Radar `index`) in `state/artifacts.json`.
- Cloud runs: some hosts may be blocked by the sandbox; say so in the report instead of guessing, and rely on primary sources when reachable.
