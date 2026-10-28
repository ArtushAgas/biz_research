---
description: Harvest opportunity signals from sites that block automated fetching (Reddit, Czech forums, Heureka, Google Maps, dTest, Allegro/Amazon lists, Google Trends, tender portals) using the owner's own Chrome. Local only.
argument-hint: [site or topic to focus on, optional]
---

Browser harvest. Focus from the user: $ARGUMENTS

This command needs the Claude in Chrome extension connected in this session (`mcp__claude-in-chrome__*` tools; if only `enable__mcp__claude-in-chrome` exists, call it first). If the tools are missing or the extension is not connected, say so and stop. It runs locally only, never in the cloud routine.

## Rules
- Load the `anthropic-skills:chrome-browser` skill first and follow it (tab context first, new tabs, close what you opened).
- Read-only. Do not log in, post, vote, message, or click purchase/consent actions other than dismissing a cookie banner. Do not work around a site the owner declines in the permission prompt.
- Be gentle: one page at a time, pauses between pages, at most about 30 page views per site per session, and stop on any CAPTCHA, bot check or rate-limit message and tell the owner.
- Record only what is visible: quote short passages (a sentence or two), the URL and the date. No personal data beyond public usernames you do not need; do not store names of private individuals.
- Czech and EU first, but record foreign signals too.

## Site playbook (read-only)
- **Reddit:** search or browse r/czech, r/Prague, r/czechrepublic, r/Slovakia, r/poland, r/germany, r/Netherlands, r/smallbusiness, r/Entrepreneur for "is there a service", "why is there no", "frustrated with", "recommend a ... in Prague". Prefer threads with many replies from the last 24 months.
- **Czech forums:** Emimino, Okoun, Mamaclub (diskuze), Živě/Lupa discussions; same patterns, plus recurring complaints about the same provider.
- **Heureka (obchody and produkty):** 1-2 star shop and product reviews for category leaders; note repeated complaint themes and counts.
- **Google Maps:** reviews of category leaders (parcel pickup points, repair shops, cleaning firms, car services, clinics); sort by lowest rating; note repeated themes.
- **dTest:** article headlines, test results and complaint reports the owner can see (free parts); note which products/services fail repeatedly.
- **Allegro / Amazon.de / Amazon.pl bestsellers and Movers & Shakers, Kickstarter trending, Google Trends (CZ vs DE vs PL rising topics):** record category names, rank changes and trend direction.
- **Tender portals (NEN, Věstník veřejných zakázek, TED):** repeated small service tenders by the same type of buyer (municipalities, schools); record the service, typical value and buyer type.

## Output
1. Append new signals to `opportunities.md` in its line format, with ids continuing each group (A for reviews/complaints, B for communities, C for tenders/B2B, E for bestseller and trend lists), status `new`, and a note `(browser)`. Skip duplicates; raise strength when an existing line gets independent confirmation.
2. Update `sources.md`: mark each site reachable via the owner's browser, usefulness and the signals it produced.
3. Commit and push the changed files.
4. Reply with signals added per site, the 10 strongest, what was blocked or needed a CAPTCHA, and the page count per site.
