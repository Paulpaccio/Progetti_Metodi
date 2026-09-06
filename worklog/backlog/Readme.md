
## Catalogo Dati Beni Culturali — Backlog di Progetto

Documento di sintesi contenente le **Personas**, le **Epiche** e le **User Stories (US)**

---

## Personas 

### 1. Maria — Ricercatrice in storia dell’arte e data journalist *(Utente esterno del catalogo)*

##Descrizione generale##. Maria ha 34 anni e lavora come ricercatrice presso un dipartimento di beni culturali. Accanto all’attività accademica collabora con una testata online che si occupa di articoli divulgativi. Usa il catalogo in modo semplice: per ricerca, lettura e download dei dati relativi alle opere d’arte.
Ottima padronanza dei fogli di calcolo, discreta conoscenza di SPARQL, nessuna esperienza di programmazione. Conosce il dominio della catalogazione dei beni culturali meglio degli strumenti informatici che è costretta ad usare.

*Obiettivi*:
-	Individuare rapidamente i dataset pertinenti alla sua ricerca fra quelli pubblicati
-	Comprendere come sono strutturati i dati prima di scaricarli, per non perdere tempo su fonti inadatte
-	Incrociare le opere con i luoghi di conservazione per ricostruire distribuzioni territoriali
-	Citare correttamente le fonti e sapere con certezza se può ripubblicare ciò che ha scaricato

*Frustrazioni*. Impiega più tempo a capire com’è fatto un dataset che a usarlo. Alcune volte ha dovuto rinunciare a pubblicare un articolo perché la licenza del dato non era dichiarata. Sa scrivere una query ma non conosce i nomi delle proprietà, e le datazioni espresse in forme diverse le impediscono di confrontare le opere sull’asse temporale o di selezionare quelle di un determinato periodo.

*Motivazione*. Il catalogo le interessa perché promette dati collegati e non tabelle isolate. La possibilità di passare dall’opera, all’istituto, al territorio incarna l’essenza del suo lavoro che richiede un modello documentato: metadati che dichiarano licenza e provenienza, e date confrontabili fra loro.

---

## 2. Luca – Data Manager del Ministero della Cultura (editore e pubblicatore dei dati)

*Descrizione generale*. Luca ha 41 anni ed è funzionario presso una Direzione generale del MiC. Sovrintende l’intera catena di pubblicazione: produce i dati in CSV, ne modella la semantica in un’ontologia, genera la versione RDF e li metadata secondo la profilazione nazionale. Redige, inoltre, la sezione dell’informativa relativa al tracciamento del sito ed espone l’endpoint SPARQL e le API. Conosce RDF, RDFS e OWL, ha esperienza dei profili di metadatazione DCAT-AP e DCAT-AP_IT, e dei vocabolari controllati europei e nazionali.

*Obiettivi*:
-	Pubblicare dati che siano effettivamente riusabili, non soltanto scaricabili
-	Rendere il dataset reperibile dal portale nazionale 
-	Documentare il modello semantico in modo che sia interpretabile da un terzo
-	Garantire che la trasformazione da tabella a Linked Open Data sia reperibile

*Frustrazioni*. I dati che riceve provengono da sistemi eterogenei con convenzioni disomogenee: il caso peggiore sono le datazioni, nelle quali la stessa informazione compare come data completa, intervallo o secolo. Sa che un dataset con metadati incompleti non viene indicizzato al portale nazionale, ma i controlli di conformità sono manuali e dispendiosi. Diffida delle conversioni fatte a mano, perché non reggono quando il volume dei dati cresce.

*Motivazione*. Il rifacimento del catalogo è l’occasione per passare da una pubblicazione documentale a una pubblicazione semantica: dati descritti da un modello esplicito e interrogabili da un endpoint. Inoltre, è necessario rendere il processo riproducibile, così che l’aggiunta di nuove opere non richieda di rifare il lavoro da capo.

---


## 3. Giulia – Funzionaria addetta alla gestione dei contatti e alla compliance privacy

*Descrizione generale*. Giulia ha 38 anni e opera nell’ufficio che riceve le segnalazioni inviate dagli utenti attraverso la pagina contatti del sito. È la persona che materialmente tratta i dati personali che arrivano: prende parte al processo decisionale sui tempi di conservazione, ne gestisce l’accesso secondo le regole definite dall’organizzazione, gestisce le richieste di cancellazione e prende in carico i messaggi.

*Obiettivi*:
-	Sapere cosa può fare con i messaggi ricevuti e cosa no
-	Disporre di tempi di conservazione dichiarati e coerenti con le finalità del trattamento
-	Conoscere quali figure interne possono accedere ai messaggi, per rispettare il principio di minimizzazione
-	Rispondere a chi esercita un diritto all’oblio entro i tempi definiti
-	Riconoscere e gestire correttamente i messaggi che contengono dati personali e sensibili

*Frustrazioni*. Le procedure esistono ma sono disperse in documenti diversi: quando arriva una richiesta deve cercare il trattamento o procedura più adatta per soddisfarla. Teme i messaggi che contengono informazioni sulla salute o convinzioni personali, perché non sa se sta trattando dati sensibili e quali cautele deve usare.

*Motivazione*. La pagina contatti introduce il trattamento dei dati personali di cui Giulia è responsabile operativa. Le interessa che l’informativa sia completa e che le procedure interne vengano scritte e rese disponibili prima che il servizio entri in funzione. Le interessa che l'informativa dichiari con precisione i tempi di conservazione, i destinatari dei dati e le modalità di esercizio dei diritti dell’interessato: sono le informazioni che deve poter fornire quando un utente le chiede informazioni sul trattamento.

---

## Epiche

* **E1** — Home page e presentazione dell'iniziativa
* **E2** — Catalogo dati e ricerca dataset
* **E3** — Semantica e ontologie
* **E4** — Accesso ai dati via API e SPARQL
* **E5** — Pagina contatti e gestione dei messaggi
* **E6** — Privacy e protezione dei dati personali
* **E7** — Pubblicazione del dataset opere d'arte

---

## User Stories

| US ID | Titolo | Persona |
| :--- | :--- | :--- |
| **US1.1** | Home page chiara | Maria |
| **US1.2** | Ricerca dataset nel catalogo | Maria |
| **US1.3** | Consultare il modello semantico | Maria |
| **US1.4** | Accesso ai dati via API/SPARQL con esempi pronti | Maria |
| **US1.5** | Download dei dati | Maria |
| **US1.6** | Consultare i metadati per citazione, riuso e affidabilità | Maria |
| **US1.7** | Invio di un messaggio dalla pagina contatti | Maria |
| **US1.8** | Informazioni utili e immediate (footer) | Maria |
| **US1.9** | Il progetto dati.cultura.gov.it | Maria |
| **US1.10** | Sezione FAQ (domande frequenti) | Maria |
| **US1.11** | Formato visibile nella sezione dataset | Maria |
| **US1.12** | Licenza utilizzata nel footer | Maria |
| **US1.13** | Lasciare un commento | Maria |
| **US2.1** | Produzione dati in CSV | Luca |
| **US2.2** | Creazione dell'ontologia delle opere d'arte | Luca |
| **US2.3** | Trasformazione CSV → RDF/Turtle con YARRRML | Luca |
| **US2.4** | Metadatazione DCAT-AP_IT | Luca |
| **US2.5** | Informativa privacy: tracciamento del sito | Luca |
| **US2.6** | Esposizione di API e SPARQL endpoint | Luca |
| **US3.1** | Tempi di conservazione dei messaggi | Giulia |
| **US3.2** | Base giuridica del trattamento dei messaggi | Giulia |
| **US3.3** | Destinatari e accesso ai messaggi | Giulia |
| **US3.4** | Cancellazione su richiesta dell'interessato | Giulia |








