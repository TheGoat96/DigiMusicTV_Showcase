# Architecture

How DigiMusic TV’s channel and network stack worked, reconstructed from the surviving site export and Freeway project history.

---

## Product shape

DigiMusic TV was a **vertical streaming network** for the music community:

1. **Site** — Freeway-authored marketing / connect / advertise / store pages
2. **Channel** — full-screen (or near full-screen) player experience
3. **Inventory** — sponsor pre-rolls + AdPeeps display zones
4. **Supply** — content-provider agreements + original in-house production
5. **Settlement** — royalty reporting against distributed titles

---

## Channel evolution

### Phase 1 — QuickTime Digi player (`broadcast4.html`, ~2008)

Custom “console” chrome (sliced background art, Channel Guide / Advertise / Help, QT7 badge) wrapping a QuickTime `<embed>` in a layer named `DMTStream`.

Exported snapshot behavior:

- `src` → `http://www.digimusictv.com/movies/bluecataudiopr2.mov`
- `autoplay=true`, `loop=false`, `kioskmode=true`
- Progressive HTTP delivery from the DigiMusic host (not a separate RTSP URL in the HTML)

Earlier Freeway revisions show a richer QT pattern (`DMTStream2`):

- Looping `poster.mov` as the starter
- `href` + `target="myself"` to replace the poster with the next clip (e.g. `digimusictvintro.mov`)
- Business copy describing a **10-second sponsor pre-roll** on every channel access, plus mid-roll :30s

So the intended viewer path was: **open channel → preroll / poster kickoff → program content**, with “what’s on” swapped by updating the `.mov` pointed at the player (and/or chaining via QT `href`).

Other `.mov` titles referenced across project history:

| URL path | Role |
|----------|------|
| `/movies/bluecataudiopr2.mov` | Channel program in `broadcast4` export |
| `/movies/bluecataudiopr.mov` | Earlier Blue Cat PR |
| `/digimusictvintro.mov` | Site / channel intro |
| `/movies/digimusictv.comintro2.mov` / `intro3.mov` | Intro iterations |
| `/movies/maudiopr.mov`, `/movies/vonagepr.mov` | Sponsor / partner PR |
| `/poster.mov` | QT poster / kickoff |

Upload path for site assets: FTP host referenced in project files as `ftp.digimusictv.com/www`.

### Phase 2 — KickApps live console (`broadcast.html`, ~2009)

The Digi chrome was largely replaced by a hosted KickApps Flash widget:

- Loader: `http://serve.a-widget.com/service/getWidgetSwf.kickAction`
- DigiMusic affiliate site: **`73727`**
- Full-channel widget: **`59197`** (950×620)
- Smaller widgets reused the same affiliate ID on home / mission / connect / product-placement pages

Site copy from this era refers to **“DigiMusic Tv Live Broadcast”** and a **Green Room** live chat — Kick was the live/social console layer after the QT progressive-file channel.

---

## Site + monetization

```mermaid
flowchart LR
  Viewer["Viewer"] --> Site["digimusictv.com\nFreeway HTML"]
  Site --> Channel["broadcast / broadcast4"]
  Channel --> Player["QT .mov or Kick widget"]
  Channel --> Ads["AdPeeps zones\n468x60 / 200x200 / 728x90"]
  Site --> Kit["Media kit / advertise"]
  Providers["Content providers"] --> Library["Titles + metadata"]
  Library --> Player
  Library --> Royalty["Royalty reports"]
  Sponsors["Sponsors"] --> Preroll["10s pre-roll + :30s"]
  Preroll --> Player
```

AdPeeps ran on-domain (`/adpeeps/adpeeps.php`) with named zones per page (Home, Mission, `DMT_Channel_*`, `dmt_console_728x90`, etc.).

---

## Production

Original DigiMusic programming was shot and edited in-house (founder-operated). The network also licensed / carried partner titles via content-provider paperwork (e.g. What is Indie, Under The Radar) and PSA agreements (e.g. Music In Schools Today).

---

## What this archive is *not*

- Not a runnable modern streaming stack (Flash / QT plugins are gone)
- Not a complete CMS or encoder pipeline dump
- Not a claim of inventing consumer streaming ahead of Netflix/Hulu — it is an independent vertical network built in that early window
