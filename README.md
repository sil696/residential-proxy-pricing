# residential proxy network: What It Actually Is, What It Costs per GB, and How to Pick One Without Overpaying

People search this term at three different moments. Some are trying to work out what the phrase even means. Some already know, and are trying to figure out why their datacenter proxies keep dying on the same handful of sites. The rest are holding a pricing page open in another tab, comparing cost per gigabyte.

The gap between cheapest and most expensive here is roughly tenfold. Premium networks price residential traffic at $5–15 per GB. Budget networks run between about $0.68 and $3 per GB. It's the same technical idea both times, so the useful question isn't "which network is best" — it's what you actually get at each price point, and which billing model matches the job you're running.

## What a residential proxy network actually is

A residential proxy routes your request through a device sitting on a home broadband connection, using the IP address that a consumer ISP assigned to that line. Server-side, you look like a person on Comcast, PCCW or whatever the local carrier is, rather than a rented server in Ashburn.

The network behind that is a peer model. The provider installs software on participants' devices, routes commercial traffic through their connection while the device is idle, and pays them something for it — an app, a service, or cash. You pay the provider per gigabyte or per IP.

This is why residential IPs survive where datacenter IPs don't. Anti-bot systems check the ASN first, and datacenter IPs belong to AWS, Google Cloud and similar ranges that can be blocked in bulk. Residential IPs sit inside consumer ISP ranges. Blocking those in bulk means blocking paying customers, so sites don't.

Worth being precise about the limit of that. Switching to residential IPs removes one signal — the IP reputation check. It doesn't defeat Cloudflare, Akamai Bot Manager or Imperva on its own, because those also look at TLS fingerprints, HTTP/2 settings, cookie behaviour and JavaScript execution. Residential proxies raise your success rate. They don't make you invisible, and any provider promising otherwise is selling you a story.

## Four numbers that decide whether a network is worth the money

Pool size is the number everyone quotes and the least useful on its own. These four tell you more:

1. **Price per GB versus price per IP.** Not just the rate — the metering model. A $0.68/GB plan and a $0.24/IP plan can cost the same for your workload, or ten times different, depending on how much data each request moves.
2. **Targeting granularity.** Country-only targeting is not the same product as country, state, city, ZIP and ISP. If you're checking local pricing or ad placement, city level is the floor.
3. **Session control.** Rotate per request, hold a sticky session for twenty minutes, or both. Some workflows break without one of these.
4. **What happens when an IP is dead.** Residential IPs drop. The question is whether you eat the loss or get a replacement.

That last one separates providers more than pool size does. 9Proxy runs a 60-second replacement policy: if a forwarded IP doesn't work, you report it and the IP goes back on your balance. No refunds — the service is non-refundable by their own stated policy — so the replacement credit is the actual safety net.

## The billing model question nobody explains properly

Most residential providers only sell bandwidth. You buy gigabytes, you generate as many endpoints as you want, and you pay for what you consume. That's fine for rotation-heavy work like SERP tracking or price monitoring, where each request is small.

It's a bad fit when you're pushing a lot of data through a small number of IPs. Watching a video, running a long scraping session against a heavy site, or holding a login open across a large transfer can burn gigabytes you didn't plan for.

Pay-per-IP flips that. You buy a fixed number of residential IPs, each with unlimited bandwidth during its lifetime, and the metering stops mattering. 9Proxy sells both models, plus bundles that mix them, which is unusual — most budget providers pick one and stay there.

👉 [Check the current 9Proxy packages and pick a billing model](https://bit.ly/9-Proxy)

The practical trade-off:

- **Per-IP** suits fixed sessions, account-based work, browser profiles that need to stay coherent, and anything where traffic per IP is unpredictable. Each activated IP stays alive from a few hours up to around 24 hours. Unused IP balance never expires, so you can stock up without watching a clock.
- **Per-GB** suits high rotation, many endpoints, low data per request, and cloud setups. Authentication runs on username/password or an IP whitelist, straight from the dashboard — no local software needed. Validity is 180 days, unlimited on Enterprise.

## What 9Proxy's network looks like today

Vendor-reported figures: over 20 million residential IPs across 90+ countries, targeting down to country, state, city, ZIP (US) and ISP level, HTTP/HTTPS and SOCKS5 support, plus an API for automated provisioning. They advertise 99.95% uptime and 24/7 human support rather than chatbots.

Two operational details are more interesting than the headline numbers. The Today List lets you reuse an IP you already forwarded within 24 hours without spending another IP from your balance, as long as it's still online — which quietly cuts consumption for work that repeats the same targets. And Proxy2Web now serves IP-based proxies from the browser with username/password auth, removing the old requirement to install the Windows desktop client.

On pricing, there was one event worth knowing about. 9Proxy held its rates flat for three years, then announced its first adjustment effective 1 June 2026. IP-based and bundle prices went up; GB-based prices did not. Concretely, the entry IP pack moved from $20 to $24, and the smallest bundle from $25 to $30. GB pricing is unchanged, which is why the per-GB tiers below are the same numbers people have been quoting since the GB product launched.

## Every package currently on the pricing page

All three product lines are balance purchases rather than subscriptions. There's no monthly fee attached to any of them.

### Residential proxies by IP — unlimited bandwidth per IP

| Package | Price per IP | Total | Traffic | Purchase |
| --- | --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | Unlimited per IP | [Start with 100 IPs](https://bit.ly/9-Proxy) |
| 500 IPs | $0.144 | $72 | Unlimited per IP | [Get the 500 IP pack](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus IPs | $0.084 | $126 | Unlimited per IP | [Buy 1,500 IPs with bonus](https://bit.ly/9-Proxy) |
| 2,500 IPs | $0.084 | $210 | Unlimited per IP | [Order 2,500 IPs](https://bit.ly/9-Proxy) |
| 5,000 IPs | $0.072 | $360 | Unlimited per IP | [Get 5,000 IPs](https://bit.ly/9-Proxy) |
| 15,000 IPs | $0.048 | $720 | Unlimited per IP | [Buy the 15,000 IP tier](https://bit.ly/9-Proxy) |
| 25,000 IPs | $0.035 | $863 | Unlimited per IP | [Order 25,000 IPs](https://bit.ly/9-Proxy) |
| 50,000 IPs | $0.029 | $1,438 | Unlimited per IP | [Get the 50,000 IP tier](https://bit.ly/9-Proxy) |
| 100,000 IPs | $0.023 | $2,300 | Unlimited per IP | [Buy 100,000 IPs wholesale](https://bit.ly/9-Proxy) |
| 200,000 IPs | $0.021 | $4,140 | Unlimited per IP | [Order 200,000 IPs](https://bit.ly/9-Proxy) |
| 500,000 IPs | $0.018 | $8,625 | Unlimited per IP | [Get the 500,000 IP tier](https://bit.ly/9-Proxy) |

Billing period: one-off balance purchase. Unused IP balance does not expire.

### Residential proxies by GB — unlimited endpoints

| Package | Price per GB | Total | Validity | Purchase |
| --- | --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days | [Buy the 5 GB pack](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | $2.10 | $105 | 180 days | [Get 55 GB](https://bit.ly/9-Proxy) |
| 100 GB | $1.50 | $150 | 180 days | [Order 100 GB](https://bit.ly/9-Proxy) |
| 200 GB | $1.00 | $200 | 180 days | [Buy 200 GB](https://bit.ly/9-Proxy) |
| 1,000 GB | $0.80 | $800 | 180 days | [Get 1,000 GB](https://bit.ly/9-Proxy) |
| 2,000 GB | $0.75 | $1,500 | 180 days | [Order 2,000 GB](https://bit.ly/9-Proxy) |
| 3,000 GB (Enterprise) | $0.72 | $2,160 | Unlimited | [Ask about Enterprise bandwidth](https://bit.ly/9-Proxy) |

The Enterprise tier keeps the same network but removes the validity clock and adds team controls: one owner plus up to five members, shared non-expiring bandwidth, per-member traffic limits and activity logs. Larger Enterprise commitments price down to around $0.68 per GB.

Billing period: one-off balance purchase with expiry on standard GB packs, no expiry on Enterprise.

### Bundle packages — IPs and bandwidth together

| Package | Configuration | Total | Validity | Purchase |
| --- | --- | --- | --- | --- |
| Starter Bundle | 100 IPs + 5 GB | $30 | 180 days on traffic | [Buy the Starter Bundle](https://bit.ly/9-Proxy) |
| Popular Bundle | 1,500 IPs + 50 GB | $180 | 180 days on traffic | [Get the Popular Bundle](https://bit.ly/9-Proxy) |
| Pro Bundle | 5,000 IPs + 500 GB | $720 | 180 days on traffic | [Order the Pro Bundle](https://bit.ly/9-Proxy) |

Billing period: one-off purchase. Individually, the Starter Bundle's contents would list at $24 + $15; bundling takes the edge off that.

## Reading the pricing table like someone who intends to use it

The 100 IP pack at $24 works out to $0.24 per IP, which is the most expensive per-unit rate on the page. It's a test tier, and it's fine as one — you're buying information about whether the network gets through on your targets before you commit real money.

The first genuine break comes at the 1,000 + 500 tier. You're paying $126 for 1,500 IPs, which is $0.084 each, and that's roughly a third of the entry rate. If your testing went well, that's the natural second purchase.

On the bandwidth side, the arithmetic is blunter. A 5 GB pack at $3.00/GB is a $15 experiment. Move to 200 GB and you're at $1.00/GB, so the same budget buys three times as much traffic. Anyone consuming more than a few gigabytes a month should skip straight past the small packs.

The bundle that makes sense depends on whether your workload is mixed. If half your tasks need a persistent IP and half need rapid rotation, $180 for 1,500 IPs plus 50 GB is cheaper than buying the two separately at list. If your workload is uniformly one or the other, the bundles are just a convenience, not a saving.

One editorial judgement, based on the pricing structure rather than any testing: if you're running a single browser profile per account with steady browsing, per-IP is the cheaper model. If you're firing thousands of small requests and rotating every time, per-GB wins. People usually overpay by picking the model that matches their mental picture of proxy work rather than their actual traffic pattern.

## How you connect

Setup is short:

1. Register an account — 9Proxy uses invite-code based sign-up, which is what the link above carries.
2. Buy an IP pack, a GB pack, or a bundle.
3. Choose an access method. The Proxy Program is a desktop client (Windows, Mac) that routes traffic at the OS level, so applications with no native proxy settings still work. Proxy2Web needs no install and authenticates with username/password. GB-based proxies run straight from the dashboard, using username/password or an IP whitelist.
4. Set targeting and session mode — country, state, city, ZIP or ISP, and sticky versus rotating.
5. Generate endpoints and export the list as .txt or .csv. The dashboard also provides code samples, and the API handles provisioning if you're automating rather than clicking.
6. For mobile workflows, ProxyHub Lite runs on individual devices and ProxyHub Pro manages many devices from one place.

## The limitations, stated plainly

Residential IPs are not durable assets. An IP-based proxy from 9Proxy stays online somewhere between a few hours and around 24 hours, and it dies when the underlying home user disconnects or changes networks. That's inherent to residential pools, not a defect specific to this provider — reviewers have flagged it as the most common complaint, and 9Proxy's own support replies tell those users they'd be better served by static ISP proxies for long sessions. If your workflow needs one IP for a week, this is the wrong product category.

The refund policy is compensation-based, not money-back. Dead IPs get replaced within 60 seconds of reporting. Money doesn't come back.

IP-based proxies historically required the desktop app, which is awkward on tablets or locked-down machines. Proxy2Web largely fixes that.

Pool size is modest next to the giants. Bright Data's own documentation describes a residential network of 400M+ IPs; 9Proxy advertises 20M+, which is about a twentieth of that. Smaller pools mean faster IP reuse on popular targets, and one 2026 comparison estimated 9Proxy's success rate at 95%+ on lightly protected sites but 85–92% on moderately protected ones — below what mid-market providers claim on the same targets. Nobody should be surprised by that at this price.

Reviews are genuinely mixed and worth reading rather than skimming. The positive ones cluster around budget use cases — multi-account management, streaming access while travelling, scraping at moderate scale. The critical ones tend to be about the same IP-lifetime issue described above. Several public listings still quote older pool and price figures, so treat any number you see outside the pricing page as stale.

Finally, specifics this network doesn't cover: mobile 4G/5G IPs, datacenter proxies (still listed as coming soon), and reliable streaming access on services with aggressive residential-proxy detection, which one independent review flagged as a weak point.

## Who this fits

9Proxy makes most sense for budgets that are real constraints: high-volume collection where traffic per request is small, multi-account setups that need one clean IP per profile, SERP and ad verification across regions, and resellers who buy in bulk and repackage. Above the published tiers, they run wholesale pricing for reseller inventory and quote discounts for large orders, with reseller and affiliate tracks on top.

It fits badly if you need static IPs that survive for weeks, mobile carrier IPs, or enterprise SLAs with contractual guarantees.

👉 [Compare the plans and start with the tier that matches your workload](https://bit.ly/9-Proxy)

## Short answers to the questions people actually ask

**Is using a residential proxy network legal?** In most countries, using one is legal. What matters is what you do through it and whether that violates the target site's terms — scraping public pages and violating a ToS are different problems, and neither is solved by the proxy.

**Why do datacenter proxies get blocked when residential ones don't?** ASN ownership. Datacenter IPs belong to cloud providers whose ranges are published and easy to block wholesale. Residential IPs belong to consumer ISPs, where bulk blocking would catch real customers.

**What's the cheapest way to test one?** The 5 GB pack at $15 gives you the full network with minimal commitment. 9Proxy also offers limited trials for new users, subject to availability, requested through support — so don't plan a project around getting one.

**Do unused IPs expire?** No. IP-based balance stays until you use it. GB packs hold for 180 days, and Enterprise bandwidth doesn't expire at all.

**Can you pay with crypto?** Yes — USDT, BTC, ETH, LTC, DOGE and others, alongside cards, bank cards, Alipay, Apple Pay and Google Pay. Some payment methods add a bonus, typically around 5% extra credit.

**Is the 20M+ figure verified?** No. It's the vendor's own claim, as are the 99.95% uptime and 90+ country coverage numbers. Run your own targets for a week before deciding how much of it you believe.
