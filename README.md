# TEAM-CBT Mood Log

A personal, mobile-first PWA for keeping TEAM-CBT self-help logs in the style
of Dr David Burns' published forms, plus companion files for filling them out
**by voice** with Claude (e.g. while driving).

## The four tools

| Tool | For | Faithful to |
|---|---|---|
| 🌤 **Daily Mood Log** | Upsetting events: emotions (0–100 before/after), negative thoughts with belief ratings, the 10 cognitive distortions, positive thoughts with the necessary/sufficient conditions | the classic DML (*Feeling Good* / *When Panic Attacks* / *Feeling Great*) |
| 🌀 **Habits & Addictions Log** | Temptations: tempting situation, tempting thoughts, the 10 **positive** distortions (mirror images), loving/effective responses, Devil's Advocate guidance | the Habits & Addictions Log from *Feeling Great*'s habits chapter |
| 🔄 **Positive Reframing** | Ambivalence about a habit: advantages / disadvantages of change / core values ("Triple Paradox") | the Positive Reframing Table |
| ⚖️ **Decision Tool** | Difficult decisions: two options, four quadrants, the four 100-point weighings, auto-computed totals (−200…+200) and pattern interpretation | the Decision-Making Tool |

The **Guide** tab inside the app carries the full reference material: all 10
distortions with negative *and* positive faces, emotion word clusters, DML
how-to, Devil's Advocate rules, stimulus control, untwisting techniques, and
the TEAM model.

## Structure

```
team-cbt-mood-log/
├── app/            the PWA (static, no build step, no dependencies)
│   ├── index.html  the whole app — inline CSS/JS
│   ├── manifest.webmanifest, sw.js, icons/
└── claude/         companion files for voice sessions with Claude
    ├── VOICE-SESSION.md   session protocol (keeps Claude on track)
    ├── REFERENCE.md       distortions, emotions, techniques
    └── schema/            JSON handoff format + examples
```

## Running it

- **Hosted (recommended, enables install + offline):** serve `app/` over
  HTTPS. GitHub Pages works as-is — enable Pages on the repo and open
  `/team-cbt-mood-log/app/`. All paths are relative, so any subpath works.
  On the phone: "Add to Home Screen" → it installs as an app and works
  offline.
- **Local:** `python3 -m http.server` in `app/` and open it; or just open
  `index.html` directly (everything works except the offline service worker).

Data lives only in the browser's localStorage. **Data → Export** regularly if
you care about the entries; **Data → Import** restores or merges (it also
accepts the ```json blocks Claude produces after a voice session — see
`claude/README.md`).

## Voice sessions with Claude

The `claude/` folder is a drop-in knowledge pack for a Claude Project: Claude
interviews you one question at a time (driving-safe rules), captures thoughts
word-for-word, coaches without putting words in your mouth, can play Devil's
Advocate against your own tempting thoughts, and ends the session with a JSON
block the app imports directly. Details in `claude/README.md`.

## Moving to its own repo

The folder is self-contained: copy `team-cbt-mood-log/` anywhere (e.g. the
root of a new repo), and if you use GitHub Pages, point it at `app/` or adjust
the path. Nothing references this repo.

## Credits & disclaimer

The form structures and the negative/positive-distortion model are the work of
**David D. Burns, M.D.** (*Feeling Good*, *When Panic Attacks*, *Feeling
Great*) — the original forms are © David D. Burns and available for personal
use at [feelinggood.com](https://feelinggood.com). This is an independent
personal journaling tool, not affiliated with or endorsed by Dr Burns, and not
therapy or medical advice. If you're in crisis, contact local emergency
services or a crisis line — not an app.
