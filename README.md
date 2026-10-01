# NEPA Date Nights

A hand-curated guide to date-night spots across Northeastern Pennsylvania — bars,
breweries, live music, cinemas, haunts, games, and more. No restaurants, cafés,
dessert shops, wineries, or wine bars.

**Live site:** https://stainlesssteel770.github.io/nepa-date-nights/

## How the site works

- `index.html` — the whole page (filters, cards, banners).
- `venues.json` — the venue dataset. The page fetches this file when it loads, so
  editing the data here updates the live guide without touching any code. A copy
  of the data is also embedded in `index.html` as an offline fallback.
- `assets/banners/` — one banner image per category.

## Editing venue data (no coding needed)

1. Open [`venues.json`](venues.json) on GitHub and click the pencil icon (Edit).
2. Find the venue by its `"name"` and change the fields you need (see schema below).
3. Click **Commit changes** — the site picks up the new data within a few minutes.
   A validation check runs automatically on every push; if the JSON has a syntax
   error the commit is flagged.

### `venues.json` schema

Top level: `{ "data_updated": "YYYY-MM-DD", "venues": [ … ] }`

Each venue:

| Field | Meaning |
|---|---|
| `name` | Venue name (unique) |
| `town` | Town label shown on the card |
| `cat` | Category id: `bars`, `casino`, `breweries`, `music`, `comedy`, `cinema`, `haunts`, `seasonal`, `games`, `adventure`, `creative`, `afternoon` |
| `addr` | Street address (used for the Maps link) |
| `time` | Drive minutes from each starting town: `{"kingston": 10, "scranton": 27, "canadensis": 62}` |
| `hoursBuckets` | Time-of-day filters it belongs to: any of `midday`, `evening`, `late` |
| `hours` | Human-readable hours line shown on the card |
| `type` | Short type label (e.g. "Dive bar", "Escape room") |
| `note` | One–two sentence description |
| `weeknight` | `true` if open late on weeknights (shows "Open late weeknights") |
| `friSatLateOnly` | `true` if only open Fri/Sat late — hidden unless the "Fri & Sat late-night spots" toggle is on |
| `phone` | Optional phone number |
| `flag` | Optional extra notice merged into the card's warning line |
| `season` | Optional `{"s": [month, day], "e": [month, day]}` for annual seasonal venues (powers "In season now") |
| `hoursDaily` | Per-day hours: `{"mon": "…", "tue": "closed", …}` (`null` = unknown, `"closed"` = closed). Powers the "Open tonight" filter |
| `seasonText` | Free-text season description (e.g. "Apr–Oct (annual)") |
| `priceTier` | `Free`, `$`, `$$`, or `$$$` (per person: under $15 / $15–$40 / over $40) |
| `priceDetail` | Optional price note shown under the tier |
| `hoursVerified` | `false` → the card shows a uniform "Call ahead — hours vary" notice |

## Reporting wrong hours / suggesting a spot

Every card has a **Report wrong hours** link that opens a prefilled issue naming the
venue. There's also a **Suggest a spot** link in the footer. Both use the issue
forms in `.github/ISSUE_TEMPLATE/` — no GitHub expertise required, just fill in
the boxes.
