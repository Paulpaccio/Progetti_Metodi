# Riepilogo Sprint 3 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il terzo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Periodo: 28 agosto – 1 settembre.

Repository: [Paulpaccio/Progetti_Metodi — sprint_3](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_3)

---

## Struttura della cartella

```
worklog/sprint_3/
├── README.md ← questo file
├── retrospettiva.md 
├── Metadati/
│ ├── README.md
│ └── metadati_dcat-ap_it.ttl 
├── Mockup/
│   ├── API_SPARQL/
│   │   ├── README.md
│   │   └── Immagini/
│   |       ├── API_SPARQL_.png 
│   |       ├── API_SPARQL_Query_1.png
│   |       ├── API_SPARQL_Query_2.png 
│   |       └── API_SPARQL_Metodi.png 
│   ├── Privacy/
│   │    ├── README.md
│   │    └── Immagini/
│   │        └── 06-privacy-destinatari-dati.png 
│   └── Scarica_dati/
│        ├── README.md
│        └── Immagini/
│             ├── Scarica_dati_.png 
│             ├── Scarica_dati_CSV_1.png
│             ├── Scarica_dati_CSV_2.png 
│             ├── Scarica_dati_RDF_1.png 
│             └── Scarica_dati_RDF_2.png 
└── Privacy/
    ├── README.md
    └── sezione-destinatari-dati.md
```

---

## 1. Stato delle User Story (board Trello/Jira)

| US | Titolo | Ticket | Priorità | Stima (SP) | Stato |
|---|---|---|---|---|---|
| US1.5 | Download dei dati | PM-23 | High | 6.0 | Approvato |
| US2.4 | Metadatazione DCAT-AP_IT | PM-25 | Highest | 7.0 | Approvato |
| US2.6 | Esposizione di API e SPARQL endpoint | PM-31 | Medium | 6.0 | Approvato |
| US3.3 | Destinatari e accesso ai messaggi | PM-17 | Medium | 4.0 | Approvato |

**Totale story point dello sprint: 23.0**

---

## 2. Deliverable prodotti

### 2.1 US1.5 — Download dei dati
Cartella: [`worklog/sprint_3/Mockup/Scarica_dati`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_3/Mockup/Scarica_dati)

Mockup della sezione **Scarica i dati**, raggiungibile dal menu a tendina *Accesso ai dati*, in cinque schermate:

1. **Stato del dataset**: tre indicatori di dimensione (13 opere, 11 istituti, 10 comuni) e la "carta d'identità" del dataset con nome, versione, data di pubblicazione, ontologia di riferimento e licenza.
2. **Riquadro CSV**: descrizione di `opere_arte_completo.csv` (una riga per opera, dimensione 3,8 KB, 13 record), pensato per fogli di calcolo e strumenti statistici, prima e dopo il download.
3. **Riquadro RDF/Turtle**: descrizione di `RDF_OpereArte_Onto-PM.ttl`, le stesse opere come grafo di entità collegate, con rimando alla pagina *API e SPARQL* per chi preferisce interrogare i dati senza scaricarli.

L'etichetta di versione (`v1.0.0 · 28/08/2026`) compare identica nel riquadro di stato del dataset e su entrambi i riquadri di download: è questo che garantisce che CSV e RDF, anche scaricati in momenti diversi, si riferiscano sempre alla stessa versione dei dati.

> Questa pagina *non produce dati nuovi*: riusa il CSV prodotto in **US2.1** (Sprint 1) e il file RDF/Turtle prodotto in **US2.3** (Sprint 2).

### 2.2 US2.4 — Metadatazione DCAT-AP_IT
Cartella: [`worklog/sprint_3/Metadati`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_3/Metadati)

Metadati del dataset delle opere d'arte secondo il profilo nazionale **DCAT-AP_IT** (file `metadati_dcat-ap_it.ttl`), adottato da AgID come specializzazione italiana di DCAT-AP europeo. Fonte di riferimento: la [Guida Pratica DCAT-AP_IT](https://github.com/giorgialodi/Guida-pratica-DCAT-AP_IT).

Il file distingue i due livelli richiesti dal profilo: i CSV e il TTL degli sprint precedenti contengono i **dati**, questo file descrive il **dataset in quanto tale** — chi lo pubblica, con quale licenza, in quali formati è disponibile, quando è stato aggiornato. Sono modellate sei classi (`Catalog`, `Dataset`, due `Distribution`, `Agent`, `Organization`, `LicenseDocument`), con identificativo secondo la convenzione `codiceIPA:codiceDataset` (`m_bac:D.1`).

Dove esiste un vocabolario controllato è stato impiegato il suo URI e non testo libero: tema `EDUC` (data-theme UE), licenza `A21_CCBY40` (vocabolario delle licenze italiane), formati `CSV` e `RDF_TURTLE` (file-type UE), lingua e paese `ITA`, titolare ed editore `m_bac` (codice IPA).

Il README della cartella contiene anche la **nota di trasparenza sull'uso dell'IA**, con le quattro difformità individuate in fase di verifica e corrette (URI della licenza, indirizzi delle distribuzioni, incoerenza fra formato dichiarato e `downloadURL`, annotazioni provvisorie residue).

### 2.3 US2.6 — Esposizione di API e SPARQL endpoint
Cartella: [`worklog/sprint_3/Mockup/API_SPARQL`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_3/Mockup/API_SPARQL)

Mockup della pagina **API e SPARQL** in quattro schermate:

1. **Vista d'insieme**: riquadro divulgativo "Come funziona?" su endpoint e query, seguito dalla scheda tecnica dell'endpoint — versione (v1.0.0), indirizzo (`http://localhost:7200/repositories/dati-cultura`) e contenuto (337 triple).
2. **Prima query pronta all'uso**: titolo, istituto e luogo di ogni opera, con pulsante "Copia query".
3. **Seconda query di esempio**: opere datate per secolo in un intervallo scelto, in un blocco a scomparsa.
4. **Metodi di esecuzione**: da browser con l'editor grafico (Metodo 1) oppure con la query già scritta dentro l'indirizzo, utile per un programma (Metodo 2), con esempio di chiamata API e pulsante "Copia indirizzo".

La documentazione tecnica dell'endpoint è quella già prodotta in **US1.4** (Sprint 2); questa user story aggiunge la pagina pubblica e il rimando alla sezione *Scarica Dati*, allineata alla stessa versione del dataset (v1.0.0).

### 2.4 US3.3 — Destinatari e accesso ai messaggi
Cartelle: [`worklog/sprint_3/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_3/Privacy) e [`worklog/sprint_3/Mockup/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_3/Mockup/Privacy)

Sezione **"Destinatari dei dati"** dell'informativa privacy, in continuità con la pagina già presentata per la US2.5 (Sprint 2). È articolata in due blocchi:

- **Comunicazione a terzi**: i dati conferiti tramite la pagina dei contatti non sono diffusi né comunicati a soggetti terzi, salvo obblighi di legge o richieste dell'autorità giudiziaria o di altre autorità competenti.
- **Accesso interno ai messaggi**: in applicazione del principio di minimizzazione (art. 5, par. 1, lett. c GDPR), l'accesso è limitato al personale autorizzato e istruito ai sensi degli artt. 29 GDPR e 2-*quaterdecies* del d.lgs. 196/2003, e circoscritto a tre soli ruoli — funzionario addetto alla gestione dei contatti (unico ruolo che accede al contenuto nel merito), personale tecnico/amministratore di sistema (sola manutenzione e sicurezza), Responsabile della protezione dei dati (accesso eventuale, per verifiche di conformità e istanze degli interessati).

La dashboard interna di gestione dei messaggi è dichiarata accessibile unicamente al personale autorizzato, con credenziali individuali e profili di accesso coerenti con il ruolo.

Deliverable prodotti: testo della sezione (`sezione-destinatari-dati.md`, in `Privacy/`) e mockup a una schermata (`06-privacy-destinatari-dati.png`, in `Mockup/Privacy/`).

---

## 3. Copertura dei test di accettazione

| US | Requisito | Dove è soddisfatto |
|---|---|---|
| US1.5 | L'area download offre entrambi i formati (CSV e RDF/Turtle) | `Mockup/Scarica_dati`, riquadro CSV e riquadro RDF/Turtle |
| US1.5 | Collegati alla stessa versione del dataset | Etichetta `v1.0.0 · 28/08/2026` identica su stato del dataset e su entrambi i riquadri |
| US2.4 | Tema Education con URI dal vocabolario controllato | `dcat:theme <…/data-theme/EDUC>` sul Dataset |
| US2.4 | Licenza aperta con URI dal vocabolario delle licenze italiane | `dct:license <…/licences/A21_CCBY40>` su entrambe le Distribution |
| US2.4 | Due distribuzioni con formati CSV e RDF_TURTLE | `dcatapit:Distribution` per CSV e per RDF/Turtle, `dct:format` dal vocabolario UE |
| US2.4 | Titolare ed editore Ministero della Cultura (IPA `m_bac`) | `dct:rightsHolder` e `dct:publisher` verso l'Agent con `dct:identifier "m_bac"` |
| US2.4 | `dct:modified` presente | `dct:modified "2026-08-25"^^xsd:date` su Catalog e Dataset |
| US2.6 | Esempio di chiamata API | Metodo 2, quarta schermata |
| US2.6 | Query SPARQL eseguibile | Seconda e terza schermata, entrambe verificate |
| US2.6 | Link al dump completo in RDF/Turtle | Rimando alla pagina *Scarica Dati*, quarta schermata |
| US3.3 | L'elenco dei ruoli con accesso è dichiarato nell'informativa | Blocco "Accesso interno ai messaggi", tre ruoli elencati |
| US3.3 | La dashboard interna è accessibile solo al personale autorizzato | Ultimo paragrafo della sezione |

---

## Nota

Con la metadatazione di **US2.4** si chiude il flusso CSV → ontologia → RDF/Turtle → metadatazione richiesto dalla consegna del progetto: i dati prodotti in **US2.1** (Sprint 1) e trasformati in **US2.3** (Sprint 2) sono ora descritti, scaricabili e interrogabili.

Le due modalità di accesso realizzate in questo sprint sono complementari e allineate alla stessa versione del dataset (v1.0.0): **US1.5** per chi vuole lavorare offline sui file, **US2.6** per chi preferisce interrogare l'endpoint. I metadati prodotti in **US2.4** sono la base della scheda dataset consultabile realizzata in **US1.6** (Sprint 4), che li espone in forma leggibile senza introdurre informazioni nuove.

Sul fronte privacy, **US3.3** aggiunge all'informativa la sezione sui destinatari; le sezioni su tempi di conservazione, base giuridica e diritti dell'interessato relative ai messaggi sono completate nello Sprint 4 (US3.1, US3.2, US3.4).
