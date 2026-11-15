# Decision report: pv-inverter-swap-orphan-service-cz

Date: 2026-11-15 | Category: trade-regulated | Screen score 41 (weekly deep dive taken below the 55 gate)

## 1. Header
- **Idea:** Inverter replacement plus monitoring and annual-check subscription for Czech solar owners whose installer collapsed.
- **Verdict: PASS.** **Score: 48/100** (48.5 by rubric). Confidence: Medium.
- **Capital:** about 6-8k EUR (150-200k CZK), about 3k EUR of it recoverable working capital. FX 25 CZK/EUR [estimate].
- **Hours/week:** 8-12 steady state; the owner can only coordinate (no electrical skills).
- **Reshaped variant** (lead-generation + RMA/triage coordination, no stock, ~1-2k EUR, ~5 h/week): about 55, borderline, capped at 10-25k CZK/month, demand and installer-side willingness to pay for leads unverified.

## 2. Why in 5 lines
1. Orphan demand is real but mostly service/revision inquiries; ČEZ says "dozens per month" contact it [sourced: https://www.cez.cz/cs/pro-media/tiskove-zpravy/zakaznikum-od-nespolehlivych-dodavatelu-fotovoltaik-chybi-nasledny-servis-a-revize.-na-cez-prodej-se-jich-obraceji-desitky-mesicne-229884, 2025-12-08].
2. Most orphaned plants (2021-2025 installs) are still under manufacturer warranty (Huawei 15 y, Solax 5-10 y); warranty swaps are labour-only RMA work, so the paid-swap pool (out-of-warranty, incompatible, upgrade) is small and unsized.
3. Margin per swap at 40k CZK ex VAT: Solax 5.0-M about 6k / 1k / -8k CZK (low/base/high cost); Huawei 5KTL-L1 about 20k / 16k / 9k CZK. The cheap Huawei end may be a grey import.
4. Incumbents sell the same service cheaply: ČEZ 399-499 CZK/month and ~7.3k CZK one-off, E.ON 349 CZK/month. Monitoring at 1-2k CZK/year is worthless alone (manufacturer clouds are free).
5. The owner cannot do the electrical work yet carries consumer-law and warranty liability. 25k CZK/month needs ~3-4 paid swaps/month against unproven demand.

## 3. Score breakdown
| Criterion | Wt | /10 | Pts |
|---|---|---|---|
| Demand and market size | 20 | 4 | 8 |
| Unit economics | 20 | 4 | 8 |
| Competition and barriers | 15 | 4 | 6 |
| Capital | 10 | 9 | 9 |
| Part-time feasibility | 10 | 6 | 6 |
| Regulatory burden | 10 | 4 | 4 |
| Supply availability | 5 | 4 | 2 |
| Scalability and optionality | 5 | 4 | 2 |
| Fit with existing s.r.o. (VAT only) | 5 | 7 | 3.5 |
| **Total** | 100 | | **48.5** |

Public-contract channel: not verified, no score effect.

## 4. Concept, why now
Installer failures after the 2021-2025 boom left owners without service. Why-now weakens: the ČEZ release is nearly a year old, new installs fell 28% in 2025 (27,298; 696 MW), and consolidators (PREsolidsun merged with SOLARINVEST-GREEN ENERGY, Jul 2025) absorb orphans.

## 5. Competition and public-contract channel
| Player | Offer | Price |
|---|---|---|
| ČEZ Prodej | one-off service / revision | 7,260 / 7,965 CZK |
| ČEZ Prodej | plan, third-party PV | 499 CZK/month (own PV 399) |
| E.ON | plan / one-off | 349 CZK/month / ~7,000 CZK |
| PREsolidsun | typical repair | ~50,000 CZK |
| Local electricians | revision | from 3,000 CZK |
| Manufacturer cloud | monitoring | free |
| Owner hypothesis | swap / monitoring | 35-45k CZK / 1-2k CZK per year |

ČEZ/E.ON strong on trust and scale, weaker on brand coverage (ČEZ: Solax, Growatt, GoodWe, ČEZ Battery Box). Other players: PREsolidsun (IČ 28923405), reWATT. Barrier to entry Medium; to a profitable job, higher.

**Public contracts (B2G):** Not verified; at best subcontract-only or price benchmark. TED 415638-2026 (kindergarten roof 49.5 kWp, 60 months service) and 310503-2026 bundle service inside build tenders. NEN unreadable from the cloud sandbox; values, winners, bid counts unavailable. To check: NEN tally for CPV 50532000 / 09332000 / 45261215 and "servis FVE", Registr smluv.

## 6. Supply
Retail ex VAT: Solax X1-Hybrid-5.0-M 33,444 CZK (vmshop.cz, search snippet); Huawei 5KTL-L1 687 EUR (~16.7k CZK, panpower.eu), 27,458 CZK (groupsumi.cz), ~32.5k CZK (wattuneed). At 27k CZK the Huawei margin shrinks to ~5-8k CZK [estimate]. Labour: Prague electrician 700-900 CZK/h (energozrouti.cz, 2025-10-23); revision 3,000-7,260 CZK; all-in labour 6-12k CZK [estimate]. No wholesale/trade-account prices found; 15-20% discount is [estimate]. Single subcontractor pair = single point of failure.

## 7. Legal and regulatory (research summary, not legal advice)
- Electrical work and revisions need certified individuals and a řemeslná trade (NV 194/2022 Sb. as amended by 175/2024; reserved equipment NV 190/2022); not verified on e-Sbírka. Owner would only coordinate.
- Domestic reverse charge §92e ZDPH does not apply to households. 12% VAT for construction/assembly on residential buildings (§49(4)); whether the supplied inverter qualifies is unconfirmed. If the 35-45k price is VAT-inclusive, Solax is clearly loss-making.
- Home-visit contracts: 14-day cooling-off, up to 1 year + 14 days if information missing (§1820, §1829 OZ); ČOI fines up to 5M CZK (secondary).
- 24-month warranty for work and subcontractor allocation unresolved (§2161-2165, §2615-2619). DSO notice after a swap NOT confirmed (ČEZ Distribuce A1/A2 unreadable). GDPR processor terms with cloud vendors. Imbalance (odchylka) trap for subscriptions. ERÚ licence not needed <100 kW own consumption since Aug 2025. NZÚ likely does not cover swaps (unverified).
- Burden: Medium (High if owner's own staff do electrical work). Entity: VAT-payer s.r.o.
- Lawyer: NV 194/190, DSO notice, warranty, cooling-off, non-compete, GDPR roles, jednatel liability. Accountant: 12% vs 21%, CZ-CPA class, splitting across the two s.r.o.

## 8. First-year financial sketch
Assumptions [estimate]: 40k CZK ex VAT, fixed ~6k CZK/month, CAC 3-5k CZK/swap, zero swaps months 1-3, ~20 monitoring subscribers.

| | Low | Base | High |
|---|---|---|---|
| Paid swaps/month (from month 5) | 1 | 2 | 3 |
| Contribution per swap | 6k | 12k | 18k |
| CAC per swap | 5k | 4k | 3k |
| Monthly profit, steady state | -5k CZK | +11k (~440 EUR) | +42k (~1,680 EUR) |
| Year-1 result before capex | ~-90k CZK | ~+50k | ~+270k |
| Payback | none | 20-24 months | 9-10 months |

25k CZK/month needs ~3.75 swaps/month (base) or ~2.5 (high). Most sensitive: paid swaps per month, then contribution (brand mix, dealer discount).

## 9. Top 5 risks
1. Paid-swap pool too small because of warranties. 2. Margin squeeze, retail-only pricing, brand fragmentation. 3. Incumbents (ČEZ, E.ON, PRE) own trust and cheap plans. 4. Liability for work the owner cannot supervise. 5. Single subcontractor, švarcsystém/non-compete exposure, unconfirmed DSO paperwork.

## 10. What would change the verdict
5+ real out-of-warranty orphan quotes at >=12k CZK contribution; dealer pricing >=20% below retail; simple DSO notification; subcontractor carrying warranty in writing without exclusivity; NEN tally showing repeated public PV-service demand; evidence of many out-of-warranty (2009-2013) failures; installers willing to pay for leads.

## 11. 30-day validation plan (~600-900 EUR)
1. Week 1: request trade prices (GBC Solino, Krannich CZ, Sonepar, Photomate, Ptáček); call 10 Prague electricians/revision technicians for swap labour and whether one carries warranty on referrals.
2. Week 1-2: mystery-shop ČEZ, E.ON, PREsolidsun, reWATT for out-of-warranty Solax/Huawei swap quotes.
3. Week 2: demand probe: ask Český svaz akumulace a fotovoltaiky ("Pomocná ruka" volumes), forum.mypower.cz and PV Facebook groups; landing page + Google Ads (300-500 EUR) for "výměna střídače", "servis střídače", "zkrachovalý dodavatel fotovoltaika"; measure CPC, leads, out-of-warranty share, willingness to pay.
4. Week 3: 1-hour lawyer call (~150 EUR), 30-minute accountant call, ask ČEZ Distribuce about swap notification.
5. Week 4: Go only if >=5 qualified paid out-of-warranty leads, contribution >=12k CZK, liability-bearing subcontractor and DSO answer; pivot to lead-gen variant if leads but no margin; otherwise kill.

## 12. Data gaps and sources
Gaps: all-in CZ swap price; dealer discounts; DSO procedure; VAT basis of price and 12% vs 21%; "20 firms"/"hundreds collapsed" at primary level; PREsolidsun/reWATT financials; NEN tally; CPC; Fronius/Sungrow/Growatt prices; count of paid out-of-warranty swaps per month.
The judge fetched the ČEZ press release (confirms "desítky měsíčně", states no prices or brands); ČEZ prices (7,260 / 7,965 / 399 / 499 CZK) come from the competition report's read of cez.cz/cs/sluzby/servis-a-revize-fotovoltaiky and are unverified at primary level.
Sources: ČEZ press release above; https://www.cez.cz/cs/sluzby/servis-a-revize-fotovoltaiky; https://vmshop.cz; https://panpower.eu/cs/stridace/4922-huawei-sun2000-5ktl-l1-5-kw.html; groupsumi.cz; onsaplus.eu; wattuneed; energozrouti.cz (2025-10-23); https://www.seznamzpravy.cz/clanek/ekonomika-finance-solary-bez-servisu-prevzeti-oprav-po-padlem-dodavateli-vyjde-i-na-desetitisice-304621; https://gbc-solino.cz/wp-content/uploads/2024/12/WTY_SOLAX_AELIO-CZ.pdf; https://www.estav.cz/cz/13577.servis-fve-rewatt-udrzba-revize-i-dokonceni-rozestavenych-elektraren; TED 415638-2026, 310503-2026.
