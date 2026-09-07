# Progetto rifacimento del sito `dati.cultura.gov.it`
Rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato per il corso *Metodi informatici per la trasformazione digitale* — a.a. 2025/2026.

Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

---

## Di cosa si tratta

L'obiettivo del progetto non è la riprogettazione grafica di un portale, ma il **cambio di paradigma nella pubblicazione dei dati**: il passaggio da una pubblicazione documentale — file scaricabili e isolati — a una pubblicazione semantica, in cui i dati sono descritti da un modello esplicito, collegati fra loro, interrogabili da un endpoint e corredati di metadati conformi al profilo nazionale.

Il progetto lavora su un dataset di **13 opere d'arte** e lo porta lungo l'intera catena di pubblicazione, dalla tabella grezza alla scheda consultabile dall'utente finale:

```
CSV → ontologia OWL → RDF/Turtle → metadati DCAT-AP_IT → download, endpoint SPARQL, scheda dataset
```

Accanto a questa, un secondo filone costruisce la **conformità in materia di protezione dei dati personali**: l'informativa completa, due note di motivazione della base giuridica e una procedura interna di cancellazione.

Il perimetro è definito da tre personas — **Maria**, ricercatrice e data journalist che consulta e scarica i dati; **Luca**, data manager del Ministero che li pubblica; **Giulia**, funzionaria che tratta i dati personali conferiti dagli utenti — descritte per esteso nel [backlog](worklog/backlog).

---

## Il gruppo

| Componente | Ruolo principale | Area di responsabilità tecnica |
|---|---|---|
| Paolo | Product Owner | Ontologia e modello semantico |
| Ilaria | Scrum Master | Metadatazione DCAT-AP_IT |
| Asia | Data Expert | API ed endpoint SPARQL |
| Alessia | Privacy Expert | Conformità e protezione dei dati personali |

I ruoli sono rimasti stabili per tutta la durata del progetto, ma i confini sono stati volutamente porosi: trattandosi di un lavoro didattico, ogni componente ha partecipato ad attività fuori dalla propria area per imparare attraverso la pratica. È un compromesso rispetto all'applicazione rigorosa di SCRUM, e come tale è dichiarato nel report finale.

---

## Metodo di lavoro

Il progetto è stato condotto secondo **SCRUM**, in quattro sprint di circa quattro giorni ciascuno fra il 20 agosto e il 5 settembre 2026.

Una prima fase era stata avviata a luglio ed è stata **interrotta e ripresa da capo** dopo Ferragosto, su indicazione dello Scrum Master: il lavoro non era realmente incrementale e il gruppo procedeva in modo disgiunto, senza una board condivisa. Alla ripartenza la gestione è passata da Trello a **Jira**, per le funzionalità che il primo non offre in modo nativo — tipizzazione dei ticket, sprint delimitati, priorità, stima in story point e reportistica.

- **Board Trello:** [Progetto dati.cultura.gov.it](https://trello.com/invite/b/6a9e9e870a2c20dc7eae7c01/ATTI733ce5b920f6bfd8310fa15358a6c042B16E7D4C/progetto-daticulturagovit)
- **Registro degli sprint:** [`worklog/README.md`](worklog/README.md)

L'accettazione dei deliverable è avvenuta in una sessione collettiva di fine sprint, con tutti i componenti: un modello più orizzontale di quello prescritto, in cui la direzione del lavoro spetta al Product Owner ma la validazione è un atto del gruppo.

---

## Struttura del repository

```
.
├── README.md                    ← questo file
├── LICENSE                      ← CC BY 4.0
└── worklog/
    ├── README.md                ← registro dei quattro sprint
    ├── backlog/                 ← personas, epiche, 23 user story
    ├── sprint_1/                ← CSV, ontologia, mockup home page e footer
    ├── sprint_2/                ← mapping YARRRML, RDF, SPARQL, privacy, mockup
    ├── sprint_3/                ← metadati DCAT-AP_IT, download, API/SPARQL, privacy
    └── sprint_4/                ← scheda dataset, contatti, informativa completa
```

Ogni cartella di deliverable ha un proprio README che riporta il **test di accettazione** della user story e spiega dove e come è soddisfatto.

---

## Deliverable principali

### Dati e semantica

| Deliverable | Percorso |
|---|---|
| Dataset in CSV (completo e per categoria) | [`sprint_1/CSV`](worklog/sprint_1/CSV) |
| Ontologia OWL, diagrammi E-R e Graffoo, competency question | [`sprint_1/Ontologia`](worklog/sprint_1/Ontologia) |
| Mapping YARRRML e grafo RDF/Turtle | [`sprint_2/Ontologia`](worklog/sprint_2/Ontologia) |
| Query SPARQL di esempio e documentazione dell'endpoint | [`sprint_2/SPARQL`](worklog/sprint_2/SPARQL) |
| Metadati DCAT-AP_IT | [`sprint_3/Metadati`](worklog/sprint_3/Metadati) |

L'ontologia modella le opere d'arte con le classi `Artwork`, `Painting`, `CulturalInstituteOrSite`, `Place` e `TimeReference`. Quest'ultima, con le sue tre sottoclassi disgiunte, risponde a un problema concreto descritto nel backlog: le datazioni arrivano dai sistemi di origine in forme eterogenee — data completa, intervallo di anni, secolo — e senza un modello che le riconcili non sono confrontabili fra loro.

### Privacy

| Deliverable | Percorso |
|---|---|
| Informativa sul trattamento dei dati personali (documento completo) | [`sprint_4/Informativa_sul_trattamento_dei_dati_personali.pdf`](worklog/sprint_4/Informativa_sul_trattamento_dei_dati_personali.pdf) |
| Nota di motivazione della base giuridica — dati di navigazione | [`sprint_2/Privacy`](worklog/sprint_2/Privacy) |
| Sezione destinatari e accesso ai messaggi | [`sprint_3/Privacy`](worklog/sprint_3/Privacy) |
| Nota sulla base giuridica delle segnalazioni e procedura interna di cancellazione | [`sprint_4/Privacy`](worklog/sprint_4/Privacy) |

### Mockup dell'interfaccia

Home page e footer, sezione *Il progetto*, FAQ, pagina *Ontologia*, catalogo dataset con ricerca e filtri, scheda dataset, sezione *Scarica i dati*, pagina *API e SPARQL*, pagina *Contatti* e le schermate dell'informativa privacy. Si trovano nelle sottocartelle `Mockup/` di ciascuno sprint.

---

## Riprodurre il lavoro

Gli strumenti utilizzati sono tutti gratuiti o disponibili in versione gratuita.

1. **Ontologia** — aprire `RDF_Ontologia-PM.ttl` con [Protégé](https://protege.stanford.edu/) e validarla con il reasoner HermiT. Le competency question in `CQ_Onto-PM.txt` documentano ciò che il modello deve saper rispondere.
2. **Trasformazione dei dati** — caricare `mapping.yarrrml.yml` e i CSV su [Matey](https://rml.io/yarrrml/matey/) per rigenerare il grafo RDF. Il mapping è dichiarativo: al crescere dei dati la regola resta valida e non va riscritta.
3. **Endpoint SPARQL** — creare un repository su [GraphDB](https://graphdb.ontotext.com/) (nel progetto: `dati-cultura`) e importarvi il file RDF/Turtle. Le query di esempio in [`sprint_2/SPARQL`](worklog/sprint_2/SPARQL) sono documentate con il numero di righe atteso, così da verificare che l'importazione sia riuscita.

> L'endpoint è stato configurato in locale (`localhost:7200`) e non è quindi raggiungibile pubblicamente. Chi volesse interrogare i dati deve importare il grafo in una propria istanza.

---

## Nota sull'uso dell'Intelligenza Artificiale

Strumenti di IA sono stati impiegati nel corso del progetto, principalmente per la redazione dei report e per il confronto sulle scelte progettuali. Ogni contenuto prodotto in questo modo è stato letto, verificato e approvato dal gruppo prima di entrare nel repository. Dove l'IA è stata usata per un deliverable tecnico, il README della cartella corrispondente riporta una nota di trasparenza con le difformità individuate in fase di verifica e le correzioni applicate: si veda [`sprint_3/Metadati`](worklog/sprint_3/Metadati).

---

## Licenza

This work is licensed under a [Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg
