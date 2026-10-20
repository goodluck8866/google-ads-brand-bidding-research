# How long does a Google Search ad last?

[中文版](README.zh.md) · Data cutoff: sample drawn 2026-10-12 · [Methodology](../../METHODOLOGY.md)

![Share of new Google Search ads still running](survival.svg)

## Short answer

- **Half of new Google Search ads are gone within about four months** (median 121 days).
- About **1 in 13 doesn't survive a week**, and **1 in 4 doesn't survive a month**.
- Only **about 40% are still running after six months**.
- Yet **half of the ads running today have been live for nearly two years** (median 686 days).

Both statements are true at once. Most new ads die quickly, and the few that survive go on running for years. Those survivors fill most of the ad slots you actually see.

## Two questions that look the same

"How long do ads run?" can mean two different things, and they give very different answers.

**1. How old are the ads running right now?** We took every ad in the sample still being served on or after 2026-09-01 ([`age_of_ads_running_now.csv`](data/age_of_ads_running_now.csv)):

| Running for | Share |
|---|---|
| 30 days or less | 3.5% |
| 90 days or less | 9.4% |
| Over 1 year | 70.1% |
| Over 2 years | 47.9% |

The median is 686 days. A further 8.3% have a first-seen date at the very start of Google's archive (about 2021-10-25), so they are older still.

**2. How long does a new ad survive?** That 686-day figure doesn't answer this. On any given day, the ads you see lean towards long-lived ones: a three-day ad only shows up if you search during those three days, while a two-year ad can turn up any day. It's the same reason a hospital ward on any given day is full of long-stay patients.

To answer the second question, you have to follow a group of ads from the day they launch. We took the 71,730 ads in the sample first seen between January and July 2026. Many of them are still running, so we can't yet say how long they'll last. We used a survival analysis (Kaplan–Meier) to handle that: an ad that is still running counts as "survived at least this long" ([`new_ad_survival.csv`](data/new_ad_survival.csv)).

| Days after launch | Still running |
|---|---|
| 3 | 97.3% |
| 7 | 92.4% |
| 14 | 85.4% |
| 30 | 74.7% |
| 60 | 63.4% |
| 90 | 55.7% |
| 180 | 40.2% |

To check this isn't one odd month, we split the launches into four periods. Seven-day survival ranges from 89.5% to 93.4% across them, and 30-day survival from 64.6% to 77.5% ([`survival_by_launch_period.csv`](data/survival_by_launch_period.csv)).

## Bigger advertisers' ads last longer

| Advertiser (by ads in sample) | Median lifespan | 30-day survival | 90-day survival |
|---|---|---|---|
| 1–9 ads | 64 days | 65.9% | 43.0% |
| 10–99 ads | 67 days | 65.0% | 44.5% |
| 100+ ads | 185 days | 84.4% | 67.9% |

Grouping by landing domains points the same way: advertisers pointing at a single domain have a median of 91 days; those pointing at five or more have 184 days ([`survival_by_advertiser_size.csv`](data/survival_by_advertiser_size.csv), [`survival_by_landing_domains.csv`](data/survival_by_landing_domains.csv)).

Many of the large, many-domain advertisers are platforms, agencies and big retailers that generate ads in bulk per product or per client and rarely touch them again. Small advertisers are mostly testing, swapping copy, landing pages and offers, so their ads come and go quickly.

## What this is useful for

- **Reading a competitor's ads.** Search ads are paid per click, and nobody keeps paying for an ad that loses money. An ad that has run past six months has already outlasted about 60% of ads launched alongside it. Long-running ads are the ones the market has tested.
- **Brand-bidding evidence.** An ad on your brand that has run for 90 days has already outlasted nearly half of the ads launched alongside it. That makes "it was a mistake" hard to argue. See the [evidence kit](../../evidence-kit/).
- **Your own account.** If you're a small advertiser, most of your ads not lasting two months is normal. If you've run for six months and none has settled in, that's worth a closer look.

## Caveats

- **The real picture is probably harsher.** We collect in batches, so an ad that launched and stopped between two collections may never have been seen. The "died within a week / month" shares are lower bounds.
- **"Run duration" is first seen to last seen.** The ad may have paused in between.
- **Ads launched in 2025 or earlier were left out of the survival estimate.** Because of how they were collected, those older groups lean towards long-lived ads.
- **No spend data.** Google's archive has none, so nothing here says how much any ad cost or earned.

## How the sample was drawn

400,000 Google Search ads, sampled evenly across the full range of ad IDs on 2026-10-12. An ad counts as still running if it was seen within 3 days of our latest collection of it. Advertiser size and landing-domain counts are measured within the sample.

## Cite this

> PPCEye (2026). *How long does a Google Search ad last?* Sample of 400,000 ads from Google's public ad archive, drawn 2026-10-12. https://github.com/goodluck8866/google-ads-brand-bidding-research

Licensed CC BY 4.0. Reuse freely, with attribution and a link.
