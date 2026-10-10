# Timeline — dated proof

Filesystem timestamps from the original DigiMusic archive on disk (macOS birth + modified). These are the receipts that this work lived in **2008**, during the same early consumer-streaming window as Netflix Watch Instantly (2007) and Hulu’s public launch (2008).

> Showcase copies under this repo preserve those original **modified** dates where possible. Git itself does not store filesystem birthtime — the table below is the durable proof record.

---

## Industry context

| When | What happened |
|------|----------------|
| Jan 2007 | Netflix launches browser “Watch Now” / Watch Instantly |
| Oct 2007 | Hulu public beta |
| Mar 2008 | Hulu full public U.S. launch |

DigiMusic TV was an **independent niche music-community network** built and operated in that same early wave — not a claim of inventing streaming first.

---

## Proof table — archive filesystem dates

| Date | Artifact | Role |
|------|----------|------|
| **2008-03-14** | Music In Schools Today Agreement (signed) | PSA — preview PNGs in `receipts/contract-previews/` |
| **2008-03-24** | What is Indie promotional stills | Partner promo pack on the network |
| **2008-03-25** | What is Indie Content Broadcasting Agreement | Content-provider deal — first + last page PNGs |
| **2008-06-04** | `Stand Alone Productions Royalty Report.numbers` | Royalty settlement receipt |
| **2008-08-22** | `Alternative Solution Brochure.pdf` | Media kit / sponsor positioning |
| **2008-10-08** | `DigiMusic Tv.com[FW4].freeway` | Freeway site project (authoring source) |
| **2008-11-09** | `broadcast4.html` | QuickTime Digi player channel export |

Media kit / royalty / preview files in [`receipts/`](./receipts) and the Digi player page in [`site-archive/`](./site-archive) correspond to these rows.

---

## Channel progression (dated)

```text
2008-03 ── content deals + PSA paperwork
2008-06 ── royalty reporting in place
2008-08 ── media kit brochure
2008-11 ── broadcast4.html  → QuickTime Digi player (.mov channel)
```

---

## How to verify locally

From this repo (or the original Memory folders):

```bash
# macOS: birth + modified
stat -f "%SB  %Sm  %N" -t "%Y-%m-%d" \
  site-archive/broadcast4.html \
  "receipts/media-kit/Alternative Solution Brochure.pdf" \
  "receipts/royalty/Stand Alone Productions Royalty Report.numbers"
```

Finder → Get Info also shows these dates on the archived files.
