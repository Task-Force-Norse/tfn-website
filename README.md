# Task Force Norse — nettside

Offisiell nettside for [Task Force Norse](https://www.norskmilsim.no), norsktalende milsim-enhet i Arma Reforger.

Nettsiden er en enkel statisk HTML-side hostet på **GitHub Pages** med domenet `www.norskmilsim.no`. Ingen byggeverktøy, ingen rammeverk — alt er én HTML-fil med innebygde stiler og JavaScript.

---

## Filstruktur

```
tfn-website/
├── index.html          ← hele nettsiden (HTML + CSS + JS i én fil)
├── index-v3.html       ← backup av forrige versjon
├── CNAME               ← peker GitHub Pages til norskmilsim.no
├── assets/
│   ├── Kopi_av_Patch_skog_tekst.png  ← logo (brukes i topbar, hero og footer)
│   ├── hero-convoy.png         ← bakgrunnsbilde i "Hvem vi er"
│   ├── img-joint-ops.png       ← bilde i JSTF-seksjonen
│   ├── heli-bg-1-web.mp4       ← helikoptervideo (hero-bakgrunn)
│   ├── background-web.mp4      ← ørkenvideo (Media-seksjon)
│   ├── yt-thumbnail.png        ← YouTube-kortets miniatyrbilde
│   ├── tw-thumbnail.jpg        ← Twitch-kortets miniatyrbilde
│   └── gallery/
│       ├── bef8y3tqx6eg1.png   ← fremhevet galleri-bilde (t-a, størst)
│       ├── g01.png             ← CQB · Byoperasjon
│       ├── g02.png             ← Stridskontakt · Ørken
│       ├── g03.png             ← Rekognosering · Skogsposisjon
│       ├── g04.png             ← Wadi-kryssing · Kjøretøy
│       ├── g11.png             ← Mekanisert · Konvoi-klargjøring
│       ├── g12.png             ← Mekanisert · Framrykk
│       └── 20251019204943_1.jpg ← CQB · Hangar-clearing
├── css/style.css       ← kun for index-v3.html (gammel versjon)
└── js/main.js          ← kun for index-v3.html (gammel versjon)
```

---

## Slik oppdaterer du nettsiden

Alle endringer gjøres direkte på GitHub.com — ingen koding eller terminal nødvendig. Nettsiden oppdateres automatisk innen ~1 minutt etter at du lagrer.

### Oppdatere galleriet

Galleriet styres av filen [`assets/gallery/gallery.csv`](https://github.com/Task-Force-Norse/tfn-website/blob/main/assets/gallery/gallery.csv) — ikke av `index.html`. Ingen HTML-kunnskap nødvendig.

#### Slik ser filen ut på GitHub (vises som tabell):

| filnavn | beskrivelse | dato |
|---|---|---|
| bef8y3tqx6eg1.png | Norsk soldat · Ørken-deployering | 2026·02·08 |
| g11.png | Mekanisert · Konvoi-klargjøring | 2026·02·08 |
| … | … | … |

- **De 8 første radene** vises i galleriet på forsiden (størst øverst til venstre)
- **Rader under posisjon 8** er arkivert — vises ikke på forsiden, men dukker opp i «Se alle bilder»-vinduet
- **Rekkefølge** styres av linjerekkefølgen — øverst = fremst

#### Legge til et nytt bilde

1. Last opp bildet til [assets/gallery/](https://github.com/Task-Force-Norse/tfn-website/tree/main/assets/gallery) — klikk **Add file → Upload files**
   - Navnekonvensjon: `YYYY-MM-DD_Beskrivelse.png` (f.eks. `2026-05-11_CQB-byoperasjon.png`)
2. Åpne [`assets/gallery/gallery.csv`](https://github.com/Task-Force-Norse/tfn-website/blob/main/assets/gallery/gallery.csv) → klikk blyant-ikonet (✏️)
3. Legg til en ny linje **øverst** (under header-raden):
   ```
   2026-05-11_CQB-byoperasjon.png,CQB · Byoperasjon,2026·05·11
   ```
4. Klikk **Commit changes**

Bildet er nå fremst i galleriet. Det gamle bildet som falt ut av topp 8 havner i «Se alle bilder».

#### Endre rekkefølge

Åpne `gallery.csv` med blyant-ikonet og flytt linjer opp eller ned. Lagre.

#### Arkivere et bilde (ta det av forsiden uten å slette)

Flytt raden ned til under posisjon 8 i CSV-en. Bildet forsvinner fra forsiden, men vises fremdeles i «Se alle bilder»-vinduet.

#### «Se alle bilder»-knappen

Vises automatisk under galleriet når CSV-en inneholder mer enn 8 bilder. Åpner et vindu med alle bilder — inkludert de arkiverte. Knappen skjules automatisk hvis det er 8 eller færre bilder totalt.

### Oppdatere YouTube-video

Åpne `index.html` og finn seksjonen `<!-- MEDIA -->` (~linje 620):

```html
<a class="yt-card" href="https://www.youtube.com/@TaskForceNorse" ...>
  <div class="yt-thumb"><img src="assets/yt-thumbnail.png" ...></div>
  <div class="yt-body">
    <div class="t">OP Cliffhanger — JSTF Combined Arms</div>  ← tittel her
  </div>
</a>
```

- **Tittel**: endre teksten i `<div class="t">`
- **Lenke**: endre `href=` til direkte YouTube-lenke for siste video
- **Miniatyrbilde**: last opp nytt bilde som `assets/yt-thumbnail.png` (erstatter gammelt)

### Fremheve en annen Twitch-streamer

Finn Twitch-kortet rett under YouTube-kortet (~linje 649):

```html
<a class="tw-card-link" href="https://www.twitch.tv/NTFSteffen" ...>
  ...
  <div class="t">NTFSteffen</div>
  <div class="m">twitch.tv/NTFSteffen →</div>
```

- Endre begge steder med streamernavn og `href`-lenken
- Last opp nytt miniatyrbilde som `assets/tw-thumbnail.jpg`

**LIVE-merket** vises automatisk på søndager mellom 18:00 og 23:00 norsk tid. Ingenting å endre manuelt.

### Oppdatere tekst på nettsiden

Åpne `index.html` og bruk nettleserens søkefunksjon (`Ctrl+F`) for å finne teksten du vil endre. Seksjonsoverskrifter og avsnitt er ren HTML-tekst.

### Bytte logo

Last opp ny logofil som `assets/Kopi_av_Patch_skog_tekst.png` — erstatter den eksisterende filen med samme navn. Logoen brukes automatisk i topbar, hero og footer.

Hvis du vil bruke et helt annet filnavn på den nye logoen, må du også oppdatere de tre referansene i `index.html` (søk etter `Kopi_av_Patch_skog_tekst.png`).

> **Tips:** En logo med **gjennomsiktig bakgrunn** (PNG uten hvit bakgrunn) ser best ut mot den mørke bakgrunnen.

---

## Aktivere Twitch-embed (valgfritt)

Nettsiden støtter en fullskjerm Twitch-embed som kan vises under galleri-seksjonen. Den er skjult som standard.

Åpne `index.html` og finn øverst i `<script>`-blokken (~linje 710):

```js
const TWITCH_CHANNEL = null;
```

Endre `null` til kanalnavnet som en streng:

```js
const TWITCH_CHANNEL = 'NTFSteffen';
```

Commit og push — embedden vises på nettsiden. Sett tilbake til `null` når streamen er ferdig.

---

## Teknisk oversikt

- **Hosting**: GitHub Pages, automatisk deploy ved push til `main`
- **Domene**: `www.norskmilsim.no` — CNAME-filen peker til GitHub Pages
- **Fonter**: Oswald, Inter, JetBrains Mono (lastes fra Google Fonts)
- **Ingen avhengigheter**: ingen npm, ingen byggsteg, ingen rammeverk
- **Nettleserkompatibilitet**: moderne nettlesere. `background-attachment: fixed` virker ikke på iOS Safari (bakgrunnsbildet vises, men uten parallax-effekt)

---

## Lokal forhåndsvisning

Galleriet krever en lokal server for å laste CSV-filen — åpne **ikke** `index.html` direkte i nettleseren. Bruk VS Code Live Server:

1. Installer utvidelsen **Live Server** (av Ritwick Dey) fra Extensions-panelet
2. Åpne `index.html` i editoren
3. Klikk **Go Live** nede til høyre i statuslinjen
4. Nettleseren åpner `http://127.0.0.1:5500/index.html` — galleriet lastes normalt

---

*Spørsmål? Ta kontakt i Discord eller åpne en [issue](https://github.com/Task-Force-Norse/tfn-website/issues) i repositoriet.*
