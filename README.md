# Technitium DNS — Ad-Verification / Anti-Adblock Provider Blocklist

A public Technitium DNS filter list of ad-verification, anti-adblock, and bot-detection provider domains, extracted from this Reddit post:

**r/nextdns — "Ad verification providers to add to your blocklist"**
https://www.reddit.com/r/nextdns/comments/1y1u6af/ad_verification_providers_to_add_to_your_blocklist/

## Source & credit

The domains were shared in the post comments by Reddit users **u/hthouzard** and **u/xxOrdulu52xx** (the latter's list originated from a Gemini-assisted search for well-known anti-adblock domains). This repo packages them verbatim as a Technitium-compatible blocklist. Entries shown as `*.domain` in the post are included here as bare domains, which Technitium blocks for the domain and all subdomains.

## Contents

`ad-verification-providers.txt` — deduplicated domain list, grouped by category:

- **Ad verification / measurement**: doubleverify.com, adloox.com, adsafeprotected.com, integralads.com, pixalate.com, geoedge.com, confiant.com, confiant-integrations.net, humansecurity.com, fraudlogix.com, impact.com, trackdesk.com, cleartrust.cc, apphrbr.com, clickcease.com, cheq.ai, addefend.com, def-platform.com, detectadblock.com
- **Anti-adblock / ad recovery / paywall messaging**: btloader.com, blockthrough.com, pagefair.com, pagefair.net, uponit.com, adback.co, instartlogic.com, fundingchoicesmessages.google.com, contributor.google.com, html-load.com, html-load.cc, css-load.com, content-loader.com, video-loads.com, error-report.com
- **Bot / anti-fraud detection**: perimeterx.com, perimeterx.net, px-cloud.net
- **Misc from the shared list**: blissfullyzebra.com, adshield-fallback-dev-wskxz.b-cdn.net, adshield-fallback-staging-yp6cs.b-cdn.net, getadmiral.com, eventexistence.com, merequartz.com, goddesslamps.com, scenesucceed.com, whimsicalgrove.com

## How to import into Technitium DNS

**Option A — by URL (recommended, auto-updates):**

1. Open **Technitium DNS Manager**.
2. Go to **Blocklist** → **Add new blocklist**.
3. Enter this URL as the blocklist source:
   ```
   https://raw.githubusercontent.com/avd706/technitium-dns-ad-verification/main/ad-verification-providers.txt
   ```
4. Save and enable. Technitium downloads and re-parses it automatically on its refresh interval.

**Option B — paste contents (manual):**

1. Open **Technitium DNS Manager**.
2. Go to **Blocklist** → **Add new blocklist**.
3. Paste the contents of `ad-verification-providers.txt` (one domain per line).
4. Save and enable.

Technitium accepts both bare domains (`doubleverify.com`) and hosts-style prefixed entries (`0.0.0.0 doubleverify.com`). This file uses bare domains, which block the domain and all of its subdomains.

## Notes / cautions

- This is a *community-sourced* list — verify each domain in your own environment before relying on it. Some entries are aggressive (e.g. `html-load.com`, `error-report.com`, `perimeterx.com`) and may break site functionality on some pages.
- Use alongside an in-browser ad blocker (e.g. uBlock Origin) for best results; the post's author notes DNS alone won't eliminate every anti-adblock message.
- The uBlock custom-filter equivalents shared in the post were:
  ```
  @@||html-load.com^
  ||html-load.com^$redirect=empty
  @@||error-report.com^
  ||error-report.com^$redirect=empty
  ```

## Contributing

Open an issue or pull request to add a missing domain (with source) or to flag a domain that breaks legitimate sites.
