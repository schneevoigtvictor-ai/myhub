# myHUB – Wöchentliches Update via Claude Cowork

## Vorbereitung

- Claude Desktop mit Cowork und Chrome-Freigabe muss aktiv sein
- Das Repo muss lokal geklont sein: `C:\Users\Victor\repos\myhub`
- Vor dem Update einmal `git pull` ausführen, um auf dem neuesten Stand zu sein

---

## Cowork-Prompt (komplett kopieren)

```
Ich möchte mein KI-Dashboard aktualisieren.
Die Datei liegt unter C:\Users\Victor\repos\myhub\index.html

Bitte mache folgendes:

1. HIGHLIGHTS aktualisieren
   - Öffne Chrome und recherchiere auf heise.de/themen/ki, the-decoder.de und t3n.de/tag/kuenstliche-intelligenz die wichtigsten KI-Entwicklungen der letzten 7 Tage.
   - Erstelle daraus 4–6 Highlight-Einträge.
   - Ersetze den JSON-Block zwischen "COWORK-UPDATE: HIGHLIGHTS - START" und "COWORK-UPDATE: HIGHLIGHTS - ENDE".
   - Behalte die bestehende JSON-Struktur exakt bei.
   - Jeder Eintrag braucht:
     - titel: Was ist passiert
     - insight: Was bedeutet das konkret für einen Business Analysten bei einer Krankenkasse (SBK)
     - quelle: Name der Originalquelle
     - url: funktionierender Link zum Artikel
     - relevanz: hoch / mittel / niedrig
   - Verteile die Einträge auf die drei Kategorien: "Modelle & Strategie", "Preise & Lizenzen", "Praxis & Werkzeuge"

2. NEWS aktualisieren
   - Trage alle gefundenen Artikel in den Block "COWORK-UPDATE: NEWS" ein.
   - Aufgeteilt in die Kategorien: Modelle, Tools, Unternehmen, Regulierung.
   - Struktur pro Artikel: titel, quelle, zusammenfassung, einordnung, url.

3. YOUTUBE aktualisieren
   - Suche auf YouTube nach: "KI Tutorial deutsch", "Claude AI deutsch", "n8n Automatisierung deutsch", "KI Tools deutsch"
   - Trage die 5–8 relevantesten Videos der letzten 2 Wochen in "COWORK-UPDATE: YOUTUBE" ein.
   - Pro Video:
     - titel, kanal, link, video_id
     - thumbnail: https://img.youtube.com/vi/VIDEO_ID/mqdefault.jpg
     - datum_de: Datum im Format TT.MM.JJJJ
     - zusammenfassung: 2–3 Sätze, worum es geht
     - mehrwert: Was bringt das einem Business Analysten konkret
     - timestamps: Array mit zeit (z.B. "02:15"), sekunden (z.B. 135), beschreibung
     - archiv: false für aktuelle Videos, true für ältere

4. Speichere die Datei.
   WICHTIG: Ändere nichts am HTML, CSS oder JavaScript — nur die JSON-Datenblöcke zwischen den COWORK-UPDATE Markern.
```

---

## Nach dem Cowork-Update

```bash
# 1. Lokal prüfen
start C:\Users\Victor\repos\myhub\index.html

# 2. Wenn alles passt: pushen
cd C:\Users\Victor\repos\myhub
git add index.html
git commit -m "Update KW__"
git push
```

Die Live-Seite aktualisiert sich automatisch nach 1–2 Minuten:
https://schneevoigtvictor-ai.github.io/myhub

---

## Optionale Ergänzungen

### Nur Aktien-Kurse aktualisieren

```
Öffne C:\Users\Victor\repos\myhub\index.html.
Suche "COWORK-UPDATE: STOCKS - START".
Recherchiere über Chrome die aktuellen Kurse für alle Aktien und ETFs in meiner Watchlist (die Watchlist liegt im localStorage, aber die Ticker findest du auch in der Default-Watchlist im JavaScript).
Aktualisiere den STOCKS JSON-Block mit: name, ticker, wkn, price (in EUR), change_1d_pct, change_1w_pct, change_1m_pct, change_1y_pct, week52_high, week52_low, div_yield, div_rate, market_cap, pe_ratio.
Setze "aktualisiert" auf das aktuelle Datum im ISO-Format.
Speichere die Datei.
```

### Nur Links/Ressourcen prüfen

```
Öffne C:\Users\Victor\repos\myhub\index.html.
Suche "COWORK-UPDATE: LINKS - START".
Öffne jeden Link im Browser und prüfe, ob er funktioniert.
Ersetze defekte Links durch funktionierende Alternativen (deutschsprachige KI-Ressourcen).
Speichere die Datei.
```
