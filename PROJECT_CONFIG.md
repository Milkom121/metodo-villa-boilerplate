# Configurazione Progetto

> Compila questo file all'inizio del progetto. È il primo file che Claude legge dopo CLAUDE.md.

## Identità

- **Nome progetto**: [NomeProgetto]
- **Descrizione breve**: [Una frase che descrive cosa fa il progetto]
- **Dominio**: [web app | healthcare | game | tool | api | mobile | altro]
- **Stato**: [attivo | in pausa | archiviato]

## Date

- **Data creazione**: YYYY-MM-DD
- **Data ultimo aggiornamento**: YYYY-MM-DD
- **Data ultima sessione**: YYYY-MM-DD

## Stack Tecnologico (HARD CONSTRAINT)

> Queste scelte non cambiano senza decisione esplicita di Villa.

| Componente | Tecnologia scelta | Note |
|------------|-------------------|------|
| Linguaggio | [es. Python 3.11] | |
| Framework | [es. FastAPI] | |
| Database | [es. PostgreSQL 15] | |
| Frontend | [es. React 18] | |
| Deploy | [es. Docker + DigitalOcean] | |

## Regole Specifiche del Progetto

> Regole che si aggiungono o sovrascrivono il Metodo Villa globale per questo progetto specifico.

- [regola specifica 1]
- [regola specifica 2]

## Comandi Essenziali

```bash
# Installazione dipendenze
# [comando]

# Avvio in sviluppo
# [comando]

# Esecuzione test (L1)
# [comando]

# Build produzione
# [comando]
```

## Deployment

- **Ambiente**: [sviluppo | staging | produzione]
- **Hosting**: [servizio]
- **URL produzione**: [url]

## Link Utili

- Roadmap: ROADMAP.md
- Log decisioni: docs/decisions.md
- Scorciatoie attive: docs/dev-shortcuts.md
- Handoff ultima sessione: .claude/handoff.md
