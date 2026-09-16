# Jujube Log

A home-screen web app for logging Sleep, Breastfeed, and Diaper, built to replace
Nara Baby before it starts charging. Data is written in Nara's own column format, so
[understand-infant-sleep](https://github.com/alicezheng-ai/understand-infant-sleep)
keeps working against it unchanged.

**Live app:** https://alicezheng-ai.github.io/baby-is-figureoutable/
(open it in Safari, then Share → Add to Home Screen)

## Roadmap

- [x] **Day 1 — Core logging.** Live start/stop timers for Sleep and Breastfeed (with
  one-tap side switching), one-tap Diaper logging, offline-safe queuing so a save
  never gets lost to a bad connection, home-screen install.
- [ ] **Day 2 — Bath and Medicine.** Bath as a simple timestamped log; Medicine with a
  dosing interval and a countdown to the next dose.
- [ ] **Day 3 — Action screen v1.** Rule-based "what's likely going on" reading —
  elapsed time since the last event, compared against Sai's own recent averages.
  Ships before the Digital Twin model gets wired in.
- [ ] **Day 4 — Sleep-trend flag.** A longer-horizon, week-over-week check for things
  like reduced sleep, with AAP age-bracket context layered in.

CSV export isn't a separate line item — the Google Sheet behind this app already uses
Nara's exact header row, so `File > Download > CSV` on it is already a Nara-format
export, any time.

**Later, not on this sprint:** merging in the Digital Twin model and folding
`understand-infant-sleep` in as a view rather than a separate tool; multi-caregiver
support, once family is around to use it in January.

## Setup

1. **Backend:** new Google Sheet → Extensions → Apps Script → paste in `Code.gs` →
   Deploy as a web app (Execute as Me, access Anyone) → copy the Web app URL.
2. **Front end:** paste that URL into `CONFIG.APPS_SCRIPT_URL` near the top of
   `index.html`.
3. **Hosting:** this repo, with Pages turned on (Settings → Pages → main branch,
   root).
4. **Home screen:** open the live link in Safari → Share → Add to Home Screen.

Data lives in the `Log` tab of the Google Sheet from step 1 — one row per entry,
headers matching the Nara export.
