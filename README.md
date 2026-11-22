# Technitium DNS — Ad-Verification Provider Blocklist

A public Technitium DNS filter list of ad-verification / measurement / brand-safety provider domains, sourced from the subject of this Reddit post:

**r/nextdns — "Ad verification providers to add to your blocklist"**
https://www.reddit.com/r/nextdns/s/RCvYNCTCSC

## Source extraction status

Automated extraction of the exact URL list from the source Reddit post was **blocked by Reddit's network policy** from this environment — `www.reddit.com`, `old.reddit.com`, the mobile site, RSS feed, JSON API, libreddit mirrors, Wayback Machine, Pushshift/PullPush, Jina reader, DuckDuckGo/Bing search caches, and CORS proxies all returned block pages, captchas, errors, or empty shells. As a result, this repository currently contains a **curated starter set** of well-known ad-verification provider domains rather than a verbatim copy of the post's URLs.

## What to do next (one step)

If you can retrieve the post's URL/domain list (e.g., copy from a logged-in session, screenshot, or text), paste it here or open an issue/PR and I'll swap it in verbatim. Otherwise the curated list below is ready to import as-is into Technitium DNS.

## How to import into Technitium DNS

In Technitium DNS Manager:

1. Go to **Blocklist**.
2. Click **Add new blocklist**.
3. Paste the contents of `ad-verification-providers.txt` (one domain per line, optionally with `0.0.0.0` prefix).
4. Save and enable.

Technitium accepts both bare domains (`doubleverify.com`) and prefixed entries (`0.0.0.0 doubleverify.com`).

## Curated starter list

```
doubleverify.com
adsafeprotected.com
moatads.com
comscore.com
scorecardresearch.com
imrworldwide.com
nielsen.com
adloox.com
adlooxtracking.com
forensiq.com
humansecurity.com
whiteops.com
confiant.com
adform.net
media.net
adometry.com
geoedge.be
pixalate.net
clean.io
```

## Contributing

- Found a domain missing from this list? Open an issue or send a pull request with the domain and source.
- Want it removed? Open an issue.
- This repo is public — please only submit domains you own or have verified belong to ad-verification providers.
