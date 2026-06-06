# ⛳ ScoreCaddie

**De slimste scorekaart voor golfers.** Geen GPS, geen abonnement, geen gedoe. Gewoon bijhouden wie wint — inclusief automatische handicap verrekening.

## Wat doet ScoreCaddie?

- **Handicap berekening** — vul je handicap index in, de app berekent automatisch hoeveel slagen je krijgt op elke hole
- **Live stand** — direct zien wie wint tijdens de ronde, niet pas achteraf
- **Vier spelformats** — Stableford, Matchplay, Strokeplay en 6-punten (3 spelers)
- **Tot 20 spelers** — ideaal voor een familietoernooi
- **Extra wedstrijdjes** — Nearest the Pin en Longest Drive bijhouden
- **Gedeelde banen** — banen ophalen die anderen al hebben ingevoerd

## Installeren op je iPhone

1. Open Safari op je iPhone
2. Ga naar: **reenderbeks.github.io/ScoreCaddie/ScoreCaddie.html**
3. Tik op het deel-icoontje (vierkantje met pijltje omhoog)
4. Tik op **"Zet op beginscherm"**
5. Klaar — ScoreCaddie staat als app op je homescreen

## Een baan toevoegen via Claude of ChatGPT

Je hoeft geen baangegevens handmatig in te tikken. Gebruik Claude (claude.ai) of ChatGPT om de data automatisch uit een scorekaart te halen.

### Stap 1 — Maak twee screenshots

- **Screenshot 1:** de baanhandicap tabel van de baan (met CR, Slope en Par per tee-kleur voor heren en dames)
- **Screenshot 2:** de scorekaart (met par en SI/stroke index per hole)

Deze vind je op de website van de golfclub of op de fysieke scorekaart.

### Stap 2 — Stuur naar Claude of ChatGPT

Ga naar claude.ai of chatgpt.com, upload de twee screenshots en stuur dit bericht:

---

Analyseer de bijgevoegde scorekaart en handicaptabel en geef me de baangegevens in dit exacte JSON formaat. Geef ALLEEN de JSON terug, geen uitleg:

```json
{
  "name": "Naam van de baan",
  "holes": 18,
  "tees": [
    {
      "color": "yellow",
      "crM": 72.5,
      "srM": 135,
      "parM": 72,
      "crF": 78.9,
      "srF": 143,
      "parF": 72
    }
  ],
  "siData": [
    {"par": 4, "si": 8},
    {"par": 3, "si": 16}
  ]
}
```

Gebruik voor color: white, yellow, blue, red, orange, black of gold. Voeg alle tee-kleuren toe. siData bevat alle holes op volgorde van hole 1 t/m 18 (of 1 t/m 9 voor een 9-holes baan).

**Belangrijk:** ScoreCaddie is een eigen app — Claude of ChatGPT kent het format niet automatisch. Kopieer de bovenstaande prompt inclusief het JSON voorbeeld, dan werkt het gegarandeerd.

---

### Stap 3 — Importeer in ScoreCaddie

1. Kopieer de JSON die Claude/ChatGPT teruggeeft
2. Open ScoreCaddie → tik op **Gedeelde banen**
3. Scroll naar beneden naar **"Baan toevoegen via Claude/ChatGPT"**
4. Plak de JSON in het tekstveld
5. Tik op **"Verwerk en deel"**
6. Vul je naam in — de baan wordt opgeslagen op jouw telefoon én gedeeld met alle ScoreCaddie gebruikers

## Spelformats

| Format | Beschrijving | Spelers |
|--------|-------------|---------|
| Stableford | Punten per hole op basis van score vs par | 1-20 |
| Matchplay | Hole voor hole, live stand | 2 |
| Strokeplay | Totaal slagen, netto en bruto | 1-20 |
| 6-punten | Per hole 6 punten te verdelen | 3 |

## Handicap berekening

ScoreCaddie gebruikt de officiële WHS formule:

**Baanhandicap = Handicap Index × (Slope / 113) + (CR - Par)**

Voor 9-holes rondes wordt de handicap index eerst gehalveerd, conform de NGF methode.

## Tips

- **Team matchplay** — maak twee "spelers" aan met de gemiddelde handicap van elk team
- **Baan verwijderen** — via Banen beheren kun je banen die je niet meer nodig hebt verwijderen
- **Meerdere apparaten** — laad je banen via Gedeelde banen op elk nieuw apparaat

## Technisch

ScoreCaddie is een Progressive Web App (PWA) — een gewone webpagina die werkt als app. Geen App Store, geen installatie, geen updates nodig. Je data wordt lokaal opgeslagen op je telefoon. Banen worden gedeeld via Firebase (Google).

---

Gemaakt met ❤️ en ⛳ — feedback welkom!
