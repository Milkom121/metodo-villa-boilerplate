# Struttura File Standard di Ogni Progetto

## Struttura obbligatoria per ogni progetto Villa

```
progetto/
├── CLAUDE.md              # Bussola — stato, convenzioni, regole (OBBLIGATORIO)
├── PROJECT_CONFIG.md      # Configurazione specifica del progetto (nome, stack, dominio)
├── ROADMAP.md             # Piano a blocchi con checkbox (OBBLIGATORIO)
├── docs/
│   ├── decisions.md       # Log decisioni architetturali (generato da Claude)
│   ├── ideas.md           # Idee future emerse durante le sessioni
│   └── dev-shortcuts.md   # Registro scorciatoie di sviluppo (OBBLIGATORIO)
├── .claude/
│   ├── handoff.md         # Contesto per la prossima sessione (generato da Claude)
│   └── metodo-villa/      # Manuale completo del Metodo Villa
└── ...
```

## Struttura centralizzata a livello utente

A livello di home utente, Villa mantiene file centralizzati:

```
C:\Users\Mario\Documents\
├── ideas.md               # Idee cross-progetto (intuizioni che toccano più progetti o il metodo stesso)
└── METODO_VILLA_v1.md     # Versione definitiva del Metodo Villa

C:\Users\Mario\.claude\
└── CLAUDE.md              # Metodo Villa globale (letto automaticamente da Claude Code)
```

## Come attivare il sistema

Claude Code supporta un CLAUDE.md globale nella home dell'utente (`~/.claude/CLAUDE.md`) che viene letto automaticamente per ogni sessione. Il Metodo Villa va messo lì:

```
C:\Users\Mario\.claude\CLAUDE.md    # Metodo Villa (strato universale)
```

Ogni progetto ha poi il suo CLAUDE.md locale che:
1. NON ripete le regole universali (sono già nel globale)
2. Aggiunge le regole specifiche del progetto
3. Sovrascrive regole universali solo se necessario (con commento che spiega perché)

## Esempio di CLAUDE.md locale (dopo l'adozione del Metodo Villa)

```markdown
# NomeProgetto — CLAUDE.md

## Progetto
Descrizione breve del progetto.

## Stato
- **Progetto**: attivo
- **Data ultimo aggiornamento**: YYYY-MM-DD
- **Data ultima sessione**: YYYY-MM-DD

## Regole specifiche (oltre al Metodo Villa)
- [regola specifica del progetto]

## Stack (HARD CONSTRAINT)
| Componente | Scelta |
|---|---|
| [componente] | [tecnologia] |
```

Questo riduce drasticamente la dimensione dei CLAUDE.md individuali e garantisce coerenza tra progetti. Le regole su commit, branching, lingua, ciclo continuo, testing — sono tutte nel globale.

## Descrizione di ogni file obbligatorio

### CLAUDE.md

La bussola del progetto. Contiene:
- Descrizione del progetto e obiettivi
- Stato attuale (attivo/in pausa/archiviato)
- Stack tecnologico come vincoli hard
- Regole specifiche del progetto che estendono o sovrascrivono il Metodo Villa globale
- Link al roadmap

### ROADMAP.md

Piano a blocchi con checkbox. Ogni blocco ha:
- Titolo descrittivo
- Descrizione concreta di cosa deve essere fatto
- Gate di uscita (criteri verificabili per considerare il blocco completato)
- Checkbox di completamento

Esempio:
```markdown
## B1: Autenticazione JWT
- [ ] Implementare JWT token generation e validation
- [ ] Middleware di autenticazione su tutte le route protette
- [ ] Refresh token logic
- **Gate di uscita**: Tutti i test passano, 3 endpoint protetti testati manualmente
```

### docs/dev-shortcuts.md

Registro obbligatorio di tutte le scorciatoie di sviluppo prese durante il blocco. Deve rimanere aggiornato durante lo sviluppo, non alla fine della sessione.

### .claude/handoff.md

Generato da Claude a fine sessione. Contiene:
- Blocco appena completato
- File modificati/creati nella sessione
- Risultati dei test
- Problemi aperti (se any)
- Decisioni prese
- Prossimo passo esatto — il prompt di handoff che Villa deve incollare

### docs/decisions.md

Log strutturato di tutte le decisioni architetturali prese durante il progetto. Formato a 4 colonne (Data, Decisione, Motivazione, Alternative scartate). Generato da Claude, sempre in crescita.

### docs/ideas.md

File libero dove Claude raccoglie idee interessanti che emergono durante il lavoro ma che non fanno parte del blocco corrente. Inclusa data e contesto.
