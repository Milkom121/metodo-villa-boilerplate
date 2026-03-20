# Metodo Villa — Indice Documentazione

Questa cartella contiene la documentazione operativa del Metodo Villa integrata nel progetto.
Per il manuale completo, vedi `C:\Users\Mario\Documents\METODO_VILLA_v1.md`.

## Struttura del Boilerplate

```
[NomeProgetto]/
├── CLAUDE.md                    # Regole operative per Claude (Metodo Villa)
├── PROJECT_CONFIG.md            # Configurazione specifica del progetto
├── ROADMAP.md                   # Piano di sviluppo a blocchi e fasi
├── metodo-villa-runner.sh       # Runner automatico per ciclo semi-autonomo
├── avvia-metodo-villa.bat       # Launcher Windows (Git Bash)
├── avvia-metodo-villa.ps1       # Launcher Windows PowerShell
│
├── .claude/
│   ├── handoff.md               # Handoff sessione corrente (generato da Claude)
│   ├── handoff-template.md      # Template formato handoff
│   ├── decisions.md             # Log decisioni architetturali
│   ├── ideas.md                 # Idee future cross-blocco
│   └── metodo-villa/            # Documentazione dettagliata del metodo
│       ├── README.md            # Questo file
│       ├── 01-filosofia.md
│       ├── 02-workflow-blocchi.md
│       ├── 03-ciclo-continuo.md
│       ├── 04-testing.md
│       ├── 05-qualita-sicurezza.md
│       ├── 06-scorciatoie-sviluppo.md
│       ├── 07-gestione-codice.md
│       ├── 08-gestione-progetto.md
│       └── 09-struttura-file.md
│
├── docs/
│   ├── progress.json            # Stato runner (fase, blocco, status)
│   ├── session-log.md           # Log sessioni runner (generato automaticamente)
│   ├── runner-log.txt           # Log dettagliato runner (generato automaticamente)
│   ├── dev-shortcuts.md         # Scorciatoie di sviluppo attive
│   ├── decisions.md             # Log decisioni (alternativo a .claude/decisions.md)
│   └── ideas.md                 # Idee future
│
├── skills/
│   └── discovery/               # Skill pre-sviluppo: raccolta requisiti
│       ├── SKILL.md             # Workflow completo discovery (9 fasi)
│       └── references/
│           ├── interview-guide.md        # Guida intervista strutturata
│           ├── concept-doc-template.md   # Template concept document Word
│           └── presentation-template.md  # Template presentazione PowerPoint
│
├── src/                         # Codice sorgente
└── tests/                       # Test
```

## File Obbligatori per Ogni Progetto

| File | Scopo | Compilato da |
|------|-------|--------------|
| `CLAUDE.md` | Regole operative + regole specifiche progetto | Villa + Claude |
| `PROJECT_CONFIG.md` | Stack, comandi, deployment | Villa |
| `ROADMAP.md` | Piano fasi e blocchi | Villa + Claude |
| `docs/dev-shortcuts.md` | Scorciatoie attive in sviluppo | Claude |
| `.claude/handoff.md` | Stato fine sessione | Claude |

## File Generati Automaticamente dal Runner

| File | Quando |
|------|--------|
| `docs/progress.json` | Aggiornato ad ogni blocco completato |
| `docs/session-log.md` | Log sintetico per sessione |
| `docs/runner-log.txt` | Log completo con output Claude |
| `.claude/handoff.md` | Fine di ogni blocco |

## Riferimenti

- Manuale completo: `C:\Users\Mario\Documents\METODO_VILLA_v1.md`
- Documentazione dettagliata: `.claude/metodo-villa/`
- Idee cross-progetto: `C:\Users\Mario\Documents\ideas.md`
