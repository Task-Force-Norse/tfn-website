# Task Force Norse — Nettside

Rekrutteringsside for TFN, en norsk milsim-enhet i Arma Reforger. Bygget med ren HTML/CSS/JS, hostet på GitHub Pages.

- **Live:** `https://kjweme.github.io/milsim-sandbox/`
- **Repo:** `github.com/kjweme/milsim-sandbox`
- **Bruker:** kjweme (kjweme@gmail.com) — ny til webutvikling, forklar konsepter enkelt og på norsk

---

## Struktur

```
index.html        — hele nettsiden (én side)
css/style.css     — all styling
js/main.js        — scroll-animasjoner og aktiv nav-lenke
assets/           — bilder og komprimerte videoer
source-material/  — råfiler, gitignored
```

## Designsystem

**Fonter:** Barlow Condensed (headings/labels) + Barlow (brødtekst) — Google Fonts

**Fargetema (Taktisk Kull — aktivt):**
```css
--olive: #2c323d;  --olive-dark: #1e232c;  --olive-darker: #121620;  --gold: #c9a84c;
```
Temabytte: endre kun de tre `--olive`-variablene øverst i `css/style.css`.
Alternativer kommentert i CSS: Olive Khaki (`#525034`), Nordic Skog (`#253d20`), Mørk Rav (`#4a3620`).

---

## Viktig innhold om TFN

- **Spill:** Arma Reforger (PC kun, norsktalende)
- **Møtetid:** Søndager 18:45–22:00 CET, 30+ medlemmer
- **Krav:** Norsk, PC, mikrofon, TeamSpeak 3 + CVON-plugin
- **Discord:** `https://discord.gg/r8m6QrFmMj`
- **YouTube:** `https://www.youtube.com/@TaskForceNorse`
- **Flernasjonal samarbeid:** Heter **Joint Scandinavian Task Force (JSTF)** — ikke "Nordic Joint Operations" (feil navn brukt tidligere)
- **Disclaimer:** TFN har ingen tilknytning til Forsvaret — dette må alltid forbli i footeren

## Discord-søknad
Nye medlemmer klikker Discord-lenken og fyller ut et kort søknadsskjema (Discord Server Member Applications). Staben godkjenner manuelt.

---

## Assets

| Fil | Innhold |
|---|---|
| `hero-convoy.png` | Desert konvoi — hero-bakgrunn |
| `logo-patch.png` | TFN-logo/emblem |
| `img-patch-closeup.png` | Soldat med TFN-patch, norsk skog |
| `img-joint-ops.png` | JSTF-formasjon, 40–50 spillere |
| `img-briefing.png` | Briefing-sirkel, desert |
| `heli-bg-1-web.mp4` | Komprimert helikoptervideo (974 KB) |
| `heli-bg-2-web.mp4` | Hav og skyer — aktiv i videoseksjonen (1.1 MB) |

Råvideoer (`heli-bg-1.mp4`, `heli-bg-2.mp4`) ligger lokalt i `assets/` men er gitignored (167/183 MB).
ffmpeg er installert via winget. Komprimeringskommando: `ffmpeg -i kilde.mp4 -vf scale=1280:-2 -c:v libx264 -crf 28 -an output-web.mp4`

---

## Gjenstående oppgaver

- **Bildegalleri:** Ønsket seksjon mellom JSTF og Bli med. Bilder velges fra `source-material/`, kopieres til `assets/gallery/`, konverteres til WebP.
- **Bildeoptimalisering:** PNG-filer i assets/ er 5–9 MB — bør konverteres til WebP.
- **Mobilmeny:** Nav-lenker skjules på mobil (< 700px) — ingen hamburgermeny ennå.
- **Overlevering:** Repoet skal overføres til en GitHub-organisasjon eid av TFN-lederen (se trinnvis guide i chat-historikken).
