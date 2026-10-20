# Brand-bidding evidence kit

[中文版](README.zh.md)

Someone is running Google Search ads on your brand. This kit covers what to collect, which route to take, and what to send.

Most brand-bidding complaints get rejected because the paperwork doesn't hold up, not because nothing happened. Typical gaps: the advertiser isn't named, there's no identifying URL, or there's no proof of trademark rights in that country and class. This kit is about getting the paperwork right.

- [`checklist.md`](checklist.md): the fields an accepted complaint contains and where each one comes from
- [`templates/takedown-notice.en.md`](templates/takedown-notice.en.md): a notice to an affiliate, reseller or agency, ready to edit
- [`templates/takedown-notice.zh.md`](templates/takedown-notice.zh.md): the same notice in Chinese

This is not legal advice.

## 1. What Google requires

The acceptance criteria are a single sentence in Google's [trademark policy](https://support.google.com/adspolicy/answer/6118):

> Google will only accept complaints against specific advertisers identified on the basis of their URL(s) within the countries and industries in which trademark owners have demonstrated trademark rights.

That sentence sets three hard requirements. If you miss any one of them, the whole complaint fails.

| Requirement | What it means | What you supply |
|---|---|---|
| specific advertisers | A named advertiser entity | The advertiser's registered name, not "some company selling X" |
| identified on the basis of their URL(s) | Identified by URL | The root domain of the ad's final URL |
| countries and industries … demonstrated trademark rights | Only within the rights you can prove | Registration number, country, Nice class |

Rights holders trip on the third one most often. A mark registered in one country can't restrict ads served in another. A class 25 (clothing) mark can't police class 42 (software) ads. Work out the scope of your own rights first, then scope the complaint to match.

Once a complaint succeeds, the restriction generally applies to the **second-level domain of the final URL as a whole**, not just the one ad you reported. So the field that matters most is the domain. Advertisers swap creatives constantly; changing a domain is expensive.

## 2. The one piece of evidence that decides it

The policy says: *"The trademark must be used in the ad, not only on the ad's landing page."*

If the other side only bought your brand name as a keyword and the ad text is clean, no amount of extra material will get the complaint accepted. A **screenshot of the ad itself**, with the text legible, is the only thing that proves your mark was used in the ad. Take it the moment you find the ad. Google has never published how long ads stay in its public archive, so a record you can see today may be gone next month.

## 3. Collect evidence in three layers

Work from coarse to fine. Each layer answers one question.

1. **The domain: how many are there?** Start from your own brand's root domain and list every advertiser sending paid search traffic to it. That list is your "specific advertisers". Write down the date you looked; it's the timestamp on your evidence.
2. **The advertiser: who are they?** For each suspect, check which other landing domains it advertises. The answer tells you which route to take (section 4):
   - It only promotes your domain → most likely your own agency, reseller or affiliate.
   - It promotes dozens or hundreds of unrelated domains → a media agency or affiliate network buying for many clients. Talking to them directly is often faster than chasing the end client.
   - It promotes its own brand domain → an actual competitor.
3. **The ad: did they cross the line?** Open the individual ad and record its ID, the countries it ran in, its first and last seen dates, and a screenshot. Keep the screenshot, the ad ID and the date you looked together. If one is missing, it becomes your word against theirs.

Google's public ad archive lets you look up a single advertiser's ads. It doesn't answer layer 1: given a domain, which advertisers point ads at it? We built [PPCEye](https://ppceye.com/domain-search) to answer that reverse lookup, but any method that gets you a complete advertiser list will do.

## 4. Pick the route before you collect

| | Google trademark complaint | Affiliate / agency contract |
|---|---|---|
| Applies when | Your mark appears **in the ad text** | They broke your terms, even with clean ad text |
| Core evidence | Screenshot showing the mark in the ad | How long the ads have been running + which domain they point to |
| Needs a trademark registration | Yes, matched to country and class | No |
| Speed | Slow; Google gives at least 7 days' warning before suspension | Fast; one email often stops it |
| Scope | The second-level domain of the final URL | Binds that one partner |

In practice the second route comes up more often. Most brand-term bidding isn't done by competitors. It's done by your own resellers, affiliates and agencies, because your brand terms are the highest-converting traffic they can buy. You don't need Google for that, but you still need evidence, and the useful kind shows intent rather than accident: **how long the ads have been running**. An ad that has been live for 90 days is not a misclick. For how long ads normally survive, see [`research/2026-10-ad-lifespan`](../research/2026-10-ad-lifespan/).

## 5. When not to send anything

Three cases where a complaint will very likely be rejected, and will cost you credibility with whoever receives it:

1. **They only bought the keyword; your mark isn't in the ad text.** Google's policy explicitly does not restrict this.
2. **They are a legitimate reseller or information site.** The policy makes exceptions for pages that mainly sell the trademarked goods or mainly provide information about them.
3. **You have no rights in that country or class.**

In those cases your time is better spent on your own account: improve quality score on your brand campaigns and buy back impression share.

## FAQ

**Can I complain without a registered trademark?**
Not through Google's trademark process. If the other side is your affiliate or agency, the contract route needs no registration.

**Is an ad ID enough without a screenshot?**
No. The record may disappear before you file, and an ID alone can't show your mark was in the ad text.

**They swapped in new ads. Is my old evidence still useful?**
Yes, even more so. A successful complaint applies at the domain level, and older ads show the behaviour has been going on for a while.

**Can I find out how much they spent on my brand terms?**
No. No public source has keyword-level bids or spend; any figure you see is a model's estimate. What holds up is the delivery record: who ran the ads, where they pointed, for how long, and in which countries.

**The advertiser name doesn't match the company I know.**
Google's archive lists advertisers by registered entity name, which is usually the legal name rather than the brand. Starting from the landing domain is more reliable.

---

*Policy quotations come from Google's [trademark policy](https://support.google.com/adspolicy/answer/6118) in the original English (Google states the English version governs enforcement), checked 2026-08-17.*
