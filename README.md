# Metodo Villa — Boilerplate

> Punto di partenza per ogni nuovo progetto condotto con il Metodo Villa.

## Cos'è il Metodo Villa

Il Metodo Villa è un sistema di sviluppo software semi-automatizzato condotto da Claude (Anthropic). Il lavoro è organizzato in **blocchi atomici**: ogni sessione produce un risultato concreto, testato, committato. Un runner automatico può eseguire blocchi in sequenza senza intervento umano continuo, fermandosi solo per checkpoint, errori o decisioni architetturali.

Principi chiave:
- **Funziona > Elegante** — priorità al codice che gira e ai test verdi
- **Un blocco per sessione** — nessuna divagazione, nessun refactoring non richiesto
- **Handoff obbligatorio** — ogni sessione termina con `.claude/handoff.md` che descrive stato e prossimo passo
- **Commit in italiano** — descrittivi, atomici, senza Conventional Commits

## Come Usare il Boilerplate

### 1. Clona e configura

```bash
# Clona il boilerplate
git clone https://github.com/Milkom121/metodo-villa-boilerplate.git nome-progetto
cd nome-progetto

# Rimuovi il remote del boilerplate e aggiungi il tuo
git remote remove origin
git remote add origin https://github.com/[utente]/[nome-progetto].git
```

### 2. Compila i file di configurazione

- **`PROJECT_CONFIG.md`** — stack tecnologico, comandi essenziali, deployment
- **`ROADMAP.md`** — fasi e blocchi del progetto (se non usi la skill discovery)
- **`CLAUDE.md`** — aggiungi le regole specifiche del progetto nella sezione dedicata

### 3. (Opzionale) Skill Discovery — Fase pre-sviluppo

Se il progetto è nuovo e i requisiti non sono ancora definiti, usa la **skill discovery** prima di iniziare a sviluppare. Lancia Claude Code e descrivi il progetto — la skill guida l'intero processo da brief a ROADMAP pronta.

La skill si trova in `skills/discovery/SKILL.md` ed è attivata automaticamente da Claude Code quando menzioni: nuovo progetto, raccolta requisiti, concept, discovery, analisi cliente, ecc.

### 4. Avvia il runner

**Windows (doppio click):**
```
avvia-metodo-villa.bat
avvia-metodo-villa.ps1
```

**Linux/Mac/Git Bash:**
```bash
chmod +x metodo-villa-runner.sh
./metodo-villa-runner.sh --max-blocks 10 --timeout 30
```

**Opzioni runner:**
```
--max-blocks N    Numero massimo blocchi per sessione (default: 10)
--timeout N       Timeout minuti per blocco (default: 30)
--phase N         Forza la fase di partenza
--dry-run         Simula senza eseguire Claude
--verbose         Output dettagliato
--resume          Riprendi dall'ultimo handoff
```

## Struttura File

```
[NomeProgetto]/
├── CLAUDE.md                    # Regole operative (Metodo Villa + specifiche progetto)
├── PROJECT_CONFIG.md            # Configurazione progetto
├── ROADMAP.md                   # Piano sviluppo a blocchi
├── metodo-villa-runner.sh       # Runner automatico
├── avvia-metodo-villa.bat       # Launcher Windows
├── avvia-metodo-villa.ps1       # Launcher PowerShell
│
├── .claude/
│   ├── handoff.md               # Stato sessione corrente
│   ├── handoff-template.md      # Formato handoff
│   ├── decisions.md             # Decisioni architetturali
│   └── metodo-villa/            # Documentazione dettagliata metodo
│
├── docs/
│   ├── progress.json            # Stato runner (fase, blocco, status)
│   ├── dev-shortcuts.md         # Scorciatoie sviluppo attive
│   └── metodo-villa/README.md   # Indice struttura boilerplate
│
├── skills/
│   └── discovery/               # Skill pre-sviluppo
│       ├── SKILL.md
│       └── references/
│
├── src/                         # Codice sorgente
└── tests/                       # Test
```

## Skill Discovery

La skill discovery gestisce la fase **pre-sviluppo** in 9 fasi:

1. **Input** — lettura documenti cliente
2. **Analisi** — identificazione gap e requisiti mancanti
3. **Intervista** — domande strutturate una alla volta
4. **Concept Document** — Word `.docx` per il cliente
5. **Presentazione** — PowerPoint `.pptx` di sintesi
6. **Feedback** — raccolta revisioni cliente
7. **Impatti a cascata** — analisi delle modifiche strutturali
8. **Aggiornamento** — revisione documenti
9. **Output sviluppo** — `PROJECT_CONFIG.md`, `ROADMAP.md`, `CLAUDE.md`, schema DB

Documentazione: `skills/discovery/SKILL.md`

## Runner Automatico

Il runner esegue blocchi di sviluppo in sequenza, leggendo lo stato da `docs/progress.json` e il handoff da `.claude/handoff.md`. Si ferma automaticamente a:

- `CHECKPOINT` — richiede decisione umana
- `PHASE_COMPLETE` — fase completata, pronta per review
- `ERROR` — errore nel blocco
- `BLOCKED` — mancano informazioni per procedere

Log in `docs/session-log.md` e `docs/runner-log.txt`.

---

*Metodo Villa — [github.com/Milkom121/metodo-villa-boilerplate](https://github.com/Milkom121/metodo-villa-boilerplate)*
