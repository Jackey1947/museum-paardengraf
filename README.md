# Paardengraf van Borgharen — iPad Kiosk

Interactieve informatiekiosk over het Paardengraf van Borgharen, bedoeld voor gebruik op een iPad in het **Vesting Museum Maastricht (Helpoort)**.

## Inhoud

De kiosk vertelt het verhaal van het grootste paardengraf van Europa: 67 oorlogspaarden die in 2010 werden ontdekt bij Borgharen, en de archeologische discussie over de datering (beleg van 1632 door Frederik Hendrik, of 1673 door Lodewijk XIV).

**Zes schermen:**

| Scherm | Onderwerp |
|---|---|
| Home | Inleiding en kernfeiten |
| Ontdekking | De vondst in mei 2010 |
| Vondsten | Skeletten, hoefijzers, musketkogels — en het skelet naast de iPad |
| Datering | 1632 of 1673? De twee theorieën vergeleken |
| Verhaal | Hoe archeoloog Wim Dijkman het mysterie oploste |
| Video | Videoreportage |

## Installatie op de iPad

1. Kopieer de volledige map naar de iPad (via AirDrop, Finder of een USB-verbinding).
2. Open `index.html` in **Safari**.
3. Voor kioskmodus (bezoeker kan de iPad niet verlaten): activeer **Begeleide toegang** via *Instellingen → Toegankelijkheid → Begeleide toegang*.

De app werkt volledig offline — er is geen wifi of internetverbinding nodig.

## Bestanden

```
index.html                                  ← de volledige app
foto_W.Lem1.jpg                             ← opgraving, close-up skeletten
foto_W.Lem2.jpg                             ← open dag 2010
Luchtopnames 2010.jpg                       ← luchtfoto van de opgraving
Skelet in Helpoort.jpg                      ← het skelet in de vitrine (Helpoort)
Wim Dijkman-In Helpoort.jpg                 ← archeoloog Dijkman bij het skelet
Lodewijck XIV voor Maastricht.jpg           ← schilderij Lodewijk XIV te paard
Schilderij-Joseph_parrocel.jpg              ← gevechtsscène beleg 1673 (Parrocel)
Paardengraf Borgharen toch weer ouder.mp4   ← videoreportage
Paardengraf.txt / .docx                     ← bronmateriaal (niet ingeladen)
```

## Techniek

Één zelfstandig HTML-bestand zonder externe afhankelijkheden. Geen buildstap, geen server, geen frameworks. Ontworpen voor portret- en landschapsoriëntatie op iPad.
