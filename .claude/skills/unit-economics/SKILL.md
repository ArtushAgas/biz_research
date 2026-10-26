---
name: unit-economics
description: Standard template and formulas for a first-year unit-economics and break-even sketch for a small business idea. Use when the judge builds the financial section of a report.
---

# First-year unit economics

Work in EUR (show CZK in brackets at a stated rate). Produce Low / Base / High cases and state every assumption as [estimate] or [sourced].

## Inputs
- Price per unit (ex-VAT) from the competition report; units or customers per month ramp (month 1-12).
- Variable cost per unit: goods landed cost, services expert cost, payment fees, shipping, returns, customer acquisition cost.
- Fixed monthly costs: rent, software, insurance, accounting, marketing baseline, salaries (owner is part-time, so count outsourced labor), licenses.
- One-off capex: equipment, build-out, initial inventory, legal/registration, branding/site, deposits.

## Formulas
- Gross margin = (price - variable cost) / price
- Contribution per unit = price - variable cost
- Break-even units/month = fixed monthly costs / contribution per unit
- Cash needed = one-off capex + inventory + sum of monthly losses until break-even + 3 months buffer
- Payback (months) = cash needed / steady-state monthly profit
- Hours/week: owner time per month / 4.3

## Sanity checks
- Does ramp-up respect real demand and the competition's volume?
- Is acquisition cost consistent with ad prices seen?
- Corporate tax (check current CZ rate), VAT treatment and dividend tax noted from the legal report, not guessed.
- Compare with the 100k EUR cap and the owner's minimum profit target in `profile.md`.

Output as a compact table plus 3 lines on the most sensitive assumption.
