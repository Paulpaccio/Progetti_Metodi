# Riepilogo Sprint 2 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il secondo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Repository: [Paulpaccio/Progetti_Metodi — sprint_2](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2)

---
## Struttura della cartella

```
worklog/sprint_2/
├── README.md                  ← questo file
├── Mockup/
│   ├── ilProgetto/
│   ├── Privacy/
│   └── Semantica/
├── Ontologia/
│   ├── README.md
│   ├── RDF_OpereArte_Onto-PM.ttl
│   ├── mapping.yarrrml.yml
│   └── CSVs/
├── Privacy/
│   ├── README.md
│   └── nota-motivazione-base-giuridica.md
└── SPARQL/
    ├── README.md
    └── Immagini/
```
---
## 1. Stato delle User Story (board Trello/Jira)

| US | Titolo | Priorità | Stato |
|---|---|---|---|
| US1.9 | Il progetto dati.cultura.gov.it | Low | Approved |
| US1.3 | Consultare il modello semantico | Low | Approved |
| US1.4 | Accesso ai dati via API/SPARQL con esempi pronti | High | Approved |
| US2.3 | Trasformazione CSV → RDF/Turtle con YARRRML | Highest | Approved |
| US2.5 | Informativa privacy: tracciamento del sito | High | Approved |

---

## 2. Deliverable prodotti

### 2.1 US1.9 — Il progetto dati.cultura.gov.it
Cartella: [`worklog/sprint_2/Mockup/ilProgetto`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/ilProgetto)

Mockup della sezione **Il progetto**, pensata per spiegare in poche righe la nascita e le finalità dell'iniziativa, soprattutto per chi non conosce i Linked Open Data. Tre sottosezioni:

1. **Il progetto**: introduzione per l'utente con rimando alla sezione Dataset.
2. **Cosa sono i LOD**: spiegazione breve e non tecnica con un approfondimento sulla loro funzione.
3. **Domande frequenti**: le domande più poste dagli utenti con link a una sezione di approfondimento dedicata.

### 2.2 US1.3 — Consultare il modello semantico
Cartella: [`worklog/sprint_2/Mockup/Semantica`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/Semantica)

La pagina **Ontologia** espone il modello concettuale definito nella US2.2 (Sprint 1) ed è organizzata in quattro sezioni con un indice:

- **L'ontologia delle opere d'arte**
- **Esplora il modello**: diagramma con le cinque classi principali, spiegate in una legenda
- **A quali domande risponde**: tre competency question scritte come le farebbe davvero un utente
- **Scarica il modello**: TTL, diagramma Graffoo in PNG, PDF delle dieci competency question

> Questa pagina *non produce dati nuovi*: riusa il diagramma e le domande già preparati nella US2.2.
> Copre ciò che era richiesto dal *test di accettazione*: il diagramma con le cinque classi, la legenda, almeno tre domande spiegate, e il mockup della pagina.

### 2.3 US2.3 — Trasformazione CSV → RDF/Turtle con YARRRML
Cartella: [`worklog/sprint_2/Ontologia`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Ontologia)

Pipeline completa di trasformazione dei dati: **CSV → YARRRML → RDF/Turtle → Ontologia OWL**. Sarà la base per le fasi successive di pubblicazione SPARQL e documentazione DCAT-AP-IT.

- **CSV**: oltre al file principale `opere_arte_completo.csv` (UTF-8), sei CSV aggiuntivi divisi per categoria (`paintings`, `institutes`, `places`, `exact_dates`, `year_ranges`, `century_references`), per facilitare il mapping YARRRML e distinguere i valori della classe `TimeReference` e delle sue tre sottoclassi.
- **Mapping YARRRML**: generato con [Matey/RML.io](https://rml.io/yarrrml/matey/#), file `mapping.yarrrml.yml`.
- **RDF/Turtle**: `RDF_OpereArte_Onto-PM.ttl`.
- **Prefissi RDF**: in un file RDF, ogni classe o proprietà è identificata da un indirizzo web completo (es. `http://www.progetto-shell.org/dati-cultura-ontology#Painting`), troppo lungo da scrivere ogni volta. I prefissi sono abbreviazioni dichiarate una volta sola all'inizio del fil, nel nostro ce ne sono cinque: `rdf` e `xsd` (vocabolari standard del web semantico), `sd` (standard per i servizi SPARQL), `dco` (il vocabolario della nostra ontologia, con classi e proprietà definite da noi, come `dco:hasTitle`) e `data` (i dati veri e propri: i singoli dipinti, istituti e luoghi).

### 2.4 US1.4 — Accesso ai dati via API/SPARQL con esempi pronti
Cartella: [`worklog/sprint_2/SPARQL`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/SPARQL)

Abbiamo generato un endpoint SPARQL caricando ontologia e istanze su **GraphDB** (repository `dati-cultura`, 337 statement complessivi), con due query di esempio pronte all'uso:

- **Query 1**: catena dipinto → istituto → luogo (CQ 2, 3, 6, 7): 13 righe verificate, una per dipinto.
- **Query 2**: dipinti datati per intervallo di secoli (CQ 4, 5, 9): 7 righe verificate (5 dipinti del XVII secolo, 2 del XIX), con corretta esclusione delle opere del XX secolo.

Documentati anche due modi per eseguire le query: da browser tramite il Workbench di GraphDB e come chiamata API via URL (con nota sull'URL encoding).

### 2.5 US2.5 — Informativa privacy: tracciamento del sito
Cartelle: [`worklog/sprint_2/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Privacy) e [`worklog/sprint_2/Mockup/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/Privacy)

Tre schermate mostrano la sezione dell'informativa privacy sui dati di navigazione:

1. **Intestazione e dati trattati**: riferimenti normativi e data di aggiornamento, l'elenco di cosa viene raccolto (IP, nomi a dominio, pagine richieste e altri dati tecnici automatici).
2. **Finalità e base giuridica**: perché i dati vengono raccolti (statistiche aggregate sull'uso del sito) e su quale norma si basa il trattamento.
3. **Tempi di conservazione**: massimo 7 giorni e un riquadro che rassicura sull'anonimità delle statistiche pubblicate.

*Deliverable prodotti*: nota di motivazione della base giuridica (`nota-motivazione-base-giuridica.md`, in `Privacy/`) e mockup a tre schermate (in `Mockup/Privacy/`). Il testo integrale della sezione informativa arriverà in uno sprint successivo.

---

## Nota

I dati e l'endpoint prodotti in **US2.3** e **US1.4** sono la base su cui si costruisce lo Sprint 3: le User Story US1.5 (Download dei dati) e US2.6 (Esposizione di API e SPARQL endpoint) riusano lo stesso dataset e la stessa versione dei file RDF/Turtle e CSV.
