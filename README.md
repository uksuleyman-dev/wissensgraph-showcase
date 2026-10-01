# KI-Second-Brain / Wissensgraph — Showcase

> Datenschutzfreundlicher Showcase eines Git-basierten persönlichen Wissenssystems, das menschliche Notizen, KI-Agenten, strukturiertes Gedächtnis und mehrere Clients miteinander verbindet.

## Warum ich dieses System gebaut habe

Chats, Projektentscheidungen, Recherchen und operatives Wissen verteilen sich schnell auf unterschiedliche Anwendungen. Mein Ziel war deshalb ein System, in dem relevantes Wissen nicht mit einer einzelnen Unterhaltung verschwindet, sondern als wiederverwendbare und versionierte Wissensbasis erhalten bleibt.

Das private Produktiv-Repository dient dabei als **Single Source of Truth**. KI-Agenten können gezielt relevanten Kontext abrufen, bestätigte Entscheidungen und Projektfortschritte einarbeiten und den Wissensbestand aktuell halten – ohne vollständige Chatverläufe wahllos zu archivieren.

Dieses öffentliche Repository enthält bewusst **keine privaten Notizen, Zugangsdaten, personenbezogenen Daten oder Produktivinhalte**. Es zeigt ausschließlich Architektur, Prinzipien und anonymisierte Beispiele.

## Architektur

```text
ChatGPT / KI-Agenten / Hermes
            │
            ▼
   Wissensextraktion
   + Relevanzfilterung
            │
            ▼
┌───────────────────────────┐
│ GitHub-Wissensbasis       │
│ Single Source of Truth    │
│ Markdown + Git-Historie   │
└─────────────┬─────────────┘
              │
       ┌──────┴──────┐
       ▼             ▼
    Obsidian       Logseq
       │             │
       └──────┬──────┘
              ▼
       Menschliche Prüfung
```

## Wissensmodell

Der produktive Vault ist nach Verantwortungsbereichen statt nach einzelnen Anwendungen strukturiert:

| Bereich | Zweck |
|---|---|
| `Projekte/` | Aktive und abgeschlossene Vorhaben |
| `Wissen/` | Wiederverwendbares Wissen, Recherchen und Verfahren |
| `CRM/` | Beziehungs- und Kommunikationskontext |
| `Journal/` | Tagesnotizen und Entscheidungen |
| `Hermes/` | Agenten-Workflows, Aufgaben und Automationen |
| `Vorlagen/` | Wiederverwendbare Notizvorlagen |

Die Notizen bestehen aus Markdown und werden über Wiki-Links wie `[[Wissen/...]]` und `[[Projekte/...]]` miteinander verbunden. Dadurch entsteht aus einzelnen Dateien ein navigierbarer Wissensgraph.

## Agenten-Workflow

1. Nur den für die aktuelle Aufgabe relevanten Kontext abrufen.
2. Rohunterhaltung von dauerhaft relevantem Wissen unterscheiden.
3. Bestätigte Entscheidungen, Projektfortschritte, wiederverwendbare Verfahren und belastbare Rechercheergebnisse speichern.
4. Bestehende Notizen gezielt ergänzen, statt sie pauschal zu ersetzen.
5. Zusammengehörige Wissensknoten miteinander verlinken.
6. Secrets, Tokens, Kontodaten und unnötige Rohtranskripte aus dem Wissensgraphen heraushalten.
7. Jede dauerhafte Änderung über Git versionieren.

## Architekturprinzipien

- **Git als Single Source of Truth** — Versionshistorie, Diffs, Rollback und Nachvollziehbarkeit sind Teil des Systems.
- **Human-in-the-Loop** — KI unterstützt die Wissenspflege; bei relevanten Entscheidungen bleibt der Mensch die Freigabeinstanz.
- **Selektives Gedächtnis** — gespeichert wird wiederverwendbares Wissen statt vollständiger Chatarchive.
- **Kontextminimierung** — Agenten laden nur die Informationen, die für eine Aufgabe benötigt werden.
- **Privacy by Design** — Zugangsdaten und unnötige sensible Rohdaten gehören nicht in den Wissensgraphen.
- **Tool-Unabhängigkeit** — Markdown hält die Daten zwischen GitHub, Obsidian, Logseq und zukünftigen Clients portabel.
- **Agenten-Interoperabilität** — mehrere Agenten arbeiten auf gemeinsamen Regeln und demselben versionierten Wissensstand.

## Was dieses Projekt technisch demonstriert

Das Projekt ist für mich weniger eine Notiz-App als eine **Systemarchitektur-Aufgabe**: Eine kanonische Datenquelle definieren, Verantwortlichkeiten trennen, Informationsflüsse gestalten, mehrere KI-Agenten koordinieren, Zustand persistent halten, Änderungen nachvollziehbar machen und verschiedene Clients um ein gemeinsames Datenmodell integrieren.

Gerade im Data-/AI-Kontext ist der vollständige Lebenszyklus interessant:

```text
unstrukturierte Interaktion
          ↓
Relevanzprüfung / Validierung
          ↓
strukturiertes Wissen
          ↓
versionierte Persistenz
          ↓
Abruf durch Menschen & Agenten
          ↓
neue Entscheidungen / Aktualisierungen
```

## Größenordnung des Produktivsystems

Zum Zeitpunkt der Erstellung dieses Showcases umfasst das private Repository rund **170 versionierte Dateien und Verzeichnisse**. Dazu gehören unter anderem Tagesjournale, Projektnotizen, wiederverwendbares Wissen, Agenten-Memory und Workflow-Definitionen sowie eine erzeugte Graphdarstellung.

## Inhalt dieses Repositories

- `README.md` — öffentliche Projektübersicht
- `ARCHITECTURE.md` — technische Architektur und Designentscheidungen
- `examples/` — anonymisierte Beispiele des Wissensmodells

## Datenschutz

Der tatsächliche Wissensgraph bleibt privat. Dieser Showcase bildet bewusst nur **Architektur, Muster und anonymisierte Beispiele** ab – nicht die darin gespeicherten persönlichen Informationen.

---

Entstanden als praktisches Projekt zu **KI-gestützter Wissensarchitektur, Agentengedächtnis, Informationsflüssen und Git-basiertem Lifecycle-Management**.
