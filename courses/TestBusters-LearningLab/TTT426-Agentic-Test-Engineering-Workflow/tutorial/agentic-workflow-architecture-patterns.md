# Agentic Workflow Architecture Patterns

## Ziel dieses Dokuments

Dieses Dokument beschreibt bewährte Architekturmuster für Agentic Workflows. Es dient als konzeptionelle Grundlage für den TTT426 Agentic Test Engineering Workflow.

---

# 1. Von einem LLM zu einem Agentic System

## Single Prompt

```text
User
  │
  ▼
LLM
  │
  ▼
Antwort
```

Geeignet für kleine Aufgaben.

Nachteile:

- keine Spezialisierung
- keine Wiederverwendung
- kaum Governance
- begrenzte Nachvollziehbarkeit

---

## Single Agent

```text
User
   │
   ▼
Test Engineer Agent
   │
   ▼
Artefakte
```

Ein Agent besitzt Rollenbeschreibung, Wissen und Tools.

Geeignet für klar abgegrenzte Aufgaben.

---

## Multi-Agent System

```text
                Orchestrator
                      │
     ┌────────────────┼───────────────┐
     ▼                ▼               ▼
 Business       Test Analysis     Test Design
  Analyst           Agent            Agent
     │                │               │
     └──────────────┬─┴───────────────┘
                    ▼
             Review Agent
```

Jeder Agent übernimmt genau eine Verantwortung.

---

# 2. Orchestrator Pattern

Der Orchestrator koordiniert den gesamten Workflow.

Aufgaben:

- Agent auswählen
- Kontext bereitstellen
- Reihenfolge steuern
- Ergebnisse speichern
- Fehler behandeln
- Human Reviews einfordern

Der Orchestrator enthält möglichst wenig Fachlogik.

---

# 3. Planner Pattern

Ein Planner zerlegt große Aufgaben.

Beispiel

```text
"Erstelle Teststrategie"

↓

Analyse

↓

Teilaufgaben

↓

Agenten auswählen

↓

Ergebnisse zusammenführen
```

Der Planner entscheidet, welche Agenten benötigt werden.

---

# 4. Supervisor Pattern

Der Supervisor bewertet Ergebnisse.

Er überprüft beispielsweise:

- Vollständigkeit
- Konsistenz
- Richtlinien
- Qualität

Er erzeugt selbst keine fachlichen Artefakte.

---

# 5. LLM-as-a-Judge

Ein spezieller Agent bewertet Ergebnisse anderer Agenten.

Beispiel

```text
Test Cases

↓

Judge Agent

↓

Score

↓

Verbesserungsvorschläge
```

Typische Kriterien:

- ISTQB-Konformität
- Lesbarkeit
- Vollständigkeit
- Risikoabdeckung
- Traceability

---

# 6. Human in the Loop

Nicht jede Entscheidung sollte automatisiert werden.

Empfohlene Freigaben:

- Anforderungen
- Architektur
- Teststrategie
- Release

---

# 7. Workflow Pattern

```text
Requirements
      │
      ▼
Test Context

      ▼
Test Analysis

      ▼
Test Design

      ▼
Automation

      ▼
Execution

      ▼
Reporting
```

Jede Stufe besitzt klar definierte Ein- und Ausgaben.

---

# 8. Event Driven Pattern

Agenten reagieren auf Ereignisse.

Beispiele:

- Pull Request erstellt
- User Story geändert
- Test fehlgeschlagen
- Build erfolgreich

Dadurch entstehen automatische Workflows.

---

# 9. Memory Pattern

## Short-Term Memory

Kontext der aktuellen Aufgabe.

Beispiele:

- Chatverlauf
- aktuelle User Story
- aktuelle Testfälle

## Long-Term Memory

Dauerhaftes Wissen.

Beispiele:

- Test Policy
- Coding Guidelines
- ISTQB
- Architektur

---

# 10. RAG Pattern

Retrieval Augmented Generation erweitert den Kontext.

```text
Frage

↓

Retriever

↓

Dokumente

↓

LLM

↓

Antwort
```

Geeignete Quellen:

- Markdown
- Wiki
- Confluence
- Git Repository
- PDF
- Datenbanken

---

# 11. MCP Pattern

Model Context Protocol standardisiert den Zugriff auf externe Systeme.

Typische Integrationen:

- GitHub
- Jira
- Test Management
- Dateisystem
- Datenbanken
- CI/CD
- Browser
- APIs

Der Agent nutzt Werkzeuge statt Informationen zu erfinden.

---

# 12. Tool Calling Pattern

Agenten führen Aktionen aus.

Beispiele:

- Git Commit
- Jira Ticket erstellen
- Test ausführen
- SQL ausführen
- REST API aufrufen

---

# 13. Artifact Pattern

Artefakte bilden die Kommunikation zwischen Agenten.

```text
User Story

↓

Test Conditions

↓

Test Cases

↓

Automation

↓

Test Report
```

Alle Artefakte sollten versioniert werden.

---

# 14. Skill Pattern

Skills sind wiederverwendbare Fachbausteine.

Beispiele:

- Risk Based Testing
- Boundary Value Analysis
- REST Testing
- Playwright
- Security Testing

Agenten kombinieren mehrere Skills.

---

# 15. Guardrail Pattern

Guardrails definieren Grenzen.

Beispiele:

- Keine Halluzinationen akzeptieren
- Quellen angeben
- Unternehmensrichtlinien beachten
- Entscheidungen begründen

---

# 16. Quality Gate Pattern

Zwischen Agenten werden Ergebnisse geprüft.

```text
Generate

↓

Review

↓

Improve

↓

Approve
```

Fehler werden früh erkannt.

---

# 17. Agent Registry

Jeder Agent sollte dokumentiert sein.

Beispiel:

- Name
- Rolle
- Verantwortlichkeiten
- Eingaben
- Ausgaben
- Skills
- Tools
- Guardrails

---

# 18. Architektur für TTT426

```text
                   Orchestrator
                         │
     ┌───────────────────┼────────────────────┐
     ▼                   ▼                    ▼
 Product Context   Test Analysis      Test Design
      Agent            Agent             Agent
     │                   │                  │
     ├──────────────┐     │                  │
     ▼              ▼     ▼                  ▼
 Test Data     Automation Agent      Exploratory Agent
     │              │                  │
     └──────────────┴────────────┐
                                 ▼
                          Review Agent
                                 │
                                 ▼
                       Quality Gate Agent
                                 │
                                 ▼
                          Human Approval
```

---

# Architekturprinzipien

- Kleine spezialisierte Agenten
- Gemeinsame Wissensbasis
- Versionierte Artefakte
- Standardisierte Handovers
- Wiederverwendbare Skills
- Qualität vor Geschwindigkeit
- Human-in-the-Loop an kritischen Entscheidungen
- Nachvollziehbarkeit und Auditierbarkeit

---

# Fazit

Ein Agentic Workflow besteht nicht aus einem intelligenten Agenten, sondern aus einem
koordinierten System spezialisierter Agenten. Die Architektur definiert Rollen,
Informationsfluss, Qualitätskontrollen und Governance. Das LLM ist nur eine Komponente.
Die eigentliche Intelligenz entsteht durch die Struktur des Workflows.