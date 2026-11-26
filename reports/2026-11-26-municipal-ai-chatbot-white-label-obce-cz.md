# Decision report: municipal-ai-chatbot-white-label-obce-cz (2026-11-26)

**Verdict: Pass as briefed (57/100, Medium-Low confidence). Reshaped partner/mikroregion variant about 62 = Investigate, only if a partner is validated.**
Capex about EUR 6k cash (range 3-8k; about 146k CZK at 24.3 CZK/EUR [estimate]); build is 120-200 owner hours. Hours/week: ~15 build quarter, then ~10-12.

## Idea
Annual-subscription Czech AI FAQ assistant (RAG over an obec's website, úřední deska and PDFs) for small obce, městské části and schools, plus an AI Act/GDPR compliance pack. Screen score 58 -> final 57.

## Why (5 lines)
1. Technically easy, 90%+ software margin, cheap to start; therefore already filling up.
2. Demand real but cheap: 36-56k CZK ex VAT/yr in small-town contracts read.
3. MULTIMA AI (MAICA/Chetty) has tiers and 9+ contracts 2025-26; Citymind, Galileo and web vendors own the obec relationship; newcomer has no references.
4. Constraint is distribution: ~11-16 obce at 36-42k needed for 25k CZK/month; each sale 5-10 h with slow municipal cycles.
5. Profile fits build and capital, not a cold sales grind; a partner channel could fix this but none is verified.

## Score
| Criterion (weight) | Score /10 | Points |
|---|---|---|
| Demand and market size (20) | 5 | 10.0 |
| Unit economics (20) | 5 | 10.0 |
| Competition and barriers (15) | 3 | 4.5 |
| Capital (10) | 9 | 9.0 |
| Part-time feasibility (10) | 6 | 6.0 |
| Regulatory burden (10) | 6 | 6.0 |
| Supply (5) | 4 | 4.0 |
| Scalability (5) | 6 | 3.0 |
| Fit with s.r.o. (5) | 8 | 4.0 |
| **Total** | | **56.5 -> 57 (Pass, below 60)** |

## Price evidence (judge-verified)
| Source | Price | Notes |
|---|---|---|
| Mokrá-Horákov (CT24, 2 Mar 2025) | ~50,000 CZK/yr incl. earlier development costs | mayor quote verified; vendor not named; n=1, 20 months old [sourced: https://ct24.ceskatelevize.cz/clanek/domaci/ai-pomaha-casti-obci-s-uredni-rutinou-i-komunikaci-358513, 2026-11-26] |
| Obec Bílá (CT24) | 20,000 one-time + ~3,000/month | quote under negotiation (~56k yr1, 36k/yr after) |
| Holice (MULTIMA) | 47,916 incl. VAT (~39.6k ex), 2025-06 | term unknown |
| Kutná Hora MAICA "Město 30 000" | 68,244 incl. VAT (~56.4k ex), 2026-07 | term unknown |
| Hodonín Chetty | 136,488 incl. VAT, 2025-04 | |
| Tišnov / Zábřeh | 239,580 incl. VAT each, 2025 | |
| Česká Lípa / Liberecký kraj / FN Ostrava | 377,520 / 476,256 / 604,999 incl. VAT | |
Source: https://www.hlidacstatu.cz/Hledat?q=MULTIMA%20AI%20chatbot (Registr smluv maximum values, fetched 2026-11-26). Contract terms (1 vs multi-year) unknown, so "50k/yr is at or above incumbent" cannot be confirmed. "MULTIMA 9 of 9" is a search-selection artefact. Vendor of Mokrá-Horákov conflicts between reports (Citymind/Tessa) and is unresolved.

## Competition and public-contract channel
- MULTIMA: strong (references, population tiers, SK small-obec edition). Citymind: medium (Prague 6, Mikulov, Mokrá-Horákov; individual quotes). Galileo/web vendors: biggest channel threat. sitmpcz/ai-chatbot is only a client for the Plzeň backend. Barrier: technical low, commercial high.
- B2G: every customer is public; route is small direct awards (ZMR under ZZVZ §27, up to 3M CZK services, no tender duty below, §6 principles; 2026 thresholds per Reg. 541/2025 not verified from primary source). Registr smluv: contracts >50k CZK ex VAT published and effective only after publication. Above-threshold tenders (Brno TED 303416-2026 ~10M CZK, MPO 448670-2026 4.144M CZK) unreachable for a newcomer. NEN/TED not reachable directly: not verified.

## Supply
Mistral Small $0.10/$0.30 per 1M tokens [sourced: https://developer.puter.com/tutorials/mistral-api-pricing/, 2026-11-26]; running cost per obec 85/270/740 CZK/month [estimate]; fixed ~50k CZK/yr [estimate]; build own (outsourcing 100-300k CZK). Supply risk low-medium.

## Legal (research summary, not legal advice; verify with lawyer/accountant)
AI Act Art.50 applies from 2 Aug 2026; Digital Omnibus Reg. 2026/1744 moved Annex III to 2 Dec 2027; FAQ bot probably not high-risk. GDPR: obec controller, owner processor, Art.28 DPA, EU hosting. NIS2 act 264/2025 probably not applicable to small obce; accessibility act 99/2019 probably applies to widget. Use the VAT-payer s.r.o. Costs [estimate]: lawyer EUR 1-3k, DPA 0.5-1.5k, insurance 0.5-1.5k/yr, accessibility audit 0.5-2k.

## First-year sketch (ex VAT, pre-tax, owner time not costed)
| | Low | Base | High |
|---|---|---|---|
| Obce by month 12 | 5 | 10 | 16 |
| Price/obec/yr | 36k | 42k | 48k |
| Billing yr1 | 180k | 420k | 768k |
| Capex | ~100k (EUR 4k) | ~146k (EUR 6k) | ~195k (EUR 8k) |
| Run-rate profit/month at m12 | ~9.5k | ~28k | ~55k |
| Payback | >30 months | ~15 months | ~9 months |
Target 25k CZK/month net needs ~11-12 obce at 42k or 16 at 30k. Most sensitive: obce signed per month (3% conversion = ~330 contacts for 10), then real annual price, then churn/support.

## Top risks
Distribution/no references; price compression (micro-obec will not pay 50k); wrong-answer liability; slow annual-budget sales cycle (first realistic sales Q1-Q2 2027); commoditisation by free plugins and big-tech widgets.

## What would change the verdict
3+ paid pilots/LOIs at 36k+ from obce <3,000 inhabitants in 30 days; a written reseller partner (non-Galileo web vendor, SMO or mikroregion) at 18-25k wholesale; Holice/Kutná Hora PDFs confirming 1-year term at 40-56k; open subsidy covering chatbots (Vysočina ICT grant ~33-53k eligibility unverified).

## 30-day validation plan (<EUR 300)
- Days 1-5: pull all chatbot Registr smluv via Hlídač (chatbot, virtuální asistent, AI asistent); read Holice and Kutná Hora PDFs for term/scope; find non-MULTIMA winners.
- Days 3-10: 1-day demo on 3 target obce websites (Mistral EU), 2-minute video, one-page Art.50/GDPR pack.
- Days 8-25: contact 100 obce <3,000 inhabitants; offer 3-month free pilot then 30-36k/yr; target 5 calls, 2 LOIs, 1 paid pre-order.
- Days 10-25: talk to 2-3 web vendors, one SMO/mikroregion body, Svaz měst a obcí about resale and subsidies.
- Day 30 kill rule: <2 LOIs from 100 obce and no partner = Pass; 2+ LOIs at 30k+ or a partner commitment = paid pilot and lawyer check.

## Reshaped variant (~62, Investigate if partner exists)
One contract for 10-20 obce via mikroregion/SMO or wholesale resale at 18-25k per obec through a web vendor; reseller contribution ~15-20k/obec, ~20 obce for target [estimate]. Falls back to 57 without a partner.

## Data gaps
Contract terms for all Registr rows; NEN/TED; 2026 ZZVZ services thresholds (Reg. 541/2025 Sb.); Mokrá-Horákov vendor; Vysočina grant eligibility; any obec <3,000 inhabitants buying a chatbot; Azure EU prices; Czech language quality benchmark.
FX: 24.3 CZK/EUR [estimate].
