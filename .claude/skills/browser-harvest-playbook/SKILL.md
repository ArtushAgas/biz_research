---
name: browser-harvest-playbook
description: Practical how-to for harvesting signals through the owner's Chrome (Claude in Chrome extension): connection fixes, tool tips, per-site URL patterns, what works and what does not, and how to scan each site efficiently. Includes the NEN public-procurement playbook. Use before any /harvest-browser run or any task that reads Heureka, Google Maps, Amazon.de, NEN, dTest, Allegro, Google Trends or Czech forums in the browser.
---

# Browser harvest playbook
Learned in the first four browser runs (2026-10-28, ~35 page views). Local only. Update this file when a site pattern changes.

## 1. Connection and tools
- The extension must be connected when the session starts. Check with `/chrome` (or start with `claude --chrome`). If browser tools are missing, stop and tell the owner; do not retry. If the connection drops mid-session the tools vanish; the owner must reconnect (quit Chrome with Cmd+Q, reopen, `/chrome`, or start a fresh session).
- Tools are deferred: load them in ONE ToolSearch call: `tabs_context_mcp, navigate, computer, read_page, get_page_text, find, tabs_create_mcp, tabs_close_mcp`. A `browser_batch` tool may exist; use it to chain navigate + get_page_text when available.
- Start with `tabs_context_mcp` (createIfEmpty true). It gives one empty tab; use that tab, do not touch the owner's tabs. Close it at the end with `tabs_close_mcp`.
- Reading a page: `get_page_text` first (cheap, works on most sites). If it says "No text content" (dTest), use `read_page` with `filter: all` and a `max_chars`. Use `find` to get a ref for a button or link, then click with `ref`.
- Screenshots: use `scale` 0.4-0.5. The reported coordinate frame is the full size; multiply half-scale pixels by 2 before clicking by coordinate. Prefer `find` + ref over coordinates (layouts shift, e.g. the Maps Reviews tab moves when a photo header is present).
- Errors seen:
  - "This site is not allowed due to safety restrictions": the extension blocks the site (Reddit). Do not work around it. Owner decision: ignore Reddit.
  - "Permission denied for reading pages on this domain": occurred when `find` ran before the page finished loading; wait a moment (take a screenshot) and retry once. If it persists, ask the owner to allow the domain in the extension.
  - "Frame with ID 0 is showing error page": Chrome could not load the site (Mamaclub). Try once more with the root URL, then record it as unreachable.
  - "Can't interact with browser-internal or unparseable URLs": the tab is still loading; retry after a screenshot.
- Stop after 2-3 failures on the same site and record it in `sources.md`. Do not guess URLs more than twice; navigate through the site's own links with `find` instead.

## 2. Consent banners (declining is allowed)
- Heureka: "Povolit nezbytné". The page text is readable even with the banner.
- dTest: `deny cookies` button ("Ne, nesouhlasím"); the banner hides the page.
- Allegro.cz: "Nesouhlasím" (full-width dialog).
- Amazon.de: banner shows but page text is readable; no click needed.
- Google Maps / NEN / Google Trends: no consent screen seen.
- Never click Accept, log in, or open sponsored ad links (Maps "Sponzorováno" results).

## 3. Site recipes
### NEN (nen.nipez.cz) - high value, use every run
- Use the English UI: `https://nen.nipez.cz/en/verejne-zakazky`. The Czech path `/verejne-zakazky` redirects there.
- Keyword search by URL: `https://nen.nipez.cz/en/verejne-zakazky/p:vz:query=<url-encoded term>`, e.g. `...query=%C3%BAklid` for "úklid" (about 2,800 results, 56 pages of 50). Typing into the Quick search box and pressing Search produces the same URL.
- `get_page_text` returns 50 rows per page: NEN number, procedure name, status (Not terminated = open, Awarded, Cancelled, Termination of performance), contracting authority, deadline. "LOAD ANOTHER 50" and page numbers give more. Estimated contract values and CPV codes are NOT in the list; they sit on each Detail page and in Advanced search (not tried yet).
- How to scan: search one keyword, read page 1 (and page 2 if the mix is interesting), then tally: services vs supplies, buyer types (ministries, offices, courts, hospitals, municipalities, schools), contract periods (2027-2030 = multi-year), Prague buyers, same buyer repeating numbered purchases. Record "n of 50" patterns as C-group lines with the keyword and date. Then open 2-3 Prague Detail pages for value, qualification and incumbent.
- Detail pages: click the row's "Show detail ..." link (found with `find`) or open `/en/verejne-zakazky/detail-zakazky/<NEN-number-with-dashes>`, e.g. `N006-26-V00021635`. The Information tab shows procedure type (above-threshold, small-scale), contracting authority, deadline, CPV, place; it does NOT show the estimated value for most tenders. The Result tab (`.../vysledek`) stayed empty (loading placeholders) in two tries; do not retry it.
- Getting value, winner and bidders (works): note the VVZ form number from the Information tab ("Publication Records in the VVZ", e.g. F2026-058141). Open `https://vvz.nipez.cz/vyhledat-formular`, type the number in "Evidenční číslo formuláře" and press Enter, then open the result; the page shows the TED notice number. Open `https://ted.europa.eu/en/notice/-/detail/<number>` (e.g. 742544-2026), choose "Accept only essential cookies", click the collapsed "Notice" section, then `get_page_text`: it lists estimated value, winning price, winner, number of tenders (SME share), award criteria, qualification and the contract-register link (smlouvy.gov.cz). Only above-threshold tenders appear on TED. Guessed VVZ URLs 404; use the search form. NEN's own cookie banner has "Refuse all".
- Worked example (MPSV Prague cleaning): see C-035. Small-scale tenders (below threshold, "otevřená výzva", e.g. Drážní inspekce, C-036) have shorter deadlines; open Documents for the specification and price form.
- Keywords to run (done: úklid; first unfiltered page): ostraha, údržba zeleně / sekání / výsadba, zimní údržba, IT podpora / správa sítě, překlady / tlumočení, stravování / catering, tisk / polygrafie, školení, mytí oken, deratizace, odpady / svoz, kurýrní / přeprava, správa webu / grafické práce, revize / servis hasicích přístrojů, stěhování, audit / poradenství.
- Findings so far: C-031 (energy-saving tenders by private firms), C-032 (MoD small buys), C-033 (about 30 of 50 "úklid" results are public cleaning-service contracts), C-034 (cleaning supplies).
- VVZ (vvz.nipez.cz) and TED are reachable; see above. Still to try: NEN Advanced search filters (Prague, service type, status "Not terminated" only), the Documents tab of small-scale tenders, smlouvy.gov.cz contract pages (price lists), and VVZ search by CPV code (90910000 cleaning, 90919200 offices) to list awarded cleaning contracts with winners.

### Heureka (heureka.cz)
- Shop reviews: `https://obchody.heureka.cz/<shop-slug>/recenze/`. Negative only: `https://obchody.heureka.cz/<shop-slug>/recenze/negativni`. `/obchody/` and guessed slugs 404 (`zasilkovna-cz` is not a shop); `alza-cz` works. Find slugs via the shop's Heureka link or `find`.
- Page text includes: 6-month theme counts (positive and negative), reviews with percentage and "Doporučuje / Nedoporučuje", and the shop's replies. Each negative page shows about 17-20 reviews; "Zobrazit další recenze" loads more.
- Scan: read the negative page, tally themes ("n of 17": delivery promise, partial delivery, stock, support, damage), note the shop's standard reply (voucher = no real remedy). Untried: Notino, Rohlik, Datart, Mall, Czc, Okay; product reviews.

### Google Maps
- Search URL: `https://www.google.com/maps/search/<query>?hl=cs`. `get_page_text` returns about 10 results with rating, review count, category, address. Items marked "Sponzorováno" are ads: read, never click.
- Use it to rate the field (are leaders 4.5-5.0 with large counts, a counter-signal, or 2.0-4.0, a quality gap?). To read reviews: `find` the organic result, click its ref, `find` the "Recenze" tab and click, then `get_page_text` (about 10 reviews). Reviews tab can be sorted ("Nejrelevantnější" control; sorting by lowest not yet tried).
- Do not store reviewer names. Tally themes per outlet ("n of 10").
- Results so far: Zásilkovna pickup points (2.0-4.3, redirect complaints), cleaning firms (4.5-5.0, no gap), movers (4.4-5.0, no gap), appliance repair (4.2-5.0, no gap), car services (4.1-4.8, old disputes). Untried: clinics, dentists, pet services, locksmiths and plumbers, parcel boxes (Balíkovna, Z-Box), hairdressers, language schools.

### Amazon.de
- Movers & Shakers pages are empty. Use `https://www.amazon.de/gp/new-releases/<dept>/` (Hot New Releases) and `.../gp/bestsellers/<dept>/` (not tried yet). Departments tried: `kitchen`, `pet-supplies`. Page text gives 30 items with CZK price (ships to Czechia), stars and review counts; page 2 via pagination.
- Scan: count clusters ("6 of 30 are heated ponchos"), note seasonality, price band, no-name vs brand. One-day snapshot only; repeat later to see rank movement. About 18 departments remain (garden, sports-outdoors, baby, toys, automotive, electronics, health, beauty, diy).

### dTest (dtest.cz/clanky)
- Free part is headlines and consumer advice, little complaint data. `get_page_text` fails; use `read_page` filter all after declining cookies. Low value; revisit only for "Chytáky a podvody", "E-shopy", "Reklamace" category lists.

### Google Trends CZ
- `https://trends.google.com/trending?geo=CZ&hours=168` loads as text but is mostly news, sport, weather. Low value unless filtered by category (not tried) or used for explicit term comparisons (explore pages not tried).

### Czech forums
- Emimino: homepage loads; `/diskuze/` and `?q=` URLs 404, the on-site search box did not submit, the menu "Diskuze" link did not navigate. Unresolved; try opening a discussion from a search-engine result (`site:emimino.cz <topic>`) and read that page.
- Mamaclub: Chrome error page on `/` and `/diskuze/` (2026-10-28). Retry later.
- Okoun: `/boards/` is only a board index. Needs a specific board. Low expected value.
- Modrý koník (modrykonik.cz/forum) was the best forum source via the search tool.

### Allegro.cz
- Loads after declining consent. A guessed category slug redirected to Music and `get_page_text` returned one listing. Needs real category URLs or the "Cenové hity" page. Not yet useful.

### Reddit
- Refused by the extension. Owner decision (2026-10-28): ignore. Do not retry or work around.

## 4. Efficient scanning rules
- Budget: about 30 page views per site; most sites need 2-5. Decide the question first (what pattern would count as a signal), read the list page once, tally, then open at most 1-2 detail pages.
- Prefer sources that show counts or lists (NEN rows, Maps ratings, Heureka theme counts, Amazon clusters). Record patterns as "n of N" with the date, never as generalisations.
- Counter-signals count: a category with 4.5-5.0 ratings and big volumes (movers, cleaning, appliance repair in Prague) rules out a quality-gap idea. Record them with strength 1-2 so the scout does not re-propose them.
- Keep a short note per site in `sources.md` (reachable, URL pattern, usefulness, signals, page views).
- Order of work per run: NEN keywords, Heureka negative pages, Maps categories, Amazon departments, then forums. End by closing the tab, writing signals, committing and pushing.
- Quote at most a sentence, no reviewer names, always URL and date. Mark `(browser)`.
