# [NomeProgetto]

> [Descrizione breve del progetto — una frase]

## Panoramica

[Descrizione più dettagliata del progetto: cosa fa, per chi, perché esiste.]

## Stack

| Componente | Tecnologia |
|------------|------------|
| [componente] | [tecnologia] |

## Come iniziare

```bash
# Clona il repository
git clone [url-repository]
cd [nome-progetto]

# Configura le variabili d'ambiente
cp .env.example .env
# Modifica .env con i tuoi valori

# Installa le dipendenze
# [comando specifico del progetto]

# Avvia in sviluppo
# [comando specifico del progetto]
```

## Struttura del progetto

```
[NomeProgetto]/
├── CLAUDE.md              # Regole operative per Claude (Metodo Villa)
├── PROJECT_CONFIG.md      # Configurazione specifica del progetto
├── ROADMAP.md             # Piano di sviluppo a blocchi
├── docs/
│   ├── decisions.md       # Log decisioni architetturali
│   ├── ideas.md           # Idee future
│   └── dev-shortcuts.md   # Scorciatoie di sviluppo attive
├── src/                   # Codice sorgente
├── tests/                 # Test
└── .env.example           # Template variabili d'ambiente
```

## Sviluppo

Questo progetto segue il **Metodo Villa** — un sistema di sviluppo a blocchi condotto da Claude.

- Ogni sessione di sviluppo corrisponde a un singolo blocco della ROADMAP
- Le regole operative sono in `CLAUDE.md`
- Il manuale completo del metodo è in `.claude/metodo-villa/`

## Stato

Vedi `PROJECT_CONFIG.md` per lo stato attuale del progetto.

---

*Progetto basato su [metodo-villa-boilerplate](https://github.com/[owner]/metodo-villa-boilerplate)*
