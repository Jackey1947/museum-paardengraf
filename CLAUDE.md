# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Offline HTML-kiosk over het Paardengraf van Borgharen, bedoeld voor gebruik op een iPad in het Vesting Museum Maastricht (Helpoort). Eén HTML-bestand dat volledig zelfstandig draait — geen server, geen internet, geen buildstap.

## Uitvoeren en testen

Open `index.html` direct in Safari (Mac of iPad). Er is geen buildstap, geen package manager en geen testframework.

```bash
open index.html          # opent in de standaard browser (Mac)
```

Op de iPad: zet de volledige map via Finder/AirDrop over en open `index.html` in Safari. Voor kioskmodus: gebruik de functie "Begeleide toegang" van iOS om de iPad te vergrendelen op Safari.

## Architectuur

Alles staat in één bestand: `index.html`. De structuur daarbinnen:

- **CSS** (bovenin `<style>`) — CSS-custom properties (`:root`) voor kleuren en afmetingen. Alle stijlcomponenten zijn opgebouwd via herbruikbare utility-klassen (`.quote`, `.fact-list`, `.sec-head`, etc.).
- **HTML** — Zes `<section class="screen">` elementen, elk met id `screen-{naam}`. Standaard `display: none`; de actieve sectie krijgt class `active` (dan `display: block`).
- **JavaScript** (onderin `<script>`) — Één functie `toonScherm(id, knop)` die schermen wisselt. Aanvullend: blokkering van dubbel-tik-zoom en contextmenu voor kioskmodus.
- **Navigatie** — Vaste `<nav>` onderaan met zes `.nav-btn` knoppen. De actieve knop krijgt class `active` en een gouden lijn bovenaan via `::before`.

## Bestanden

| Bestand | Rol |
|---|---|
| `index.html` | De volledige applicatie |
| `foto_W.Lem1.jpg` | Close-up skeletten in opgravingsgreppel |
| `foto_W.Lem2.jpg` | Open dag 2010 met bezoekers bij de opgraving |
| `Luchtopnames 2010.jpg` | Luchtfoto van de volledige opgraving |
| `Skelet in Helpoort.jpg` | Het skelet in de vitrine ter plekke in de Helpoort |
| `Wim Dijkman-In Helpoort.jpg` | Archeoloog Dijkman bij het skelet in de Helpoort |
| `Lodewijck XIV voor Maastricht.jpg` | Barok schilderij: Lodewijk XIV te paard voor Maastricht |
| `Schilderij-Joseph_parrocel.jpg` | Gevechtsscène beleg 1673 door Joseph Parrocel |
| `Paardengraf Borgharen toch weer ouder.mp4` | Videoreportage (wordt lokaal afgespeeld) |
| `Paardengraf.txt` / `.docx` | Bronmateriaal (niet ingeladen door de app) |

## Aandachtspunten

**Bestandsnamen met spaties** moeten URL-encoded worden in `src`- en `href`-attributen (bijv. `Luchtopnames%202010.jpg`). Bestandsnamen zónder spaties hebben geen encoding nodig.

**Geen externe afhankelijkheden** — voeg geen CDN-links, Google Fonts of externe scripts toe. Alles moet offline werken.

**iPad-kiosk beperkingen** — vermijd hover-states (werken niet op touch), houd tap-targets minimaal 44×44 px, en gebruik `playsinline` op `<video>` zodat iOS niet automatisch fullscreen gaat.

**Schermen toevoegen** — voeg een `<section id="screen-{naam}" class="screen">` toe aan `#content`, en een bijbehorende `.nav-btn` in `<nav>`. De JavaScript-functie `toonScherm()` werkt automatisch voor elk scherm met het juiste id.
