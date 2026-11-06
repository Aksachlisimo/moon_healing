# Moon Healing 🌙

Website for **Moon Healing**, Moon's (Hằng's) one-to-one reiki, massage and somatic practice in Hải Châu, Đà Nẵng, Vietnam.

**Live:** https://moon-healing-zeta.vercel.app

Built mobile-first, in English and Vietnamese, as a single static page with no build step and no dependencies.

## What's on the page

- **Hero:** a live moon-phase drawing calculated for today, on a twinkling night sky.
- **Sessions and prices:** Reiki (800k ₫), Somatic session (1,200k ₫) and the 8-session journey (900k ₫ per session). Prices can switch between VND, € and $.
- **Booking message builder:** pick a session, day and time. It writes the message, copies it, and opens Moon's Instagram.
  - It only offers open days and times.
  - In the visitor's language.
- **Box-breathing exercise:** one calm minute before the visit.
- **Reviews:** from Google (5.0 ★).
- **About, FAQ and Visit:** with a Google Map, directions and the hours table (today highlighted).
- **Language:** EN/VI switch, remembered per visitor.

## Practical info

| | |
|---|---|
| Hours | Tuesday–Friday, 10 AM–12 PM, **by appointment only** |
| Address | K91, 8 Đ. 3 Tháng 2, Hải Châu, Đà Nẵng 50000 |
| Phone | +84 975 422 987 |
| Instagram | [@moonhealing_reiki_massage](https://www.instagram.com/moonhealing_reiki_massage/) |
| Payment | VND, cash or QR code |

## Files

| File | What it is |
|---|---|
| `index.html` | The whole site: HTML, CSS, JS and the EN/VI text |
| `moon.webp` | Moon's portrait (About section) |
| `avatar.webp` | Small round photo next to the booking message |
| `favicon.svg` | Browser tab icon |
| `vercel.json` | Clean URLs and security headers |

## Editing

Everything lives in `index.html`:

- **Text in both languages:** the `T = { en: {...}, vi: {...} }` dictionary near the bottom.
- **Hours:**
  - `OPEN=[2,3,4,5]` sets the days, where 0 is Sunday.
  - `LAST=11` is the last start hour.
  - The time chips are `data-v="10"` and `data-v="11"`.
  - The hours text is in the `st.long`, `facts.hoursv` and `f.a4` keys, and in `renderHours()`.
- **Prices:** the `data-vnd` attributes on the session cards.
- **Currency rates:** `FX={EUR:30000,USD:26500}`.

## Run locally

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Deploy

The site is hosted on Vercel, project `moon-healing`, with framework preset **Other** and no build command. Pushing to `main` deploys to production.
