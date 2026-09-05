# Riepilogo Sprint 1 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il primo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Repository: [Paulpaccio/Progetti_Metodi — sprint_1](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1)

---

## Struttura della cartella

```
sprint_1/
├── README.md                              ← questo file
├── CSV/
│   ├── README.md
│   ├── opere_arte_completo.csv
│   ├── paintings.csv
│   ├── institutes.csv
│   ├── places.csv
│   ├── exact_dates.csv
│   ├── year_ranges.csv
│   └── century_references.csv
├── Mockup/
│   ├── HomePage/
│   │   ├── README.md
│   │   └── Immagini/
│   ├── Footer/
│       ├── README.md
│       └── Immagini/
└── Ontologia/
    ├── README.md
    ├── CQ_Onto-PM.txt
    ├── RDF_Ontologia-PM.ttl
    └── Diagrammi/
        ├── DiagrammaER_Onto-PM.drawio.png
        ├── DiagrammaER_Onto-PM.drawio.xml
        └── Graffoo_Onto-PM.drawio.png
```

---

## 1. Stato delle User Story (board Trello/Jira)

| US | Titolo | Priorità | Stato |
|---|---|---|---|
| US1.1 | Home page chiara | Medium | Approvato |
| US1.8 | Informazioni utili e immediate (footer) | Low | Approvato |
| US2.1 | Produzione dati in CSV | High | Approvato |
| US2.2 | Creazione dell'ontologia delle opere d'arte | Highest | Approvato |

---

## 2. Deliverable prodotti

### 2.1 US1.1 — Home page chiara
Cartella: [`sprint_1/Mockup/HomePage`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/Mockup/HomePage)

Mockup della home page: titolo, breve descrizione introduttiva, due pulsanti principali (**Catalogo e ricerca tra dataset**, **Accesso ai dati - API e SPARQL**), due numeri riassuntivi (dataset pubblicati, entità collegate). Il menu in testata resta sempre visibile e raggiunge tutte le sezioni del sito; la voce **Accesso ai dati** si apre in una tendina con due opzioni (API e SPARQL, Scarica Dati).

### 2.2 US1.8 — Informazioni utili e immediate (footer)
Cartella: [`sprint_1/Mockup/Footer`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/Mockup/Footer)

Mockup del footer diviso in tre blocchi: contatti istituzionali, link utili (amministrazione trasparente, privacy, note legali, accessibilità), collegamenti social.

### 2.3 US2.1 — Produzione dati in CSV
Cartella: [`sprint_1/CSV`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/CSV)

**File principale `opere_arte_completo.csv` con le 13 opere della tabella di consegna, più sei CSV divisi per categoria (usati poi per il mapping YARRRML della US2.3, Sprint 2). Verificato contro il test di accettazione: righe totali e quoting RFC 4180 corretti; **due scostamenti documentati**: 14 colonne invece di 8 (per la scomposizione del riferimento temporale in più campi) e presenza del BOM UTF-8 in tutti i file.** (DA RIVEDERE)

### 2.4 US2.2 — Creazione dell'ontologia delle opere d'arte
Cartella: [`sprint_1/Ontologia`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/Ontologia)

Modello concettuale e ontologia OWL per il dataset delle opere d'arte: quattro classi principali (`Artwork`, `Painting`, `CulturalInstituteOrSite`, `Place`, `TimeReference` con le sue tre sottoclassi disgiunte), documentate in un diagramma E-R semplificato e in un diagramma Graffoo completo. Dieci competency question verificate con il reasoner HermiT in Protégé.

---
