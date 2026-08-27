# Journal Citation Rate Tools

Five interactive charts of **Cites per Document (2 years)** — the Scopus/SCImago citation
ratio — by publication year, covering 756 journals and 15,697 data points from 2000–2025.

Each tool is a single self-contained HTML file: no server, no database, no build step.
Open one in a browser and it works, including offline.

| Tool | Journals | Groups |
|---|---|---|
| Ecophysiology | 23 | 4 |
| Ecology, Evolution & Marine | 103 | 9 |
| Biology (curated) | 94 | 16 |
| Biology Top 500 | 496 | 18 |
| Tamzins List (ecotoxicology) | 40 | 6 |

---

## Publish on GitHub Pages

**1. Create the repository**

On GitHub, create a new **public** repository — for example `journal-citation-rates`.
(Pages requires a public repo unless you have a paid plan.)

**2. Push this folder**

From inside this `website/` folder:

```bash
git init -b main
```

```bash
git add . && git commit -m "Journal citation rate tools"
```

```bash
git remote add origin https://github.com/YOUR-USERNAME/journal-citation-rates.git
```

```bash
git push -u origin main
```

**3. Turn on Pages**

In the repository: **Settings → Pages → Source: Deploy from a branch**, then choose
branch `main` and folder `/ (root)`. Save.

Your site appears within a minute or two at:

```
https://YOUR-USERNAME.github.io/journal-citation-rates/
```

Individual tools live at `/ecophysiology/`, `/biology-top-500/`, and so on.

---

## Turn on visit counts

The pages ship with a [GoatCounter](https://www.goatcounter.com) tag that is **inert until
you configure it**. GoatCounter is free for personal use, sets no cookies, stores no
personal data, and needs no consent banner.

**1.** Sign up at [goatcounter.com](https://www.goatcounter.com) and pick a code
(for example `jutfelt`). Your dashboard will be at `https://jutfelt.goatcounter.com`.

**2.** Replace the placeholder in all six pages:

```bash
grep -rl YOURCODE . --include=*.html | xargs sed -i '' 's/YOURCODE/jutfelt/g'
```

(On Linux, drop the `''` after `-i`.)

**3.** Commit and push:

```bash
git add . && git commit -m "Enable analytics" && git push
```

Visits then appear on your GoatCounter dashboard, broken down **per page**, so you can see
which of the five tools people actually open, plus referrers and countries.

### Alternatives

- **Cloudflare Pages** — host there instead and analytics are built in, no tag needed.
- **Plausible** — paid, similar privacy stance; swap the script tag.
- **Netlify Analytics** — server-side, paid, immune to ad-blockers.

To remove analytics entirely, delete the `<script data-goatcounter=...>` block from each
HTML file. Everything else keeps working.

---

## Updating the data

The figures are baked into each HTML file at build time, so refreshing them means
regenerating the pages from source rather than a database update. Ask Claude to re-run the
pipeline against `scijournal.org`, then rebuild this folder and push.

---

## Caveats worth keeping in view

- The metric is **not** the Clarivate Journal Impact Factor. It divides by *all* documents,
  not just "citable items", so journals carrying a lot of news and commentary read lower.
  Each tool's footer reports the measured agreement **for its own journals** — median
  difference ranges from 3.3% (Ecophysiology) to 7.6% (Biology Top 500).
- **2023 is missing for most journals** — a gap in the source archive, not a zero. Interior
  gaps are bridged with a linearly interpolated estimate, drawn as a dotted segment and
  marked `~`.
- Frontiers Media, MDPI and Hindawi-imprint titles are excluded by design, as are
  *Chemosphere*, *Science of the Total Environment* and *Ecotoxicology and Environmental
  Safety*, over editorial-integrity concerns.

---

Analysis by Fredrik Jutfelt.
