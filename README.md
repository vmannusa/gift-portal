# Gift Portal – A Gift for the Future

A one-page site for friends and family who ask what to get the kids. Instead of toys, it invites small contributions to each child's 529 college savings plan and shows how much a gift today could grow over time.

**Live:** https://vmannusa.github.io/gift-portal/

## What it does

- A short note explaining the request (no pressure, small amounts welcome).
- **"The Magic of Compounding" calculator:** a slider from $5 to $250 shows what that gift could be worth at ages 18, 30 and 65 if given to a newborn.
- **Per-child projections:** a table under the cards shows the same gift grown for Emery (born 2023) and Micah (born 2026), using the years each has left until 18, 30 and 65. Ages update automatically each new year.
- **Micah's 529** and **Emery's 529** buttons open Venmo (@KatelynMann91) with the slider amount and a note ("For Micah's 529" / "For Emery's 529") filled in. The giver can change the amount before sending.
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

The cards count years from birth (age 0). In the per-child table, `years = target age − (this year − birth year)`, so Emery's numbers are a little lower than a newborn's. Birth years are set in `KIDS` near the bottom of `index.html`. The 8% rate is an estimate based on historical long-term market returns, not a guarantee.

## Setup

1. **Venmo links.** The buttons use `https://venmo.com/<user>?txn=pay&amount=<amount>&note=<note>`. To change the recipient, edit `VENMO_USER` near the bottom of `index.html`; to change a note, edit the button's `data-note`. (A 529 plan's own gifting page, such as Ugift, is an alternative that deposits straight into the account.)
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
