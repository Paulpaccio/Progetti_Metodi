# Riepilogo Sprint 2 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il secondo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Repository: [Paulpaccio/Progetti_Metodi — sprint_2](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2)

---

## Struttura della cartella

```
worklog/sprint_2/
├── README.md                    ← questo file
├── retrospettiva.md
├── Mockup/
│   ├── ilProgetto/
|   |    ├── README.md
|   |    └── Immagini/
|   |        ├── ilProgetto_head.png        
|   |        └── ilProgetto_LOD.png        
│   ├── DomandeFrequenti/
|   |    ├── README.md                 
|   |    └── Immagini/
|   |         ├── ilProgetto_QnA.png    
|   |         └── ilProgetto_QnAext.png  
│   ├── Privacy/
|   |    ├── README.md                                   
|   |    └── Immagini/
|   |         ├── 05-privacy-dati-navigazione.png        
|   |         ├── 05.1-privacy-dati-navigazione.png       
|   |         └── 05.2-privacy-dati-navigazione.png       
│   └── Semantica/
|       ├── README.md                                 
|       └── Immagini/
|            ├── 06-ontologia-intro.png                
|            ├── 07-ontologia-esplora.png                
|            ├── 07.1-ontologia-esplora-legenda.png     
|            ├── 08-ontologia-domande.png               
|            ├── 08.1-ontologia-domande.png               
|            └── 09-ontologia-scarica.png                
├── Ontologia/
│   ├── README.md
│   ├── RDF_OpereArte_Onto-PM.ttl
│   └── mapping.yarrrml.yml
├── Privacy/
│   ├── README.md
│   └── nota-motivazione-base-giuridica.md
└── SPARQL/
    ├── README.md                         
    └── Immagini/
        ├── query1-.png                   
        ├── query1-risultati.png          
        ├── query2-.png                  
        ├── query2-risultati.png          
        └── esempio-risposta-api.srx       
```

---

## 1. Stato delle User Story (board Trello/Jira)

| US | Titolo | Ticket | Priorità | Stima (SP) | Stato |
|---|---|---|---|---|---|
| US1.9 | Il progetto dati.cultura.gov.it | PM-37 | Low | N/A | Approvato |
| US1.10 | Sezione FAQ (domande frequenti) | PM-38 | Lowest | N/A | Approvato |
| US1.3 | Consultare il modello semantico | PM-18 | Low | 4.0 | Approvato |
| US2.3 | Trasformazione CSV → RDF/Turtle con YARRRML | PM-20 | Highest | 10.0 | Approvato |
| US1.4 | Accesso ai dati via API/SPARQL con esempi pronti | PM-21 | High | 4.0 | Approvato |
| US2.5 | Informativa privacy: tracciamento del sito | PM-28 | High | 6.0 | Approvato |

**Totale story point dello sprint: 24.0**
---

## 2. Deliverable prodotti

### 2.1 US1.9 — Il progetto dati.cultura.gov.it
Cartella: [`worklog/sprint_2/Mockup/ilProgetto`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/ilProgetto)

Mockup della sezione **Il progetto**, pensata per spiegare in poche righe la nascita e le finalità dell'iniziativa, soprattutto per chi non conosce i Linked Open Data. Due sottosezioni:

1. **Il progetto**: introduzione per l'utente con rimando alla sezione Dataset.
2. **Cosa sono i LOD**: spiegazione breve e non tecnica con un approfondimento sulla loro funzione.

### 2.2 US1.10 — Sezione FAQ (domande frequenti)
Cartella: [`worklog/sprint_2/Mockup/DomandeFrequenti`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/DomandeFrequenti)

Mockup della sezione FAQ, raggiungibile dallo stesso indice laterale della pagina "Il progetto". Tre domande in blocchi a scomparsa. **Il contenuto non è ancora quello reale**, domande e risposte non sono ancora state scritte.

### 2.3 US1.3 — Consultare il modello semantico
Cartella: [`worklog/sprint_2/Mockup/Semantica`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/Semantica)

La pagina **Ontologia** espone il modello concettuale definito nella US2.2 (Sprint 1) ed è organizzata in quattro sezioni con un indice:

- **L'ontologia delle opere d'arte**
- **Esplora il modello**: diagramma con le cinque classi principali, spiegate in una legenda
- **A quali domande risponde**: tre competency question scritte come le farebbe davvero un utente
- **Scarica il modello**: TTL, diagramma Graffoo in PNG, PDF delle dieci competency question

> Questa pagina *non produce dati nuovi*: riusa il diagramma e le domande già preparati nella US2.2.
> Copre ciò che era richiesto dal *test di accettazione*: il diagramma con le cinque classi, la legenda, almeno tre domande spiegate, e il mockup della pagina.

### 2.4 US2.3 — Trasformazione CSV → RDF/Turtle con YARRRML
Cartella: [`worklog/sprint_2/Ontologia`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Ontologia)

Mapping YARRRML e grafo RDF/Turtle, a partire dai CSV prodotti in **US2.1** (Sprint 1). 

- **Mapping YARRRML**: generato con [Matey/RML.io](https://rml.io/yarrrml/matey/#), file `mapping.yarrrml.yml`.
- **RDF/Turtle**: `RDF_OpereArte_Onto-PM.ttl`.

Dettagli su prefissi RDF e mapping nel [README della cartella](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Ontologia).

### 2.5 US1.4 — Accesso ai dati via API/SPARQL con esempi pronti
Cartella: [`worklog/sprint_2/SPARQL`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/SPARQL)

Abbiamo generato un endpoint SPARQL caricando ontologia e istanze su **GraphDB** (repository `dati-cultura`, 337 statement complessivi), con due query di esempio pronte all'uso:

- **Query 1**: catena dipinto → istituto → luogo (CQ 2, 3, 6, 7), 13 righe verificate, una per dipinto.
- **Query 2**: dipinti datati per intervallo di secoli (CQ 4, 5, 9), 7 righe verificate (5 dipinti del XVII secolo, 2 del XIX), con corretta esclusione delle opere del XX secolo.

Documentati anche due modi per eseguire le query: da browser tramite il Workbench di GraphDB e come chiamata API via URL (con nota sull'URL encoding).

### 2.6 US2.5 — Informativa privacy: tracciamento del sito
Cartelle: [`worklog/sprint_2/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Privacy) e [`worklog/sprint_2/Mockup/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_2/Mockup/Privacy)

Tre schermate mostrano la sezione dell'informativa privacy sui dati di navigazione:

1. **Intestazione e dati trattati**: riferimenti normativi e data di aggiornamento, l'elenco di cosa viene raccolto (IP, nomi a dominio, pagine richieste e altri dati tecnici automatici).
2. **Finalità e base giuridica**: perché i dati vengono raccolti (statistiche aggregate sull'uso del sito) e su quale norma si basa il trattamento.
3. **Tempi di conservazione**: massimo 7 giorni e un riquadro che rassicura sull'anonimità delle statistiche pubblicate.

Deliverable prodotti: nota di motivazione della base giuridica (`nota-motivazione-base-giuridica.md`, in `Privacy/`) e mockup a tre schermate (in `Mockup/Privacy/`).

---

## 3. Copertura dei test di accettazione

| US | Requisito | Dove è soddisfatto |
|---|---|---|
| US1.9 | La pagina spiega l'iniziativa del catalogo | Sezione "Il progetto" del mockup |
| US1.9 | Rimando alla sezione Dataset | Presente nel mockup |
| US1.10 | Sezione FAQ con domande a scomparsa | Mockup con tre domande in blocchi a scomparsa |
| US1.3 | Diagramma con cinque classi | Sezione "Esplora il modello" |
| US1.3 | Legenda delle classi | Presente nel mockup |
| US1.3 | Almeno tre competency question | Sezione "A quali domande risponde" |
| US1.3 | Link per scaricare il modello TTL | Sezione "Scarica il modello" |
| US2.3 | Mapping YARRRML | `mapping.yarrrml.yml` |
| US2.3 | File RDF/Turtle | `RDF_OpereArte_Onto-PM.ttl` |
| US1.4 | Endpoint SPARQL attivo | Repository GraphDB `dati-cultura` |
| US1.4 | Due query di esempio pronte | Sezione 2.5, Query 1 e 2 |
| US2.5 | Informativa privacy per il tracciamento del sito | Mockup a tre schermate |
| US2.5 | Base giuridica motivata | `nota-motivazione-base-giuridica.md` |

---
## Nota

I dati e l'endpoint prodotti in **US2.3** e **US1.4** sono la base su cui si costruisce lo Sprint 3. Le User Story US1.5 (Download dei dati) e US2.6 (Esposizione di API e SPARQL endpoint) riusano lo stesso dataset e la stessa versione dei file RDF/Turtle e CSV.
