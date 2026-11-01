# Decision report: eshop-lookalike-domain-takedown-cz
**Score 55/100 (agent-style model as specified) · Verdict PASS · Capex about 6,500 EUR (range 4,000-10,000) · Confidence Low-Medium**
Reshaped variant (pilot-first, client files own notices, evidence pack + detection, Black Friday/Christmas sweep): about 59/100, borderline; Investigate only if pilot shows >=5 paid shops.
Date 2026-11-01 · Category digital-saas · Hours/week 8-12 pitched, ~11 at 15 shops incl. sales · Screen score 59

## Why in 5 lines
1. Clones are real and growing, but losses fall mostly on consumers and brand reputation. No source shows a small Czech shop paying for protection; named victims (Sportisimo, Tescoma, Super Zoo) are large brands. WTP unproven.
2. Cheap tier is crowded: Recon free tier / $24 mo, StoreLock $4.99, Thicket $49, Tramatm (Czech-language) $20-105. Brief's 990-2,500 CZK sits at/above the top of that range.
3. "Near-zero cost" half true: feed cost small, but no .cz zone/new-registration feed and .cz takedown needs court order. Real cost is takedown labour; at high-cost case margin is negative at 990 CZK.
4. Agent-style model (vendor files notices for client) hits the advocacy monopoly (Act 85/1996) and false-notice liability (DSA, Civil Code). Client-files-own-notices is legally workable but less valuable to buy.
5. Base case [estimate]: ~15 shops after 12 months = ~235 EUR/month profit vs 1,000 EUR target. Only the high case (25 shops at ~2,000 CZK) reaches it.

## Score breakdown
| Criterion | W | Score/10 | Pts | Note |
|---|---|---|---|---|
| Demand and market size | 20 | 4 | 8 | Consumer exposure evidenced (Gen +1,190%, SOBR); no small-shop WTP evidence |
| Unit economics | 20 | 5 | 10 | GM 61-84% at base cost and 1,500+ CZK; tiny absolute revenue; negative in high-cost case at 990 CZK; payback ~50 months base |
| Competition and barriers | 15 | 5 | 7.5 | SME end thin but cheap/free tools cap price; Tramatm can extend; no moat beyond local trust |
| Capital | 10 | 9 | 9 | ~6.5k EUR incl legal opinion; cash need 12-13k EUR |
| Part-time feasibility | 10 | 6 | 6 | ~10-11 h/wk at 22 shops; high case 15+ h/wk |
| Regulatory burden | 10 | 4 | 4 | Advocacy grey zone, DSA/false-notice, GDPR |
| Supply availability | 5 | 3 | 3 | .cz bulk feed closed; CT only; no white-label price |
| Scalability/optionality | 5 | 4 | 4 | SK, evidence-pack SaaS; takedown labour hard to scale |
| Fit with s.r.o. | 5 | 4 | 4 | VAT-payer s.r.o. fits B2B |
| **Total** | 100 | | **55.5** | Pass (<60) |
Variant: Demand 4, Unit econ 5, Competition 5, Capital 9, Part-time 7, Regulatory 6, Supply 4, Scalability 4, Fit 4 = ~59.5; lifts via legal/hours fixes only, so verdict not upgraded.

## Concept, why now
Scan CT logs, new registrations and typosquat permutations for lookalikes of a client's domain/brand; screenshot and score; prepare takedown packs for registrar, host, Google Safe Browsing, Meta, Cloudflare; free lead-magnet scanner. AI-built clones appearing earlier before Christmas (energozrouti.cz, Oct 2026); Black Friday 2026 is 27 Nov. Market size: brief said ~38,000 e-shops; sources give ~50,000 (APEK/Heureka ~50.1-51k 2025; Shoptet ~45k CZ+SK) [sourced: lupa.cz, cc.cz via search, 2026-11-01]; shops with brand worth cloning and ad spend are a small unsourced subset.

## Competition and public-contract channel
| Player | Price (excl VAT unless noted) | Note |
|---|---|---|
| Recon (Shopify) | $24/mo or $220/yr; free up to 10 lookalikes | English, Shopify-centred (pickyourapp.com/products/recon-bot, 2026-11-01) |
| Thicket | $49/brand/mo; $99 takeover incl 4 takedowns/yr | English, US (slashdot.org/software/p/Thicket/, 2026-11-01) |
| StoreLock | $4.99/mo | cheap anchor |
| Tramatm (CZ/SK) | Essential $20/mo, Advanced $105/mo, takedown $40, warning letter $50, demand $180 | prices confirmed 2026-11-01 (tramatm.com/cs/pricing/brand-protection); page does not state automated lookalike e-shop scanning; ask support@tramatm.com |
| Brandfence | $5,000-30,000/yr | enterprise |
| Netcraft, MarkMonitor, BrandShield etc. | quote only | banks/large brands |
| Czech law firms (Arrows, KSANDK) | unknown | bespoke |
| Free | Google/Meta forms, CZ.NIC, ČOI, Police, rizikove.cz | cap WTP |
Barriers Medium. Czech-language/CZK/local-escalation angle real but thin; Tramatm could close it or become partner.
**Public-contract lens:** price/demand benchmark only; subcontract at best; NEN not verified. n=1: ČNB "Brand Protection" (TED 300851-2026, published 2026-05-04), ~312,620 EUR excl VAT, lowest-price award, up to 3 yrs follow-on (from search excerpt, unverified; winner/bids/deadline unknown). Scope executives/credentials/dark web = enterprise-grade, references needed. Small-scale calls up to 3,000,000 CZK exist but no recurring e-shop demand found. Score effect none. Check NEN/VVZ for "ochrana značky", "monitoring internetu", "phishing" (CPV 72xxx/79xxx); smlouvy.gov.cz for ČNB award.

## Supply
Feeds: CertStream (free, uptime unconfirmed; self-host ~10-20 EUR/mo [estimate]); crt.sh free; RDAP rdap.nic.cz free per-domain; ICANN CZDS gTLD zones (.shop/.store unverified); .cz new-registration feed effectively nonexistent (CZ.NIC ended zone contracts 2011); paid NRD feeds $200-600/mo or 499 EUR/mo, .cz unverified - not worth it pre-revenue. Takedown: direct abuse reports free except time; .cz removal needs court/police order; white-label (Netcraft, PhishFort, Takedown.co) no published per-takedown price.
Variable cost per client/month [estimate]: ~175 / 390 / 1,450 CZK (low/base/high), driver is takedown labour at 300 CZK/h. Gross margin: 990 CZK 82/61/-46%; 1,800 CZK 90/78/19%; 2,500 CZK 93/84/42%. The "near-zero cost and complete" assumption does not hold.

## Legal and regulatory (research summary, not legal advice)
- Advocacy monopoly (85/1996 §1-2): paid continuous drafting/sending of legal notices for a client is grey zone, highest risk. Redesign: client files in own accounts; service supplies detection, evidence, forms; legal-effect items to partner advokát.
- False notices: DSA Art.16(2), Art.23(2) suspension; §2976-2978 OZ unfair competition, §81 OZ, §184 TZ if "fake/fraud" label wrong. Mitigate: client warrants mark ownership + indemnity, human review, neutral wording.
- GDPR: WHOIS/RDAP natural-person data; Art.6(1)(f), Art.14, Art.10 flag, Art.30.
- Scraping: CT/RDAP low risk; bypassing controls (§230 TZ) high; test purchases via separate entity/card.
- Entity/VAT: VAT-payer s.r.o. for B2B; optional ring-fence s.r.o. [estimate]; 990 CZK gross = 818 net, 2,500 = 2,066 net.
- Checklist: advocacy opinion 1,500-4,000 EUR [estimate] 2-4 wks; partner advokát; insurance 300-1,000 EUR/yr [estimate]; client contract with indemnity/cap. Burden High as specified, Medium redesigned.
- Open lawyer questions: registrar as hosting service under DSA; indemnity vs criminal liability; GDPR basis for .cz data; DSA implementing law (sněmovní tisk 69); place of supply EU B2B.

## First-year financial sketch ([estimate]; 24.3 CZK/EUR; ex-VAT)
| | Low | Base | High |
|---|---|---|---|
| Price/shop/mo | 990 CZK (41 EUR) | 1,500 (62) | 2,000 (82) |
| Variable cost/shop | 700 | 390 | 390 |
| Contribution/shop | 290 (12 EUR) | 1,110 (46) | 1,610 (66) |
| Shops at month 12 | 8 | 15 | 25 |
| Fixed/month | ~600 EUR | ~450 | ~350 |
| CAC/paying shop | 250 EUR | 250 | 250 |
| One-off capex | ~4,000 | ~6,500 | ~10,000 |
| Operating break-even (excl CAC) | ~50 shops (unreachable) | ~10 shops, month 8 | ~5 shops, month 3 |
| Profit/month at month 12, pre-tax | negative | ~235 EUR | ~1,300 EUR |
| Cash needed | ~12k, never recovered | ~12-13k | ~12k |
| Payback | none | ~50+ months | ~9-12 months |
| Hours/week | 6-8 | ~11 | 14-16 |
Base case cash flow negative through month 12 (cumulative loss ~4,700 EUR with CAC). Target 1,000 EUR/month reached only in high case. Sensitivities: shops reached x price; cases per shop and hours per case; CAC (cold B2B to ~50k shops may exceed 250 EUR). Corporate/dividend tax not applied.

## Top 5 risks
1. No WTP (free + $5-24 tools cap price; losses fall on consumers). 2. Legal exposure (advocacy, false notices, DSA suspension, jednatel personally exposed). 3. Takedown fails on .cz (court order; foreign disposable hosting). 4. Churn when no clone appears. 5. Tramatm/law firm extends into automated e-shop monitoring.

## What would change the verdict
>=5 shops pay 1,500+ CZK/mo (or 4,900+ CZK one-off sweep) within 30 days without discount; Tramatm confirms in writing it does not scan lookalikes and is open to referral/white-label; advokát confirms evidence-pack model is outside the monopoly and quotes escalation fee; white-label partner quotes <~300 CZK/case; NEN/VVZ shows recurring small-scale brand/phishing-monitoring calls; evidence that mid-size shops are hit by clones and already paid someone.

## 30-day validation plan (<300 EUR, no s.r.o. changes)
1. Days 1-3: email Tramatm (lookalike scanning?), CZ.NIC (bulk/new-registration data); search NEN/VVZ.
2. Days 1-7: minimal scanner (crt.sh + typosquat generator + DNS/RDAP); scan 100 mid-size shops (Heureka top lists, Shoptet showcase).
3. Days 5-10: send each a free one-page "lookalikes found" report; no notices filed, neutral wording.
4. Days 8-25: offer Black Friday sweep (pre-sweep report by 27 Nov, evidence pack with ready-to-file notice texts for the shop to submit, post-weekend re-scan); price test 2,900 / 4,900 CZK; 30-50 conversations, >=5 paid.
5. Days 10-25: talk to 2 advokáts; do not commission opinion unless >=3 shops agreed to pay.
6. Day 30: >=5 paid and <2 h per shop = build evidence-pack SaaS and re-score; 1-4 paid = seasonal/one-off product only; 0 = drop.

## Data gaps and sources
Not verified: Czech shop WTP; takedown success rates/timings; clone frequency per shop; white-label price; whether Tramatm scans lookalikes; ČNB tender value/winner; NEN demand; CertStream reliability, crt.sh limits; CZ.NIC bulk-data policy; DSA text (secondary only) and implementing-law status; corporate/dividend tax; count of shops big enough to be targets.
Sources: tramatm.com/cs/pricing/brand-protection; pickyourapp.com/products/recon-bot; slashdot.org/software/p/Thicket/; apps.shopify.com/storelock; arws.cz copycats article; ted.europa.eu/en/notice/300851-2026/pdf; ezak.cnb.cz; ceskenoviny.cz Gen +1,190%; energozrouti.cz Christmas scams; businessinfo.cz fake-shop articles; zakonyprolidi.cz/cs/1996-85; lupa.cz and cc.cz shop counts (all seen 2026-11-01 via search unless noted).
