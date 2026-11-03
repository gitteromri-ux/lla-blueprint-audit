# Blueprint Meta campaign #118148 — the serious version

Longevity Life Academy · ad account 1459085242361281 · campaign 52663511211628 · data pulled Nov 3 2026, 13:10 Israel time.
Every number below comes from the Meta Insights/Graph API, the pixel event log, or the checkout repo commit log. QA-test events are removed where stated. Nothing is estimated.

---

## TL;DR

1. **Bug window = Sep 16 → Sep 29.** Attribution was broken, but carts and checkouts kept tracking in the browser. Inside the window the campaign produced **31 real carts, 5 real checkouts and 1 credited purchase (Sep 16, its first day) on $8,976.** The six clean days after the fix were worse. The bug hid at most 1–2 sales; it did not hide a working campaign.
2. **Delivery collapsed on Oct 5 and has never recovered.** Same sets, same ads, same 40M audiences; CPM went from $17–24 to $266–388. The current configuration has spent **$2,977 in 29 days for 5 carts, 1 checkout, 1 purchase.** This is the single biggest problem and no audience tweak fixes it.
3. **The checkout count you were shown is inflated by 21 QA-test checkouts and 37 QA-test carts** (men 35–44, Sep 20–26, $53 of spend). Meta shows 31 checkouts and 86 carts for this campaign. Real: **10 checkouts, 49 carts** in two months on $18,337.
4. **Cold interest targeting never worked, bug or no bug.** Six interest/broad sets, $14,182, 6,445 clicks, 29 carts, 6 checkouts, 2 purchases — and both purchases were Sep 10–13, the first ten days.
5. **The only thing that produces Blueprint buyers is Masterclass people.** 2 of the 3 October purchases landed within 4 days of the Oct 27 $79 attendee offer. The buyer list, the Masterclass checkout lists and the purchaser lookalikes ($305 per purchase in Masterclass set #108814) all exist in this account and **no Blueprint set uses any of them.**
6. **Win-fast plan** (section 10): kill the three starved sets, run Blueprint only to Masterclass buyers + checkout starters + purchaser lookalikes, FB Feed + Reels, mobile, women 45–65+, Courtney creative, $180/day total. Expected on Masterclass-set benchmarks: first purchases inside 7 days at $300–500, not $4,580.

---

## 1. Data integrity — what was factored in

| Factor | How it is handled here |
|---|---|
| Bug window | Sep 16 00:13 (last CAPI/EMQ commit live) → Sep 29. Period P1 below. Carts/checkouts are browser events and kept tracking; purchase attribution did not. |
| QA test device | Men 35–44 in Adset 4, Sep 20–26: 37 carts, 21 checkouts on $53. Removed from every "real" figure. Dates: Sep 20 (11 carts / 7 checkouts), Sep 21 (9/1), Sep 22 (2/0), Sep 23 (1/0), Sep 24 (11/11), Sep 25 (1/0), Sep 26 (2/2). |
| Paused sets | All 7 sets that ever ran are listed with run dates (section 3). Nothing is averaged across live and dead sets. |
| Settings changes | Adsets 1 and 3 paused Sep 16; Adset 2 and 5 rebuilt as new IDs Sep 28; budgets edited Oct 30; Adset 4 edited Nov 2. Periods are cut on those dates. |
| Time of day / day of week | Section 7, from the hourly breakdown in account time zone (Israel), translated to US Eastern. |
| Pixel vs Meta | Pixel event log by host shows real Blueprint purchases on pages.dev regardless of attribution (reaches back to Oct 6 only). |
| CRM | ActiveCampaign connector returns "Invalid URL" on every call. CRM purchase rows are not joined. |

---

## 2. Four periods, every set, tests removed

**P0 · Sep 3–15 · clean, before the bug**

| Set | Days | Spend | Impr. | CPM | Clicks | CPC | Carts | Checkouts | Purchases |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Adset 2 v1 #108808 (interests 11, 35–64) | 13 | $2,902 | 103,609 | $28 | 1,948 | $1.49 | 5 | 3 | **2** (Sep 10, Sep 13) |
| Adset 1 #108807 (interests 11, 18–65) | 6 | $1,244 | 44,584 | $28 | 353 | $3.52 | 1 | 0 | 0 |
| Adset 3 #108809 (broad 18–65) | 7 | $568 | 26,485 | $21 | 415 | $1.37 | 0 | 0 | 0 |
| Adset 4 #108810 remarketing (day 1) | 1 | $51 | 130 | $394 | 3 | — | 1 | 1 | 0 |

**P1 · Sep 16–29 · bug window (attribution broken, browser events alive)**

| Set | Days | Spend | Impr. | CPM | Clicks | CPC | Carts | Checkouts | Purchases |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Adset 2 v1 #108808 | 14 | $4,648 | 206,610 | $22 | 2,470 | $1.88 | 11 | 1 | 0 |
| Adset 4 #108810 remarketing | 14 | $2,464 | 9,698 | $254 | 172 | $14.33 | 15 | 2 | **1** (Sep 16, woman 55–64) |
| Adset 5 v1 #108811 (broad 35–64) | 13 | $1,437 | 9,376 | $153 | 131 | $10.97 | 5 | 2 | 0 |
| Adset 2 v2 + Adset 5 v2 (born Sep 28) | 2 | $427 | 11,388 | $37 | 122 | $3.50 | 0 | 0 | 0 |

**P2 · Sep 30–Oct 5 · bug fixed, delivery still normal**

| Set | Days | Spend | Impr. | CPM | Clicks | CPC | Carts | Checkouts | Purchases |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Adset 2 v2 #108808 (41 interests ∧ shoppers ∧ income, 45–64) | 6 | $725 | 29,751 | $24 | 424 | $1.71 | 3 | 0 | 0 |
| Adset 5 v2 #108811 (identical) | 6 | $578 | 34,075 | $17 | 491 | $1.18 | 2 | 0 | 0 |
| Adset 4 #108810 remarketing | 6 | $313 | 1,431 | $218 | 25 | $12.50 | 1 | 0 | 0 |

**P3 · Oct 6–Nov 3 · current configuration, delivery collapsed**

| Set | Days | Spend | Impr. | CPM | Clicks | CPC | Carts | Checkouts | Purchases |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| Adset 4 #108810 remarketing | 29 | $1,323 | 3,706 | **$357** | 88 | $15.04 | 3 | 1 | **1** (Oct 28, woman 35–44) |
| Adset 2 v2 #108808 | 29 | $793 | 2,985 | **$266** | 59 | $13.43 | 1 | 0 | 0 |
| Adset 5 v2 #108811 | 29 | $861 | 2,218 | **$388** | 32 | $26.90 | 1 | 0 | 0 |

What the four periods say:

- The bug window (P1) is not hiding a good campaign. $9,000 bought 31 real carts and 5 real checkouts. P0, with clean attribution, had the same cart rate (0.3% of clicks).
- The six clean post-fix days (P2) are the fairest test of the rebuilt interest sets: $1,303, 915 clicks at $1.18–1.71, 5 carts, 0 checkouts. That is the audience failing, not the pixel.
- P3 is a different failure. Impressions per week fell from 75,000 to 1,400–3,300. Clicks went from $1.18 to $13–27. Nothing in P3 is a read on audiences; it is a read on broken delivery.

![Weekly spend, real checkouts, QA checkouts, credited purchases](charts/Blueprint_1_timeline_spend_checkouts_purchases.png)

---

## 3. Every set that ever ran, including paused ones

| Set | ID | Ran | Status | Budget | Targeting | Spend | Clicks | Carts | Checkouts | Purchases |
|---|---|---|---|---:|---|---:|---:|---:|---:|---:|
| Adset 1 #108807 | 52663511359228 | Sep 3–8 | Paused Sep 16 | $1 | 11 interests, 18–65, 34 states | $1,244 | 353 | 1 | 0 | 0 |
| Adset 2 v1 #108808 | 52663512093428 | Sep 3–28 | Paused Sep 28 | $160 | 11 interests, 35–64, 34 states | $7,550 | 4,418 | 16 | 4 | 2 |
| Adset 3 #108809 | 52664534627228 | Sep 9–14 | Paused Sep 16 | $100 | broad, 18–65, 34 states | $568 | 415 | 0 | 0 | 0 |
| Adset 5 v1 #108811 | 52666296222628 | Sep 16–28 | Paused Sep 28 | $40 | broad, 35–64, 34 states | $1,437 | 131 | 5 | 2 | 0 |
| Adset 4 #108810 | 52666232368428 | Sep 15 → live | **Active** | $139 | 11 remarketing lists, 25–65+, 34 states | $4,151 | 288 | 57 (20 real) | 25 (4 real) | 2 |
| Adset 2 v2 #108808 | 52669013718628 | Sep 28 → live | **Active** | $39 | 41 interests ∧ Engaged Shoppers ∧ top-25% income, 45–64, US | $1,778 | 556 | 4 | 0 | 0 |
| Adset 5 v2 #108811 | 52669048300628 | Sep 28 → live | **Active** | $45 | identical to Adset 2 v2 | $1,605 | 572 | 3 | 0 | 0 |
| Blueprint LAL #108779 | 52676923495628 | never | Paused, no ads | $99 | LAL 1% Masterclass buyers, 45–65 | $0 | — | — | — | — |

Cold prospecting total (sets 1, 2 v1, 3, 5 v1, 2 v2, 5 v2): **$14,182, 6,445 clicks, 29 carts, 6 checkouts, 2 purchases**, both before Sep 14.

---

## 4. How the three live sets are configured right now

| | Adset 4 #108810 | Adset 2 #108808 | Adset 5 #108811 |
|---|---|---|---|
| Budget | $139/day | $39/day | $45/day |
| Optimization | Purchase · lowest cost · 7d click 1d view | same | same |
| Audience | site 30/90d, checkout 30/90d, cart 30/90d, leads 30/90d, form openers, 2 video-viewer lists · **27–32k people** | 41 interests AND Engaged Shoppers AND top-25% income · **40–47M people** | identical copy |
| Exclusions | none (buyers and the QA device inside) | none | none |
| Lookalikes | none | none | none |
| Geo / age / gender | 34 US states · 25–65+ · all | US · 45–64 · all | US · 45–64 · all |
| Advantage audience | off | off | off |
| Placements | FB Feed, FB Reels, IG Feed, IG Reels | same | same |
| Devices | mobile + desktop | same | same |
| Ads spending | Courtney video #3, Courtney static #3, Courtney static #2, Julie video #12, Julie static #6 | Julie video #12, Julie static #6, Courtney static #3 | Julie video #12 |

Audience size is not the reason for the Oct 5 collapse: Adset 2 and 5 reach 40–47 million people. The pattern (Purchase optimization, no Blueprint purchase signal reaching the pixel for weeks, Advantage audience off, three sets competing for the same people) is the one where Meta restricts delivery to a few "predicted buyers" and pays anything for them.

![CPM by live ad set](charts/Blueprint_2_CPM_by_adset.png)

---

## 5. Placements — three live sets, full life

Checkout counts include the 21 QA-test checkouts, which Meta cannot split by placement. Carts are the cleaner column.

| Placement | Spend | Carts | Checkouts | Read |
|---|---:|---:|---:|---|
| FB Feed | $4,279 | 40 | 12 | the only placement with volume |
| FB Reels | $1,007 | 8 | 6 | second |
| IG Feed | $1,103 | 5 | 1 | $1,103 per checkout |
| IG Reels | $446 | 0 | 0 | zero |
| IG Stories | $187 | 2 | 1 | thin |
| FB Stories | $160 | 1 | 0 | zero |
| In-stream, Reels overlay, Audience Network, unknown | $263 | 8 | 5 | test-device noise |
| Desktop (all placements) | $304 | — | 0 | zero |

Instagram + Stories + desktop + misc: **$2,463, 2 real checkouts.**

---

## 6. Ages and genders — three live sets, full life

| Cell | Spend | Carts | Checkouts | Read |
|---|---:|---:|---:|---|
| Women 55–64 | $2,658 | 14 | 1 | the only cold cell that carts in volume; credited buyer Sep 16 |
| Women 45–54 | $1,567 | 3 | 1 | credited buyer Sep 10 (Adset 2 v1) |
| Men 55–64 | $1,192 | 3 | 0 | zero |
| Women 35–44 | $584 | 2 | 1 | credited buyer Oct 28 (remarketing) |
| Men 45–54 | $502 | 2 | 0 | credited buyer Sep 13 in v1, nothing since |
| Women 65+ | $392 | 1 | 0 | capped out of Adset 2/5 by the 64 ceiling |
| Men 65+ | $336 | 1 | 1 | thin |
| Men 35–44 | $206 | 38 | 21 | **QA test device** |

Men 45–64 in the live sets: **$1,694, 5 carts, 0 checkouts.**

![Placement and gender-age](charts/Blueprint_3_placement_age_gender.png)

---

## 7. Time of day and day of week

Hourly data is in account time zone (Israel). US Eastern = Israel minus 7 hours. Lifetime hours 09:00–14:00 Israel are contaminated by the QA tests (Omri's working hours), so the clean read is the post-fix window Sep 30–Nov 3.

**Sep 30–Nov 3, by Israel hour (US Eastern in brackets)**

| Israel hour | US ET | Spend | Clicks | Carts | Checkouts | Purchases |
|---|---|---:|---:|---:|---:|---:|
| 00–06 | 17:00–23:00 ET | $2,153 | 497 | 8 | 0 | 0 |
| 06–12 | 23:00–05:00 ET | $642 | 165 | 1 | 0 | 0 |
| 12–18 | 05:00–11:00 ET | $1,148 | 248 | 2 | 1 | 1 |
| 18–24 | 11:00–17:00 ET | $648 | 209 | 0 | 0 | 0 |

Half the spend and 8 of 11 carts happen in the US evening (17:00–23:00 ET). The 23:00–05:00 ET block ($642, 1 cart) is the only day-part worth cutting, and it is 14% of spend. Day-parting is not the lever; volume is too small to schedule around.

**Day of week, whole campaign, tests removed**

| Day | Spend | Carts | Checkouts | Purchases | $ per cart |
|---|---:|---:|---:|---:|---:|
| Mon | $2,865 | 8 | 2 | 0 | $358 |
| Tue | $2,395 | 4 | 1 | 0 | $599 |
| Wed | $2,594 | 8 | 3 | 2 | $324 |
| Thu | $3,211 | 7 | 1 | 1 | $459 |
| Fri | $2,300 | 12 | 1 | 0 | $192 |
| Sat | $1,768 | 3 | 1 | 0 | $589 |
| Sun | $3,200 | 7 | 1 | 1 | $457 |

Friday carts cheapest, Saturday and Tuesday worst, but 3–12 carts a day of week is not a schedule, it is noise. No day-of-week action.

---

## 8. Ads

| Ad | Spend | Clicks | CPC | Real checkouts | Purchases |
|---|---:|---:|---:|---:|---:|
| Julie video #12 (65s) | $4,667 | 3,946 | $1.18 | 0 since Oct 6 | 1 (Sep 13) |
| Julie static #6 | $1,683 | 150 | $11.22 | 2 | 1 (Sep 10) |
| Courtney static #3 | $688 | 53 | $13 | 1 | 1 (Sep 16) |
| Courtney video #3 (75s) | $622 | 33 | $19 | 1 | 1 (Oct 28) |
| Courtney static #2 | $564 | 40 | $14 | 0 | 0 |

Julie video buys the cheapest clicks in the account and converts none of them: 3,946 clicks, 0 real checkouts in Adset 2/5. Both remarketing sales came off Courtney. Julie static is the only prospecting ad with real checkouts.

---

## 9. Purchase ledger

| Date | Source | Set / ad | Buyer | Meta credit | Note |
|---|---|---|---|---|---|
| Sep 10 | Meta | Adset 2 v1 · Julie static | woman 45–54 | yes | clean |
| Sep 13 | Meta | Adset 2 v1 · Julie video | man 45–54 | yes | clean |
| Sep 16 | Meta | Adset 4 · Courtney static | woman 55–64 | yes | night of the CAPI/EMQ commits; last credit for 42 days |
| Oct 7 | Pixel (pages.dev) | — | — | **no** | real sale, no ad credited |
| Oct 28 | Meta + pixel | Adset 4 · Courtney video | woman 35–44 | yes | day after the $79 attendee offer went live on pages.dev |
| Oct 31 | Pixel (pages.dev) | — | — | **no** | real sale, no ad credited; 4 days after the offer |

Pixel log reaches back to Oct 6 only; September is Meta-credited only. Real purchases visible: 6. Meta: 4. CRM count: not available (ActiveCampaign down).

---

## 10. Win fast — the plan and the numbers behind it

**Why this plan.** The one audience in this account that buys at scale is Masterclass people. Masterclass set #108814 (IC30/ATC14 warm + purchaser LAL 1% + 2%, buyers excluded) has done **$3,970 → 13 purchases, $305 each, 11 of them in the last 10 days.** Blueprint has spent $0 on those audiences. Two of the three October Blueprint purchases came within four days of the Masterclass attendee offer. Cold interests have had $14,182 and two sales in two months.

**Step 1 — Stop the bleed (today)**
- Pause Adset 2 #108808 (52669013718628) and Adset 5 #108811 (52669048300628). $84/day, 0 real checkouts on $3,383.
- Pause Julie video #12 in every Blueprint set.

**Step 2 — New set: `Blueprint | Masterclass buyers + checkout starters | FB Feed+Reels | W45+`** · $60/day
- Include: `Julie Masterclass | CRM paid buyers 101` (52673824207628) + `Julie campaign IC30 OR ATC14` (52673824370228).
- Exclude: nothing.
- US · women · 45–65+ · FB Feed + FB Reels · mobile only · Advantage audience off.
- Optimization: Purchase, 7d click 1d view.
- Ads: Courtney video #3 (4:5 for Feed, 9:16 for Reels), Courtney static #3. Copy leads with the $79 first payment.
- Benchmark: #108814 does $305/purchase on this audience for Masterclass. Target for Blueprint: first purchase inside 7 days, ≤ $500.

**Step 3 — Turn on `#108779` purchaser lookalike** (52676923495628) · $80/day
- Already inside: LAL 1% Masterclass buyers. Add: `CRM paid buyers 101 | Lookalike 2% US` (52674398835028). Exclude: buyers 101.
- Move into campaign #118148. US · women · 45–65+ · FB Feed + FB Reels · mobile.
- Ads: Courtney video #3, Courtney static #3, Julie static #6.
- Benchmark: same LALs inside #108814 and #108815 produced 36 Masterclass purchases on $15,189.

**Step 4 — Rebuild Adset 4 remarketing** (52666232368428) · $40/day
- Optimization: **Initiate Checkout** until the campaign logs 10+ purchases, then back to Purchase. Purchase optimization on a 6-purchases-in-60-days signal is what starved it.
- Keep: site 30/90d, checkout 30/90d, cart 30/90d. Remove: leads 30/90d, form openers, both video-viewer lists.
- Exclude: buyers 101.
- FB Feed + FB Reels · mobile · women · 45–65+.
- Ads: Courtney video #3, Courtney static #3.

**Step 5 — Measurement**
- Reconnect ActiveCampaign so every pixel purchase gets a CRM row.
- Add the QA device to a Meta exclusion list (the site code excludes it; the ad audiences do not).
- Read on Nov 10 with the same tables. No edits in between.

**Budget after the change:** $180/day vs $223/day now. Expected week 1, on account benchmarks: 2–4 Blueprint purchases, 10+ real checkouts, CPM back under $40. If week 1 shows CPM above $100 on the new sets, the problem is account-level delivery and the next step is a new campaign shell, not more audience edits.

---

## 11. Sources

| Pull | Proves |
|---|---|
| Insights, campaign 52663511211628, daily, Sep 1–Nov 3 | spend/clicks/carts/checkouts/purchases by day; purchase dates |
| Insights, ad set level, daily and weekly, with impressions | the four periods, CPM collapse, paused-set roster |
| Insights, Adset 4, age × gender, daily Sep 15–Nov 3 | QA test-device days and counts; buyer demographics |
| Insights, placement and age × gender, lifetime, live sets | sections 5–6 |
| Insights, hourly_stats_aggregated_by_advertiser_time_zone, Sep 3–Nov 3 and Sep 30–Nov 3 | section 7 |
| Graph API, ad set objects + delivery_estimate | section 4, audience sizes |
| Graph API, custom audiences | buyer list, lookalikes, which sets use them |
| Pixel 1440305917310328 stats by host, event Purchase | real pages.dev purchases Oct 7, 28, 31 |
| GitHub gitteromri-ux/lla-course-checkout commits | Sep 15–16 CAPI/EMQ, Sep 22–25 fixes, Oct 27 offer, Nov 2 consent |
| Masterclass sets #108814 / #108815 insights | lookalike and warm-audience benchmarks |

Charts: `charts/`. Raw JSON pulls on request.
