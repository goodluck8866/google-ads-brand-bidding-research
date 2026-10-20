# Methodology

[中文版](METHODOLOGY.zh.md)

## Where the data comes from

All the data in this repository comes from **Google's official public ad archive**, the Google Ads Transparency Center. Google runs it and anyone can browse it for free. We don't buy third-party datasets, collect browsing behaviour, or model anything from clickstream panels. Every ad behind these figures is a record you could look up yourself in Google's interface.

That also sets the limits. **If the archive doesn't have it, neither do we.** In particular, the archive has no spend, no bids and no keywords, so nothing in this repository says anything about them.

## What the fields mean

| Field | Meaning | Caveat |
|---|---|---|
| First seen | The first date Google's archive shows the ad being served | The archive only goes back to about **2021-10-25**. An ad showing that date may be older. |
| Last seen | The most recent date the archive shows the ad being served | |
| Run duration | Last seen − first seen + 1, in days | Counts from first to last appearance. The ad may have been paused in between. |
| Advertiser | The entity name Google lists the ad under | Usually the legal company name, not the brand |
| Landing domain | The root domain the ad points to | Search ads often don't expose the final URL as a field. Ours come from the domain printed on the ad. |

## How we collect it

We query the archive by advertiser and by landing domain and store every ad we see. We collect in batches rather than continuously. That matters for one thing in particular: **an ad that started and stopped between two of our visits may never be recorded.** Those missed ads are almost all short-lived, so any figure here about how many ads die young is a lower bound.

## How the figures are produced

- **Samples, not totals.** Each study says how its sample was drawn and how big it was.
- **Every figure has a cutoff date**, given at the top of each study. We don't update published figures in place. A new analysis gets a new dated folder.
- **Per-advertiser or per-domain detail is not published here.** Studies report shares and distributions only.

## Who did this

[PPCEye](https://ppceye.com) (竞眼) is a Google Ads competitor research tool built on the same archive. Questions or corrections: open an issue, or email info@ppceye.com.
