# myHUB – Projektdokumentation

## Was ist myHUB?

myHUB ist ein persönliches KI- und Portfolio-Dashboard als Single-file HTML-Anwendung. Es wird auf GitHub Pages gehostet und über Claude Cowork wöchentlich aktualisiert.

- **Zielgruppe:** Victor (Business Analyst bei der SBK) und sein BA-Team
- **Zweck:** Wöchentliche KI-News kuratiert für Business Analysten + persönliches Portfolio-Tracking
- **URL:** https://schneevoigtvictor-ai.github.io/myhub
- **Repo:** https://github.com/schneevoigtvictor-ai/myhub

---

## Architektur

### Grundprinzipien

- **Single-file HTML:** Alles in einer index.html — kein Build, kein Framework, kein Backend
- **Vanilla JS + CSS:** Keine Libraries außer System-Fonts
- **Kein Backend:** Alle Daten sind als JSON-Konstanten direkt im HTML eingebettet
- **Kein API-Key nötig:** Daten werden über Claude Cowork manuell aktualisiert
- **Persönliche Daten im localStorage:** Watchlist, Kaufpreise, Stückzahlen (nicht im HTML)
- **Öffentliche Daten im HTML:** News, Highlights, YouTube-Videos, Aktienkurse, Links

### Datei-Struktur im Repo

```
myhub/
├── index.html          ← Die gesamte Anwendung
├── COWORK-PROMPT.md    ← Template für wöchentliche Updates
├── notes.md            ← Diese Datei (Projektdokumentation)
└── README.md           ← Optional: Kurzbeschreibung für GitHub
```

---

## Datenblöcke (COWORK-UPDATE)

Die Inhalte werden über klar markierte JSON-Blöcke im `<script>`-Bereich verwaltet. Claude Cowork findet diese Blöcke über die Marker und ersetzt den Inhalt per str_replace.

### COWORK-UPDATE: HIGHLIGHTS

**Zweck:** Kuratierte KI-Entwicklungen, gefiltert und bewertet für Business Analysten.
**Position im Tool:** Tab "Highlights" (Startseite)

```json
{
  "kategorien": [
    {
      "emoji": "🤖",
      "titel": "Modelle & Strategie",
      "items": [
        {
          "titel": "Überschrift des Highlights",
          "insight": "Was bedeutet das konkret für einen BA bei der SBK",
          "quelle": "Name der Quelle",
          "url": "https://link-zum-artikel.de",
          "relevanz": "hoch"  // hoch | mittel | niedrig
        }
      ]
    }
  ]
}
```

**Kategorien:** Modelle & Strategie, Preise & Lizenzen, Praxis & Werkzeuge

### COWORK-UPDATE: NEWS

**Zweck:** Alle KI-News der Woche, ungefiltert. Highlights werden daraus abgeleitet.
**Position im Tool:** Tab "KI-News"

```json
{
  "kategorien": [
    {
      "emoji": "🚀",
      "titel": "Modelle",
      "artikel": [
        {
          "titel": "Artikelüberschrift",
          "quelle": "Quellenname",
          "zusammenfassung": "2-3 Sätze",
          "einordnung": "Bedeutung / Kontext",
          "url": "https://..."
        }
      ]
    }
  ]
}
```

**Kategorien:** Modelle, Tools, Unternehmen, Regulierung

### COWORK-UPDATE: YOUTUBE

**Zweck:** Relevante KI-Videos mit Zusammenfassungen und Zeitstempeln.
**Position im Tool:** Tab "YouTube" (Letzte 2 Wochen + Archiv)

```json
{
  "aktualisiert": "2026-03-26T08:00:00Z",
  "videos": [
    {
      "kanal": "Kanalname",
      "titel": "Videotitel",
      "link": "https://www.youtube.com/watch?v=VIDEO_ID",
      "video_id": "VIDEO_ID",
      "thumbnail": "https://img.youtube.com/vi/VIDEO_ID/mqdefault.jpg",
      "datum_de": "26.03.2026",
      "zusammenfassung": "Worum geht es",
      "mehrwert": "Was bringt das einem BA",
      "timestamps": [
        { "zeit": "02:15", "sekunden": 135, "beschreibung": "API-Key einrichten" }
      ],
      "archiv": false
    }
  ]
}
```

**Hinweis:** `archiv: false` = Letzte 2 Wochen, `archiv: true` = Archiv-Bereich

### COWORK-UPDATE: STOCKS

**Zweck:** Aktienkurse und Kennzahlen für das Portfolio.
**Position im Tool:** Tab "Portfolio" (Detailansicht)

```json
{
  "aktualisiert": "2026-03-26T18:00:00Z",
  "aktien": [
    {
      "wkn": "840400",
      "name": "Allianz",
      "ticker": "ALV.DE",
      "currency": "EUR",
      "price": 285.50,
      "change_1d_pct": 0.85,
      "change_1w_pct": 2.10,
      "change_1m_pct": -1.30,
      "change_1y_pct": 15.20,
      "week52_high": 310.00,
      "week52_low": 240.00,
      "div_yield": 4.85,
      "div_rate": 13.80,
      "market_cap": "120.5B",
      "pe_ratio": 12.3,
      "sparkline": [280, 282, 279, 285, 283, 285.5],
      "analyst_rating": "Kaufen",
      "analyst_target": 320.00,
      "analyst_count": 28,
      "news": [
        { "titel": "...", "einordnung": "...", "quelle": "...", "datum": "...", "url": "..." }
      ],
      "fehler": null
    }
  ]
}
```

### COWORK-UPDATE: LINKS

**Zweck:** Kuratierte Ressourcen-Links (Newsletter, Portale).
**Position im Tool:** Tab "Highlights" unten

```json
[
  {
    "name": "Heise KI",
    "desc": "Führendes deutsches Tech-Magazin",
    "url": "https://www.heise.de/themen/ki/",
    "icon": "🇩🇪"
  }
]
```

---

## Portfolio-System

### Watchlist (localStorage)

Die persönliche Watchlist wird im Browser gespeichert unter dem Key `myHUB_wl_v4`.

```json
[
  {
    "name": "Allianz",
    "wkn": "840400",
    "ticker": "ALV.DE",
    "typ": "aktie",       // aktie | etf | krypto
    "kaufpreis": 250.00,   // optional, in EUR
    "stueckzahl": 10       // optional
  }
]
```

### Funktionen

- **Hinzufügen:** Button "Asset hinzufügen" öffnet Modal
- **Bearbeiten:** ✎-Button direkt an jedem Asset in der Liste
- **Löschen:** ✕-Button direkt an jedem Asset
- **Filter:** Chips für Alle / Aktien / ETFs / Krypto mit Kategorie-Zusammenfassung
- **Sortierung:** A-Z, % 1 Woche, Gewinn/Verlust
- **Export:** JSON-Download der Watchlist
- **Detailansicht:** Klick auf Asset öffnet Panel mit Kurs, Sparkline, 52W-Range, Performance, Kennzahlen, Position (G/V), News

### Gewinn/Verlust-Berechnung

```
Investiert = Kaufpreis × Stückzahl
Aktuell = aktueller Kurs × Stückzahl
G/V absolut = Aktuell - Investiert
G/V prozentual = (G/V absolut / Investiert) × 100
```

Wird nur angezeigt, wenn Kaufpreis UND Stückzahl vorhanden sind.

---

## Design-System

### Farbpalette (warm-light, Claude-inspiriert)

| Variable | Wert | Verwendung |
|----------|------|------------|
| `--bg` | #F7F5F0 | Seitenhintergrund |
| `--white` | #FFFFFF | Cards, Modals |
| `--acc` | #C4652A | Akzentfarbe (Terrakotta) |
| `--green` | #2E7D5B | Positive Werte |
| `--red` | #C0392B | Negative Werte |
| `--amber` | #B8860B | Mittlere Relevanz |
| `--blue` | #3B6DB5 | ETF-Badge |
| `--purple` | #7C5CBF | Aktie-Badge |
| `--cyan` | #1A8A8A | Krypto-Badge |

### Typografie

- System-Fonts (`-apple-system, Segoe UI, Roboto, ...`)
- Monospace für Zahlen und Kurse (`SF Mono, Menlo, Consolas, ...`)
- Keine externen Fonts (kein Google Fonts)

### Konventionen

- Border-Radius: 6px (klein), 10px (standard), 14px (groß)
- Schatten: minimal, warm (rgba(26,25,22,...))
- Hover: Border wird stärker + leichter Shadow
- Animations: `rise` (fadeUp 6px) für Einblendungen, `slideUp` für Panel
- Mobile-first, responsive ab 768px (2 Spalten) und 1024px (3 Spalten)

---

## Tab-Struktur

| Tab | Inhalt | Datenquelle |
|-----|--------|-------------|
| Highlights | Kuratierte KI-Insights für BAs | COWORK-UPDATE: HIGHLIGHTS |
| KI-News | Alle Artikel der Woche | COWORK-UPDATE: NEWS |
| YouTube | Videos mit Timestamps | COWORK-UPDATE: YOUTUBE |
| Portfolio | Persönliche Assets + Kurse | localStorage + COWORK-UPDATE: STOCKS |

Jeder Tab hat einen `section-intro` Block mit Titel und Beschreibung, der erklärt, was der Tab macht.

---

## Update-Workflow

### Manuell (aktuell)

1. Claude Cowork öffnen → Prompt aus `COWORK-PROMPT.md` einfügen
2. Cowork recherchiert und aktualisiert die JSON-Blöcke
3. Lokal prüfen → `git push`
4. GitHub Pages aktualisiert automatisch

### Automatisch (geplant)

GitHub Action mit Python-Skript und Claude API, die jeden Montag 7:00 Uhr läuft. Wird aufgesetzt, sobald der manuelle Workflow stabil läuft.

---

## Versionshistorie

| Version | Datum | Änderungen |
|---------|-------|------------|
| v1.0 | 27.03.2026 | Initiale Version: KI-News, YouTube, Portfolio |
| v1.1 | 27.03.2026 | Portfolio-Tracking mit Kaufpreis/Stückzahl/G-V |
| v2.0 | 27.03.2026 | Neue Struktur: Highlights als Kernfeature, YouTube erweitert |
| v2.1 | 27.03.2026 | Design-Overhaul (Linear/Vercel-inspiriert, dark) |
| v3.0 | 27.03.2026 | Warm-Light Theme (Claude-inspiriert), System-Fonts, UX-Verbesserung |
| v3.1 | 27.03.2026 | Echte Beispieldaten KW13, Edit/Delete Portfolio, besseres Wording |
| v3.2 | 27.03.2026 | Bugfix Links, Filter-Chips, Timestamp-Deep-Links, neue Ressourcen |

---

## Wichtige Regeln für Weiterentwicklung

1. **Alles bleibt in einer Datei.** Kein Aufteilen in separate CSS/JS-Dateien.
2. **Keine externen Dependencies.** Kein npm, kein CDN, keine Libraries.
3. **Keine API-Keys im HTML.** Persönliche Daten nur im localStorage.
4. **COWORK-UPDATE Marker nicht verändern.** Die Marker sind die Schnittstelle für Updates.
5. **JSON-Strukturen nicht umbenennen.** Feldnamen müssen stabil bleiben, damit Cowork sie wiedererkennt.
6. **Mobile-first.** Alles muss auf dem Handy funktionieren.
7. **Deutsch.** Alle sichtbaren Texte auf Deutsch. Kommentare im Code auf Deutsch.
