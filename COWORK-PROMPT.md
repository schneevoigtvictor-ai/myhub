# myHUB – Wöchentlicher Update-Prompt (KW-Template)

Diesen Prompt am Anfang jeder neuen Cowork-Session kopieren und **[KW XX]** sowie **[DATUM]** anpassen.

---

## Prompt (kopieren ab hier)

```
Ich möchte mein KI-Dashboard myHUB für KW [XX]/2026 aktualisieren. Heute ist [DATUM, z.B. 04.04.2026].

Lies zuerst notes.md und dann index.html, damit du Struktur, Marker und aktuellen Stand kennst. Ändere danach NUR die JSON-Blöcke zwischen den COWORK-UPDATE Markern – kein HTML, kein CSS, kein JavaScript anfassen.

---

### Mein Profil (für alle Einordnungen nutzen)

Ich bin Victor Schneevoigt, Business Analyst bei der SBK (gesetzliche Krankenkasse). Ich arbeite in folgenden Rollen gleichzeitig – jede News und jedes Video soll aus allen relevanten Perspektiven eingeordnet werden:

1. **Business Analyst & Requirements Engineer**: Anforderungsmanagement, Prozessmodellierung, User Stories, Jira-Tickets, Fachkonzepte, Abstimmung mit IT und Fachbereichen
2. **Prompt Engineer**: Entwickle und optimiere Prompts für KI-gestützte Aufgaben im BA-Alltag (Dokumentation, Anforderungserhebung, Testfälle, Zusammenfassungen)
3. **HTML-Tool-Entwickler**: Baue Single-file HTML-Tools für das BA-Team der SBK – ohne Backend, ohne Framework, mit Vanilla JS. Tools sollen praxisnah und ohne Programmierkenntnisse bedienbar sein.
4. **Ideengeber für den SBK KI-Buddy**: Entwickle Konzepte für einen internen KI-Assistenten für das BA-Team – Use Cases, Anforderungen, Einschränkungen durch GKV-Regulierung und DSGVO.

Thematische Schwerpunkte: KI in der Dokumentation und im Requirements Engineering, Automatisierung von BA-Aufgaben (Ticketing, Protokolle, User Stories), KI-Tools ohne Programmierkenntnisse, EU AI Act und regulatorische Entwicklungen für GKV, NotebookLM und Wissensmanagement, Open Source KI (lokale Modelle, Datenschutz), n8n-Automatisierung.

---

### 1. HIGHLIGHTS aktualisieren (4–6 Einträge)

Recherchiere auf ALLEN folgenden Quellen die wichtigsten KI-Entwicklungen der letzten 7 Tage:

Deutsch:
- https://the-decoder.de/
- https://www.heise.de/themen/ki/
- https://t3n.de/tag/kuenstliche-intelligenz/
- https://www.golem.de/specials/artificial-intelligence/
- https://www.computerwoche.de/thema/kuenstliche-intelligenz/
- https://www.zdnet.de/thema/kuenstliche-intelligenz/
- https://www.ainauten.de/
- https://www.snipki.com/

International (auf Relevanz für deutschen/GKV-Markt prüfen):
- https://the-decoder.com/
- https://www.theverge.com/ai-artificial-intelligence
- https://techcrunch.com/category/artificial-intelligence/

Filtere nach dieser Priorität (absteigend):
1. HÖCHSTE PRIO: Direkt relevant für BAs im Gesundheitswesen / GKV (Regulierung, Datenschutz, Prozesse, ePA, KI-Buddy-Konzepte)
2. HOHE PRIO: Neue KI-Tools ohne Programmierkenntnisse (Claude, ChatGPT, Gemini, NotebookLM, n8n, Make, etc.) – besonders relevant für Prompt Engineering und HTML-Tool-Entwicklung
3. MITTLERE PRIO: Open Source KI, lokale Modelle (Datenschutz-Aspekt für GKV besonders relevant)
4. NIEDRIGE PRIO: Rein technische Entwicklungen für Entwickler

Kategorien:
- 🤖 Modelle & Strategie (neue Modelle, Benchmarks, Strategieentscheidungen)
- 🛠️ Praxis & Werkzeuge (konkret nutzbare Tools, Features, Workflows)
- ⚖️ Regulierung & GKV (EU AI Act, Datenschutz, ePA, Digitalisierung Gesundheitswesen)

Felder pro Item: titel, insight, quelle, url, relevanz (hoch/mittel/niedrig)

Das insight-Feld deckt alle vier Rollen ab – schreibe für jede Rolle einen konkreten Satz:
- Als BA: "Für Anforderungsdokumente bedeutet das...", "Im nächsten Sprint könntest du...", "Für Prozessmodellierung relevant, weil..."
- Als Prompt Engineer: "Dieser Ansatz lässt sich als Prompt umsetzen, indem...", "Für den System-Prompt des KI-Buddys relevant, weil..."
- Als HTML-Tool-Entwickler: "Könnte als Feature in einem BA-Tool umgesetzt werden...", "Zeigt ein Pattern für Single-file-Tools..."
- Als KI-Buddy-Ideengeber: "Möglicher Use Case für den SBK KI-Buddy...", "Einschränkung durch DSGVO beachten, weil..."

Qualitätskriterien:
- Mindestens 1 Eintrag mit relevanz "hoch"
- Mindestens 1 Eintrag aus Regulierung & GKV
- Keine allgemeinen Aussagen wie "KI wird wichtiger" – nur konkrete, handlungsrelevante Insights
- Quell-URLs müssen erreichbar und aktuell (max. 7 Tage alt) sein

---

### 2. NEWS aktualisieren (10–16 Artikel)

Trage ALLE relevanten Artikel aus der Recherche oben ein. Kategorien:
- 🚀 Modelle: Claude, ChatGPT/OpenAI, Gemini, Open-Source-Modelle (Llama, Mistral, Ollama etc.)
- 🛠️ Tools: NotebookLM, KI-Produktivitätstools, n8n-Automatisierung, HTML/No-Code-Tools
- 🏢 Unternehmen: KI-Strategie, Investitionen, Partnerschaften, neue Produkte
- ⚖️ Regulierung: EU AI Act, DSGVO, GKV/ePA-Digitalisierung, Compliance

Breite Abdeckung: lieber 3–4 News pro Kategorie als 10 in einer. Keine Artikel älter als 14 Tage.

Felder: titel, quelle, zusammenfassung (2–3 Sätze, neutral), einordnung, url

Das einordnung-Feld deckt alle vier Rollen ab – schreibe für jede Rolle einen konkreten Satz:
- Als BA: Was bedeutet das für Anforderungen, Prozesse, Meetings oder GKV-Regulierung?
- Als Prompt Engineer: Welche Prompt-Strategien oder -Muster ergeben sich daraus?
- Als HTML-Tool-Entwickler: Gibt es Features oder Patterns für Single-file-BA-Tools?
- Als KI-Buddy-Ideengeber: Ist das ein möglicher Use Case, eine Einschränkung oder ein Argument für den internen KI-Assistenten der SBK?

---

### 3. YOUTUBE aktualisieren (5–8 Videos)

**WICHTIG: Nur echte YouTube-Video-IDs verwenden – KEINE Platzhalter.**
Navigiere direkt auf youtube.com, öffne die Video-Seiten und lies echte IDs und Kapitel-Timestamps aus den Beschreibungen.

Bevorzugte Kanäle (immer zuerst prüfen, in dieser Reihenfolge):
- **Everlast AI** (Deutsch, sehr praxisnah, höchste Priorität)
- AI News Daily
- Alexander Eggers
- Jonas Keil / Sascha Hoffmann / Julian Ivanov / David Borst
- ainauten, snipKI – Jens Polomski

YouTube-Suchbegriffe (alle durchsuchen, beste Videos auswählen):
- "Everlast AI" (direkt Kanal aufrufen)
- "Claude AI Tutorial deutsch 2026"
- "ChatGPT Workflow Automatisierung deutsch"
- "Google Gemini Tutorial deutsch 2026"
- "NotebookLM Tutorial deutsch"
- "Open Source KI lokal deutsch Ollama Llama"
- "n8n Tutorial deutsch 2026"
- "KI Business Analyst Werkzeuge"
- "KI Gesundheitswesen Deutschland 2026"
- "Prompt Engineering deutsch Tutorial"
- "AI Tools Büro ohne Programmieren deutsch"

Themen-Priorität:
1. Claude / Anthropic Neuigkeiten und Tutorials
2. ChatGPT / OpenAI Neuigkeiten und Tutorials
3. Google Gemini Tutorials und Features
4. NotebookLM – Features, Anwendungsfälle, Tutorials
5. Open Source KI (Llama, Mistral, Ollama, lokale Modelle)
6. n8n + KI-Automatisierung
7. KI-Tools für Nicht-Entwickler und Prompt Engineering
8. KI im Gesundheitswesen / GKV

Felder: kanal, titel, link (https://www.youtube.com/watch?v=VIDEO_ID), video_id, thumbnail (https://img.youtube.com/vi/VIDEO_ID/mqdefault.jpg), datum_de (TT.MM.JJJJ), zusammenfassung, mehrwert, timestamps (echte Kapitel aus Videobeschreibung), archiv (false = letzte 14 Tage, true = älter)

Das mehrwert-Feld deckt alle vier Rollen ab – schreibe für jede Rolle einen konkreten Satz:
- Als BA: Was lässt sich direkt in Anforderungen, Prozessen oder Meetings anwenden?
- Als Prompt Engineer: Welches gezeigte Pattern oder welche Struktur lässt sich als Prompt übernehmen?
- Als HTML-Tool-Entwickler: Welches Feature oder welche Idee könnte in einem BA-Tool umgesetzt werden?
- Als KI-Buddy-Ideengeber: Was zeigt das Video als möglichen Use Case oder als Einschränkung für den SBK KI-Buddy?

---

### 4. Vorgehen

1. Lies notes.md und index.html (Marker und Struktur verstehen)
2. Recherchiere News und Highlights via WebSearch auf den genannten Quellen
3. Navigiere auf youtube.com, suche mit den genannten Begriffen, prüfe bevorzugte Kanäle, lies echte Video-IDs und Kapitel-Timestamps aus
4. Schreibe HIGHLIGHTS, NEWS und YOUTUBE in einem Schritt in index.html (nur JSON-Blöcke zwischen den Markern)
5. Validiere die JSON-Syntax per Python-Skript
6. Gib eine kurze Zusammenfassung: Anzahl Items pro Block, Top-Themen der Woche, welche Rollen besonders viele relevante News hatten
```

---

## Hinweise zur Nutzung

**Wo ist diese Datei?**
`C:\Users\schne\Desktop\Claude\repos\myhub\COWORK-PROMPT.md` – im Git-Repo, immer versioniert.

**Wie verwenden?**
1. Neue Cowork-Session starten
2. Diese Datei öffnen
3. Den Prompt-Block (alles zwischen den ` ``` `) kopieren
4. `[KW XX]` und `[DATUM]` ersetzen
5. In den Chat einfügen → Abschicken

**Wöchentlichen Schwerpunkt setzen?**
Am Ende des Prompts (vor dem letzten ` ``` `) anfügen:
> *"Schwerpunkt diese Woche: [z.B. EU AI Act Updates / NotebookLM Audio / n8n MCP-Integration]"*

**Prompt anpassen wenn:**
- Neuer bevorzugter YouTube-Kanal → unter "Bevorzugte Kanäle" eintragen
- Neue Rolle oder neuer Schwerpunkt → im Profil-Abschnitt ergänzen + notes.md aktualisieren
- Neue Highlight-Kategorie → in notes.md + im Prompt ergänzen

---

## Changelog

| Datum | Version | Änderung |
|---|---|---|
| 27.03.2026 | v1.0 | Initiale Version, basierend auf KW13-Update |
| 27.03.2026 | v1.1 | Everlast AI als bevorzugter YouTube-Kanal ergänzt |
| 27.03.2026 | v1.2 | Themen erweitert: NotebookLM, Open Source KI, Gemini, ChatGPT; Microsoft Copilot entfernt |
| 27.03.2026 | v2.0 | Vollständige Überarbeitung: Quell-URLs, YouTube-Suchbegriffe und vollständiges Nutzerprofil (BA + Prompt Engineer + HTML-Tool-Entwickler + KI-Buddy-Ideengeber) wieder aufgenommen; Insight/Einordnung/Mehrwert jetzt für alle 4 Rollen |
| 27.03.2026 | v2.1 | Insight/Einordnung/Mehrwert: alle 4 Rollen verpflichtend (nicht nur "mindestens eine") |
