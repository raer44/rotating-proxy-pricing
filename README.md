# Rotating Proxy: Sticky vs Rotating Sessions, Real Prices, and How to Set Rotation Without Burning Your Budget

Type "rotating proxy" into a search box and you probably want one of four things: a plain explanation of how IP rotation works, help choosing between sticky and rotating sessions, a realistic price per IP or per GB, or a provider that won't hand you a pool that's already blacklisted. Most pages answer one of those and skip the rest.

This piece covers all four, using 9Proxy's published residential plans as the concrete price reference, because their two billing models map almost exactly onto the two ways people buy rotation: paying per IP with unlimited traffic, or paying per gigabyte and rotating as much as you like.

## What a rotating proxy actually does

A rotating proxy gives you one endpoint that hands out a different exit IP over time. Three common patterns:

- **Per-request rotation.** Every HTTP request leaves from a new IP. Standard for scraping search results, price pages, and anything where you're firing thousands of small, independent calls.
- **Sticky sessions.** The same IP is held for a configurable window (5 minutes, 30 minutes, an hour) before it swaps. Needed for logins, multi-step forms, carts, and anything with a session cookie.
- **Timer-based rotation on ports.** The IP attached to a local port changes on a schedule. This is how most desktop-app proxy tools work, including 9Proxy's IP-based plans.

The reason rotation matters isn't mystery. Sites count requests per IP, fingerprint browser behaviour, and rate-limit. One IP doing 5,000 requests in ten minutes gets throttled or blocked; the same volume spread across 500 residential IPs looks like ordinary traffic. Rotation is what keeps those numbers per-IP low.

What most guides gloss over: **your rotation interval and session mode affect success rate far more than the size of the pool you bought.** A 20-million-IP network won't save you if you're holding one IP for a 40-minute scraping run on a site that bans at minute five. The reverse is also true, a medium pool with sensible rotation settings will outperform a giant one with careless ones.

## Sticky vs rotating: how 9Proxy splits the two

9Proxy runs two separate residential systems, and they behave differently enough that the choice matters before price.

On **Residential Proxy by GB**, rotation lives in the session string. You pick a country, state, city, ZIP or ISP in the dashboard, generate as many endpoints as you want, and choose the session mode: **rotating** gives you a fresh IP each request or session, **sticky** holds one IP for however many minutes you configure. Authentication is username and password, or IP allowlisting if you'd rather skip credentials. No desktop app needed.

On **Residential Proxy by IPs**, there's no natural rotation. You get a fixed set of residential IPs with unlimited bandwidth, and each one lives anywhere from a few hours to about 24 hours. The desktop app forwards local ports to those IPs, so rotation comes from the **Auto Rotation Proxy** feature, which swaps IPs on active ports at a set interval. You can scope it to all ports or only selected ones, and schedule it to run only during your working hours, which stops idle rotation from eating capacity.

Two details from 9Proxy's own documentation are worth internalising:

> Each automatic rotation consumes a new IP from your available pool, and the vendor advises against intervals shorter than 30 seconds because connections need time to stabilise before switching.

That single line is the difference between a $24 IP pack lasting a month and lasting a day. Rotating every 10 seconds across 20 ports drains IPs at a rate most people don't budget for.

## Per-IP or per-GB: which one suits a rotation-heavy workload

This is the decision that actually moves your bill.

**Per-IP (unlimited bandwidth)** is built for workloads where you want a small number of stable identities and you push a lot of data through them. One IP can move 50 GB and the price doesn't change. The catch is that rotating consumes IPs, so high-frequency rotation is expensive here.

**Per-GB** is billed by traffic, and rotation is effectively free, since endpoint generation doesn't cost anything. If your job is 200,000 tiny requests that rotate constantly and each response is a few kilobytes, per-GB wins comfortably.

A rough rule that holds up in practice: **if your rotation is frequent and your payloads are small, buy GB. If your sessions are long and your transfer volume is high, buy IPs.** Bundle packages exist for people running both patterns in the same account.

## All 9Proxy plans and prices

9Proxy adjusted IP-based and bundle pricing on 1 June 2026, and left GB-based pricing untouched. What follows is the published structure across the whole pricing page. Confirm the live figure at checkout, since a pay-as-you-go balance system can shift.

**Residential proxies by IP — pay per IP, unlimited bandwidth per IP. Unused IPs never expire.**

| Package | IPs you receive | Price | Effective cost | Buy |
| --- | --- | --- | --- | --- |
| 100 IPs | 100 | $24 | $0.24/IP | [Start with 100 IPs](https://bit.ly/9-Proxy) |
| 500 IPs | 500 | $72 | $0.144/IP | [500 IP package](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus | 1,500 | $126 | $0.084/IP | [1,000 + 500 bonus IPs](https://bit.ly/9-Proxy) |
| 2,500 IPs | 2,500 | $210 | $0.084/IP | [2,500 IP package](https://bit.ly/9-Proxy) |
| 5,000 IPs | 5,000 | $360 | $0.072/IP | [5,000 IP package](https://bit.ly/9-Proxy) |
| 15,000 IPs | 15,000 | $720 | $0.048/IP | [15,000 IP package](https://bit.ly/9-Proxy) |
| 25,000 IPs | 25,000 | $863 | $0.035/IP | [25,000 IP package](https://bit.ly/9-Proxy) |
| 50,000 IPs | 50,000 | $1,438 | $0.029/IP | [50,000 IP package](https://bit.ly/9-Proxy) |
| Business 100,000 IPs | 100,000 | $2,300 | $0.023/IP | [100,000 IP business tier](https://bit.ly/9-Proxy) |
| Business 200,000 IPs | 200,000 | $4,140 | $0.021/IP | [200,000 IP business tier](https://bit.ly/9-Proxy) |
| Business 500,000 IPs | 500,000 | $8,625 | $0.018/IP | [500,000 IP business tier](https://bit.ly/9-Proxy) |

**Residential proxies by GB — pay per gigabyte, unlimited endpoints, sticky or rotating.**

| Package | Price | Effective cost | Traffic validity | Buy |
| --- | --- | --- | --- | --- |
| 5 GB | $15 | $3.00/GB | 180 days | [5 GB pack](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | $105 | $2.10/GB | 180 days | [50 GB + 5 GB bonus](https://bit.ly/9-Proxy) |
| 100 GB | $150 | $1.50/GB | 180 days | [100 GB pack](https://bit.ly/9-Proxy) |
| 200 GB | $200 | $1.00/GB | 180 days | [200 GB pack](https://bit.ly/9-Proxy) |
| 1,000 GB | $800 | $0.80/GB | 180 days | [1,000 GB pack](https://bit.ly/9-Proxy) |
| 2,000 GB | $1,500 | $0.75/GB | 180 days | [2,000 GB pack](https://bit.ly/9-Proxy) |
| Enterprise 3,000 GB | $2,160 | $0.72/GB | No expiry | [3,000 GB Enterprise](https://bit.ly/9-Proxy) |
| Enterprise 6,000 GB | $4,200 | $0.70/GB | No expiry | [6,000 GB Enterprise](https://bit.ly/9-Proxy) |
| Enterprise 10,000 GB | $6,800 | $0.68/GB | No expiry | [10,000 GB Enterprise](https://bit.ly/9-Proxy) |

**Bundle packages — IPs and traffic in one purchase.**

| Bundle | Includes | Price | Buy |
| --- | --- | --- | --- |
| Starter Bundle | 100 IPs + 5 GB | $30 | [Starter Bundle](https://bit.ly/9-Proxy) |
| Popular Bundle | 1,500 IPs + 50 GB | $180 | [Popular Bundle](https://bit.ly/9-Proxy) |
| Pro Bundle | 5,000 IPs + 500 GB | $720 | [Pro Bundle](https://bit.ly/9-Proxy) |

Bundled traffic is valid for 180 days. Enterprise plans add unlimited data validity, team mode for one owner plus up to five members, per-member traffic controls, activity logs, and VIP support.

A few things worth reading off that table. The cheapest advertised rate is **$0.68/GB**, but you only reach it at 10,000 GB. At the entry end, 5 GB costs $15, which is $3.00/GB, more than four times the floor. If you're testing rotation for the first time, that gap is the argument for a 50 GB pack rather than a 5 GB one. On the IP side, the well-known sweet spot is the **1,000 + 500 bonus at $126**, where per-IP cost drops below nine cents without a five-figure commitment.

## What you're actually rotating over

Beyond the billing structure, the network itself is 20 million-plus residential IPs across more than 90 countries, with targeting down to country, state, city, ZIP code, and ISP. Both HTTP/HTTPS and SOCKS5 are supported, which matters if you're feeding proxies into antidetect browsers like AdsPower or Dolphin Anty, or into Scrapy and plain `requests` calls.

The GB dashboard includes a proxy generator with text and CSV export plus ready-made code samples, which cuts out the "copy host:port:user:pass by hand" ritual. You can create sub-users and share codes, or skip credentials entirely with an IP allowlist. Payment options cover cards, crypto including USDT, BTC, ETH, LTC and DOGE, plus Alipay, Apple Pay and Google Pay.

New accounts can request a limited trial, subject to availability. 9Proxy's own partner posts describe it as a small starter allocation for testing rather than an open free tier, so don't plan a production run around it.

## The reliability question worth asking before you top up

This is the part most affiliate write-ups skip, and it's the part that matters if you're about to put a year of budget into one provider.

Third-party trackers documented a service disruption starting 28 June 2026, when the site, dashboard and desktop app stopped responding and prepaid balances became inaccessible. 9Proxy acknowledged a "service disruption" on its Facebook page and BlackHatWorld seller account, said the team had identified an unexpected issue, and gave no cause or restoration date. ProxyStats.io, which does not sell a 9Proxy alternative, reported the site responding again around 15 July and explicitly rejected the "seized by law enforcement" story that circulated, pointing to the domain's ordinary registrar lock and unchanged Cloudflare nameservers.

Reports since then are mixed and worth reading carefully. ProxyUniverse, which markets competing providers, published an update on 14 August saying traffic-based (GB) plans had been restored and verified through its own reseller channel while IP-based plans were still under maintenance with no confirmed date. Independent status monitors have shown the site reachable through September 2026, with some intermittent gaps. 9Proxy has not published a root cause.

Two honest conclusions follow. First, if you're buying for production, test with the smallest package that lets you validate rotation and success rate against your actual targets, then scale. Second, a chunk of the "9Proxy is dead, use X instead" content out there is written by sites selling X. Weigh it accordingly.

The longer-running signal is more encouraging: Trustpilot rates 9Proxy "Excellent" at 4.6 out of 5, with reviewers consistently mentioning stable residential IPs, working integrations with Dolphin Anty and AdsPower, and an IP replacement policy for dead addresses. Read that with the usual caveat that the review set skews toward late 2024. One reviewer also complained about being refused a refund after buying, and about expecting a different proxy type than residential. Read the plan description before you pay.

## Picking a plan by workload

Concrete pairings, based on the published structure:

- **Single scraper, moderate volume, frequent rotation.** The 50 GB + 5 GB pack at $105. Rotation is free, and at $2.10/GB you're not paying entry-tier rates.
- **Antidetect browser profiles for multi-accounting.** The 100 IP pack at $24, or 500 IPs at $72 if you're running several clients. Sticky behaviour is what you want here, one IP per profile, recycled when the IP dies.
- **SEO rank tracking across cities.** GB-based, because per-city targeting with `session` parameters is rotation work, and you'd rather not count IPs. Start at 100 GB for $150.
- **Team with mixed needs.** The Popular Bundle at $180, or the Pro Bundle at $720 if IPs and traffic both run hot.
- **High-volume scraping on stable identities.** 5,000 IPs at $360 with unlimited bandwidth. Set the Auto Rotation Proxy to 30 seconds or longer and schedule it only during active hours.
- **Industrial-scale operations.** Business IP tiers from 100,000 IPs upward, or Enterprise GB with no expiry and team controls.

## Quick answers

**Is "rotating proxy" the same as "rotating residential proxy"?** Not quite. Rotation describes the behaviour; the IP source describes the pool. Rotating datacenter proxies are cheap and fast but land on blocklists quickly. Rotating residential proxies cost more (or bill per GB) and survive anti-bot checks better. 9Proxy's pool is residential on both models.

**Does rotation slow things down?** Switching IPs adds a small connection-setup cost, and residential routes are slower than datacenter ones. Rotating every 100 seconds usually costs less performance than rotating every two seconds, for the same reason 9Proxy tells users not to go under 30 seconds.

**Are free rotating proxy lists worth using?** Public lists are shared by hundreds of people, so the IPs are already burnt by the time you use them, and you have no idea who's operating the exit node. Fine for a one-off test, bad for anything involving credentials or client work.

**Do unused balances expire?** Unused IPs never expire. GB traffic lasts 180 days on standard plans and never expires on Enterprise.

**Do I need the desktop app?** Only for IP-based plans; they route through local port forwarding. GB-based plans run entirely from the dashboard.

**Is there a discount?** 9Proxy runs a partner program that advertises a 5% discount for users who sign up through a referral. The registration link used throughout this article is a referral link, so that discount is what you'd get on top of the published rates, which are otherwise a flat, top-up-based system rather than a monthly subscription.

**Can I get a refund?** The published emphasis is on replacing IPs that fail rather than refunding money, and one Trustpilot reviewer reports being refused. Start with a small top-up and the question stops mattering much.

If you're rotating for the first time, the sensible sequence is: pick a small package, test the session mode and interval against your real target sites, then buy volume once the success rate holds. Rotation settings are the lever, the pool size is just insurance.

👉 [Sign up and set your first rotating session](https://bit.ly/9-Proxy)
