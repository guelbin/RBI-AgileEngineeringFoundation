# Grundlagen eines Agentic Workflows

## Was ist ein Agentic Workflow?

Ein Agentic Workflow ist ein strukturierter Prozess, in dem mehrere spezialisierte KI-Agenten zusammenarbeiten, um eine Aufgabe zu lösen. Im Gegensatz zu einem einzelnen Prompt wird die
Arbeit in klar definierte Schritte, Rollen und Übergaben aufgeteilt.

Ein Agentic Workflow besteht aus:

- Rollen (Agents)
- Aufgaben (Tasks)
- Wissen (Knowledge)
- Fähigkeiten (Skills)
- Regeln (Guardrails)
- Übergaben (Handovers)
- Qualitätsprüfungen (Quality Gates)

## Grundprinzip

```text
Anforderung
      │
      ▼
Analyse-Agent
      │
      ▼
Design-Agent
      │
      ▼
Implementierungs-Agent
      │
      ▼
Test-Agent
      │
      ▼
Review-Agent
      │
      ▼
Freigabe
```

Jeder Agent besitzt eine klar abgegrenzte Verantwortung und erzeugt definierte Artefakte.

## Die Bausteine

### 1. Rollen

Jeder Agent übernimmt eine fachliche Rolle, beispielsweise:

- Product Owner
- Business Analyst
- Software Architect
- Developer
- Test Engineer
- Test Automation Engineer
- Security Engineer
- Reviewer

### 2. Aufgaben

Jeder Agent erhält genau definierte Aufgaben.

Beispiel:

- Anforderungen analysieren
- Testbedingungen identifizieren
- Testfälle entwerfen
- Code implementieren
- Ergebnisse überprüfen

### 3. Kontext

Agenten benötigen Kontext.

Typische Quellen:

- Anforderungen
- Architektur
- Richtlinien
- Coding Guidelines
- Test Policy
- Unternehmenswissen

### 4. Skills

Skills beschreiben Methoden und Fachwissen.

Beispiele:

- Boundary Value Analysis
- Equivalence Partitioning
- State Transition Testing
- Risk Based Testing
- Clean Code
- SOLID
- REST

### 5. Guardrails

Guardrails begrenzen das Verhalten.

Beispiele:

- Keine Anforderungen erfinden
- Fehlende Informationen kennzeichnen
- Unternehmensrichtlinien einhalten
- Nachvollziehbare Entscheidungen dokumentieren

### 6. Artefakte

Agenten kommunizieren über Artefakte.

Beispiele:

- Product Vision
- User Story
- Test Strategy
- Test Conditions
- Test Cases
- Test Report

### 7. Handovers

Ein Handover beschreibt:

- Eingaben
- Ausgaben
- Qualitätskriterien
- Verantwortlichkeiten

Dadurch entstehen reproduzierbare Prozesse.

### 8. Quality Gates

Zwischen zwei Agenten wird geprüft:

- Vollständigkeit
- Konsistenz
- Regelkonformität
- Nachvollziehbarkeit

Fehler werden möglichst früh erkannt.

## Orchestrierung

Ein Orchestrator steuert den Workflow.

Seine Aufgaben:

- Agenten starten
- Kontext bereitstellen
- Reihenfolge steuern
- Ergebnisse sammeln
- Qualität überwachen
- Human-in-the-Loop einbinden

## Human in the Loop

Nicht jede Entscheidung sollte autonom erfolgen.

Typische Freigaben:

- Anforderungen
- Architektur
- Teststrategie
- Release

## Vorteile

- Spezialisierte Experten statt Universalagent
- Wiederverwendbare Komponenten
- Höhere Qualität
- Bessere Nachvollziehbarkeit
- Skalierbarkeit
- Einfachere Wartung

## Herausforderungen

- Kontextmanagement
- Konsistente Artefakte
- Versionsverwaltung
- Konfliktlösung
- Kosten für LLM-Aufrufe
- Governance

## Best Practices

- Kleine spezialisierte Agenten bevorzugen
- Einheitliche Templates verwenden
- Wissen zentral verwalten
- Standardisierte Übergaben definieren
- Quality Gates einführen
- Menschliche Freigaben an kritischen Stellen einplanen

## Fazit

Ein Agentic Workflow ersetzt keinen klassischen Prozess, sondern unterstützt ihn durch zusammenarbeitende KI-Agenten. Die Qualität entsteht nicht durch ein besonders leistungsfähiges
LLM, sondern durch klar definierte Rollen, standardisierte Übergaben, gemeinsame Wissensquellen
und systematische Qualitätskontrollen.