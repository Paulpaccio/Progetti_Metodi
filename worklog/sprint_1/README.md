# Riepilogo Sprint 1 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il primo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Repository: [Paulpaccio/Progetti_Metodi — sprint_1](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1)

---

## Struttura della cartella

```
sprint_1/
├── README.md                                      ← questo file
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
│   │       ├── 01-home.png                       
│   │       └── 02-menu-dropdown.png               
│   └── Footer/
│       ├── README.md
│       └── Immagini/
│           └── PM-Footer.png                       
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

| US | Titolo | Ticket | Priorità | Stima (SP) | Stato |
|---|---|---|---|---|---|
| US1.1 | Home page chiara | PM-10 | Medium | *N/D* | Approvato |
| US1.8 | Informazioni utili e immediate (footer) | PM-30 | Low | *N/D* | Approvato |
| US2.1 | Produzione dati in CSV | PM-9 | High | *N/D* | Approvato |
| US2.2 | Creazione dell'ontologia delle opere d'arte | PM-16 | Highest | *N/D* | Approvato |

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

File principale `opere_arte_completo.csv` con le 13 opere della tabella di consegna, più sei CSV divisi per categoria (usati poi per il mapping YARRRML della US2.3, Sprint 2).

### 2.4 US2.2 — Creazione dell'ontologia delle opere d'arte
Cartella: [`sprint_1/Ontologia`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/Ontologia)

Modello concettuale e ontologia OWL per il dataset delle opere d'arte: quattro classi principali (`Artwork`, `Painting`, `CulturalInstituteOrSite`, `Place`, `TimeReference` con le sue tre sottoclassi disgiunte), documentate in un diagramma E-R semplificato e in un diagramma Graffoo completo. Dieci competency question verificate con il reasoner HermiT in Protégé.

---
## 3. Copertura dei test di accettazione

| US | Requisito | Dove è soddisfatto |
|---|---|---|
| US1.1 | La home mostra le sezioni principali (catalogo, semantica, API/SPARQL, contatti) | Menu di navigazione sempre visibile |
| US1.1 | Testo introduttivo di poche righe | Titolo e breve descrizione |
| US1.8 | Il footer contiene la sezione contatti | Blocco "Contatti istituzionali" |
| US1.8 | Il footer contiene link utili e social | Blocchi "Link utili" e "Seguici su" |
| US2.1 | Il CSV contiene le 13 righe con 14 righe totali | Verificato, riscontro positivo |
| US2.1 | 8 campi per riga |  il file ha 14 colonne |
| US2.1 | UTF-8 senza BOM |il file è UTF-8 |
| US2.1 | Quoting RFC 4180 | Verificato, riscontro positivo |
| US2.2 | Risponde ad almeno 5 competency question (minimo 3) | 10 CQ documentate |
| US2.2 | È disegnata in Graffoo | `Diagrammi/Graffoo_Onto-PM.drawio.png` |

---
