# Blueprint — win-fast plan (Nov 3 2026, 13:40 Israel)

Companion to [README.md](README.md). Everything here is from the live account at the time of writing.

---

## 1. The holistic picture, in numbers

**The CPM problem is account-wide, not Blueprint-specific.**

| Account, daily | Spend | Impressions | CPM | Purchases |
|---|---:|---:|---:|---:|
| Oct 1 | $1,877 | 34,198 | $55 | 0 |
| Oct 3 | $936 | 36,243 | $26 | 2 |
| Oct 4 | $2,240 | 9,194 | $244 | 2 |
| Oct 5 | $3,173 | 7,823 | $406 | 4 |
| Oct 6 | $3,204 | 6,829 | $469 | 8 |
| Oct 7 | $3,140 | 6,808 | $461 | 11 |
| Oct 12 | $3,664 | 7,044 | $520 | 11 |
| Nov 2 | $1,071 | 3,123 | $343 | 1 |

On Oct 4–5 the whole account moved from $26–80 CPM to $400–520 and has stayed at $250–820 since. That is the day the Masterclass campaign scaled to $3k/day on Purchase optimization and Meta locked the account into one expensive high-intent pocket.

**Masterclass sets live in that pocket and still work, because Ad#17 converts.**

| Set | Audience | Size (MAU) | CPM last 3 wks | Purchases / week | Cost per purchase |
|---|---|---:|---:|---:|---:|
| #108816 | 41 interests, 35–65, US, FB Feed + Reels + IG Feed | 88–104M | $680–824 | 16–27 | $284 (Ad#17, 70 purchases) |
| #108817 | same interests, 45–65 | — | $560–640 | 4–16 | $341 (Ad#17, 43 purchases) |
| #108814 | IC30/ATC14 warm + purchaser LAL 1% + 2% | — | $516–658 | 1–9 | $305 |

Ad#17 in #108816: 2,089 clicks → 70 purchases = **3.4% click-to-purchase.**

**Blueprint Adsets 2 and 5 live in the same pocket and lose.** Same 41 interests, same pixel Purchase event, same placements as #108816, 40–47M people. CPM $266–388, 91 clicks, 0 checkouts since Oct 6. They bid against #108816 for the same people and lose on conversion rate. Any new cold Blueprint set lands in that same auction.

**What converts to Blueprint: Masterclass people.** 2 of 3 October Blueprint sales landed within 4 days of the Oct 27 $79 attendee offer. The warm pool: buyer list (CRM paid buyers, 52673824207628), checkout starters IC30/ATC14 (52673824370228), Nov 14 registrants. Small warm lists get delivery within hours.

---

## 2. What 2–3 sales today actually requires

Cold Meta cannot do it today. At $700 CPM, $100 buys ~140 impressions and ~9 clicks; at Blueprint's conversion rate that is zero sales. The only same-day levers:

1. CRM message to the warm pool with the $79 VIP Blueprint offer. At 1–2% response on ~200 buyers + checkout starters + registrants: 2–4 sales.
2. A warm Meta set on the same lists with the same offer and the winning video. First sale expected inside 24–48h at $300–500.

---

## 3. Immediate steps, in order

### Step 1 — CRM blast, now
To: Masterclass buyers + checkout starters + Nov 14 registrants. Copy in section 6. Link: `https://longevitylifeacademy.pages.dev/?offer=MASTERCLASS-VIP&utm_source=crm&utm_campaign=bp-vip`

### Step 2 — Build ONE Blueprint ad from the winning asset
- Videos: `1748787486227637` (square) and `2236898053915469` (vertical), from creative 1444916017846546 (Ad#17).
- Page 1179505785236150 · IG 17841432251901978.
- Same placement customization rules as Ad#17 (vertical → Stories/Reels, square → Feed).
- Link: `https://longevitylifeacademy.pages.dev/?offer=MASTERCLASS-VIP&utm_source=fb&utm_campaign=bp-ad17`
- CTA: Sign Up. Copy in section 5.
- New link = new post, so the Masterclass post's reactions stay on the Masterclass ad. The video and the hook are what carry.

### Step 3 — New warm set, inside the Masterclass campaign shell (52668266203628)
Name: `Blueprint | Masterclass buyers + checkout starters + registrants | FB Feed+Reels+IG Feed | 35-65+`
- Include: 52673824207628 (buyers) + 52673824370228 (IC30/ATC14) + Nov 14 registrants list.
- Exclude: nothing.
- US · all genders · 35–65+ · FB Feed, FB Reels, IG Feed · mobile · Advantage audience off.
- Optimization: Purchase · lowest cost · 7d click 1d view.
- Budget: **$80/day**. Only the Ad#17-Blueprint ad.
- Expect: delivery within the hour; first Blueprint sale inside 24–48h.

### Step 4 — #108816, the 70-purchase set
It is already back in learning (significant edit Nov 2), so a budget change costs nothing.
- Budget $48 → **$120**.
- Add the Ad#17-Blueprint ad as a second ad. Meta will give 60–80% of spend to the cheaper converter (the Masterclass ad). That is fine: the Masterclass sale is the Blueprint funnel, and the Blueprint ad gets its share of a learned, delivering set instead of a starved one.
- Read Nov 6. If the Blueprint ad has under 10% of spend, move it to its own clone of #108816 at $100.

### Step 5 — Blueprint campaign (52663511211628)
- Pause Adset 2 #108808 (52669013718628) and Adset 5 #108811 (52669048300628). $84/day feeding the same auction as #108816 and losing.
- Pause Julie video #12 everywhere.
- Adset 4 #108810 (52666232368428): ads → Ad#17-Blueprint + Courtney video #3. Exclude buyers 52673824207628. Optimization → Initiate Checkout. Placements → FB Feed + FB Reels, mobile. Budget → $40.

**Net budget:** $80 (warm) + $72 (added to #108816) + $40 (Adset 4) = $192/day vs $223 today, moved from the dead auction to the one that works.

---

## 4. GitHub, same hour — repo `gitteromri-ux/lla-course-checkout`

1. Hero on pages.dev says what the ad says: one line under the H1: **"Includes a VIP seat at Julie's live masterclass, November 14, 1 pm ET, with the private 30-minute Q&A."** Same line as a bullet in the includes list.
2. `?offer=MASTERCLASS-VIP` pre-applies the $79 + 4 × $169 schedule (the code already supports MASTERCLASS-VIP), so nobody types a coupon. UTMs pass through to the CRM order.
3. Two-line block next to the price: *The masterclass is one 60-minute session, the taste. The Blueprint is the full 18-week program with your protocol written for you.*
4. One test checkout from the excluded test device → confirm AddToCart → InitiateCheckout → Purchase in Events Manager → ship.

---

## 5. Ad copy

**Primary text**

Five habits got Julie Gibson Clark ranked the world's second-slowest ager in the 2023 Rejuvenation Olympics, ahead of Bryan Johnson. The Blueprint is where she hands you the whole protocol, not the highlights.

Longevity Life Academy Blueprint:
• 18 live weekly sessions with Julie and the faculty, cohorts of 8–15
• Your personal longevity protocol, written for you: nutrition, movement, sleep, daily habits
• Monday or Wednesday cohorts, starting November
• VIP seat at Julie's live masterclass on November 14, 1 pm Eastern, with the private 30-minute Q&A, included

The masterclass is the taste. The Blueprint is the program.

$79 today, then 4 monthly payments of $169. Cohorts are capped at 15.

**Headline:** The Blueprint · 18 weeks with Julie Gibson Clark
**Description:** VIP masterclass seat included · $79 today
**CTA:** Sign Up

---

## 6. CRM message

**Subject:** Your VIP seat is already inside the Blueprint

You reserved a place at Julie's November 14 masterclass. Before Friday, you can turn that seat into the full program.

The Blueprint is 18 live weekly sessions with Julie Gibson Clark and the Longevity Life Academy faculty, in a cohort of 8–15 people, ending with your own written longevity protocol. Your VIP masterclass seat and the private Q&A are included.

Masterclass registrants pay $79 today, then 4 monthly payments of $169 (regular $799 upfront). Cohorts start Monday or Wednesday in November and close at 15.

Claim your place: https://longevitylifeacademy.pages.dev/?offer=MASTERCLASS-VIP&utm_source=crm&utm_campaign=bp-vip

Julie and the LLA team

---

## 7. Read-out schedule

| When | Check | Decision |
|---|---|---|
| +2 h | Warm set delivering (impressions > 0, CPM) | if 0 impressions: audience too small for Purchase opt → switch set to Initiate Checkout |
| +24 h | Warm set: clicks, checkouts, purchases; CRM: opens, clicks, sales | — |
| Nov 6 | #108816: spend share of the Blueprint ad | < 10% → clone #108816 for Blueprint at $100 |
| Nov 10 | Full re-read with README tables | scale what sold, kill what did not |
