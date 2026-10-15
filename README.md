# Gift Portal – A Gift for the Future

A one-page site for friends and family who ask what to get the kids. Instead of toys, it invites small contributions to each child's 529 college savings plan and shows how much a gift today could grow over time.

**Live:** https://vmannusa.github.io/gift-portal/

## What it does

- A short note explaining the request (no pressure, small amounts welcome).
- **"The Magic of Compounding" calculator:** a slider from $5 to $250 shows what that gift could be worth at ages 18, 30 and 65.
- Two buttons that link to each child's 529 plan contribution page.
- **Link preview:** when the link is texted or posted, it shows a preview card with the title and a sample projection (`og-image.png`).

## How the numbers are calculated

Future value with yearly compounding at an assumed 8% return:

```
value = gift × (1 + 0.08) ^ years
```

| Gift today | Age 18 | Age 30 | Age 65 |
| --- | --- | --- | --- |
| $5 | $20 | $50 | $744 |
| $25 | $100 | $252 | $3,719 |
| $100 | $400 | $1,006 | $14,878 |

Years are counted from birth (age 0). The 8% rate is an estimate based on historical long-term market returns, not a guarantee.

## Setup

1. **Add the 529 links.** In `index.html`, find the two buttons under "Contribute to their journey" and replace each `href="#"` with that child's plan gifting link. Many 529 plans offer a shareable gifting page or code (for example through Ugift) so family can contribute without seeing account details.
2. **Change the rate or ages** (optional): edit `RATE`, `YEARS_18`, `YEARS_30` and `YEARS_65` near the bottom of `index.html`.
3. **Publish:** **Settings > Pages**, source "Deploy from a branch", branch `main`, folder `/ (root)`.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site. Uses Tailwind CSS, Lucide icons and the Outfit font from CDNs; no build step. |
| `og-image.png` | 1200×630 preview image shown when the link is shared in texts and social apps. |
| `CHANGELOG.md` | What changed and when. |

## Privacy

The page is public. Keep account numbers and personal details out of it; link only to the plan's official gifting page.

See the [change log](CHANGELOG.md) for history.
