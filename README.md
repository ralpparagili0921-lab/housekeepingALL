# OR Housekeeping App — setup (≈15 minutes)

## 1. Database (Supabase → the Opener project, jgnweipcjghgdnktpsww)
Open **SQL Editor** and run these files in order (each is safe to re-run):
1. `hk_01_schema.sql` — creates the `hk_` tables, seeds SuperUser **Ralp Chester Paragili (PIN 0315)**
2. `hk_02a_history_import_OR.sql` — Google Forms history for OR 1–3 (641 entries)
3. `hk_02b_history_import_other_areas.sql` — PACU, Comfort/Dressing, Pantry (594 entries)

Each import ends with a small table of counts per area — check they read
or1 219 · or2 212 · or3 210 · pacu 199 · comfort 198 · pantry 197.

## 2. App key
In `index.html`, find `CONFIG` near the top of the script and replace
`PASTE_YOUR_PUBLISHABLE_KEY_HERE` with the **same `sb_publishable_…` key the Opener app uses**
(Supabase → Project Settings → API Keys).

## 3. GitHub Pages
Create a new repo (e.g. `housekeeping`), upload **index.html** and **sw.js** as files
(not a folder), then Settings → Pages → Deploy from branch `main` / root.
URL: `https://ralpparagili0921-lab.github.io/housekeeping/`

## 4. First login
Tap **Ralp Chester Paragili** → PIN **0315** → set your security questions →
My Account → Change PIN. Then have each housekeeping staff and verifier tap **Sign up** once.

## 5. Updating later
Change `APP_VERSION` in index.html **and** `CACHE` in sw.js to the same new value,
upload both files — open devices show "Update available — tap to refresh".

## Notes
- Keep-alive: this app shares the Opener project, so Opener's existing GitHub keep-alive
  workflow (if it points at jgnweipcjghgdnktpsww) keeps this database awake too.
- Storage: all 1,235 history entries ≈ 1 MB of the 500 MB free database. No photos are stored.
- Holidays seeded as closures: Apr 2–3 (Holy Week), May 1, Aug 21. Mark others in Admin → Closures
  or straight from KPI Dashboard → "Days with no log".
