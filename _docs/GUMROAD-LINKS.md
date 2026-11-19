# Gumroad link structure and channel attribution

Internal note. The `_docs/` folder starts with an underscore so GitHub Pages (Jekyll) does not publish it. No trackers, pixels or third-party scripts are on the site and none should be added for this.

## What Gumroad documents

Source: https://gumroad.com/help/article/74-the-analytics-dashboard

- Referrers: Gumroad groups views, purchases and conversion by the referring site. Visits with no identifiable source show as Direct, Email or IM. Mobile apps and messengers often land in that bucket.
- UTM links: created inside Gumroad (Analytics, then Links). Pick the product as the destination, then set Source, Medium and Campaign. Gumroad gives a link to share. Each click is recorded, and a purchase within 7 days is credited to that link, with clicks, sales, revenue and conversion shown per link.
- Gumroad does not document raw `?utm_...` strings typed onto the plain product URL, so do not rely on them. Use links generated in Gumroad.

## How the site behaves

- The two buy links on the site point at the plain product URL, `https://vls7.gumroad.com/l/pure-ambience`, and open Gumroad's overlay checkout.
- The page sends `strict-origin-when-cross-origin` (explicit meta tag), so Gumroad receives `https://pureambienceaudio.com` as the referrer. Purchases from the site should appear under that domain in Gumroad's referrer list. Not yet confirmed with a live test purchase.
- Whether the overlay iframe passes the page referrer through the same way as a normal page visit is unverified.

## Channel naming convention (create these in Gumroad, one link per placement)

| Where the link is posted | Source | Medium | Campaign |
|---|---|---|---|
| Instagram bio / posts | instagram | social | bio, or the post name |
| TikTok bio | tiktok | social | bio |
| YouTube description | youtube | video | video slug |
| Reddit post | reddit | community | subreddit name |
| KVR / forum post | kvr | community | thread name |
| Email signature / newsletter | email | email | signature, or issue number |
| Reviewer outreach | reviewer | outreach | reviewer handle |

Rules: lowercase, no spaces, one Gumroad link per placement so results do not mix. Keep the site's own buy links plain so the referrer domain stays clean. Record each link created in `company/` trackers in the Pure-Ambience repo, with the date.

## Reading the result

Analytics, then Links, for per-link clicks and sales. Analytics, then Referrers, for the website's own traffic. With very low volume (19 to 15 views per 30 days at last pull) expect single-digit counts; treat results as direction, not proof.
