# Site archive

Exported DigiMusic TV website pages (Freeway → HTML/PHP) with a **curated** `Resources/` set so the channel and nav chrome still resolve locally.

Not included in this first pass (kept out to limit size):

- Softpress Freeway project binaries (`.freeway` / `.fwbackup`)
- Full original `Resources/` library (~759 files)

## Key pages

| File | Role |
|------|------|
| `default.html` | Home |
| `broadcast4.html` | QuickTime Digi player channel |
| `broadcast.html` | KickApps live console channel |
| `mission.html` / `connect.html` / `advertise.html` | Network story + monetization |
| `productplacement.html` | Placement / sponsorship surface |

```bash
python3 -m http.server 8080
```
