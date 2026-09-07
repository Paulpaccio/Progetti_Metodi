# Worklog — Riepilogo dei quattro sprint

Registro del lavoro del progetto **dati.cultura**, rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Il progetto è stato condotto in **quattro sprint** fra il 20 agosto e il 5 settembre 2026, secondo il framework SCRUM.

**Board Trello:** [Progetto dati.cultura.gov.it](https://trello.com/invite/b/6a9e9e870a2c20dc7eae7c01/ATTI733ce5b920f6bfd8310fa15358a6c042B16E7D4C/progetto-daticulturagovit)

La gestione operativa è avvenuta su **Jira**, adottato alla ripartenza del progetto per le funzionalità che Trello non offre in modo nativo: tipizzazione dei ticket (epica, story, sotto-attività), sprint con inizio e fine definiti, priorità, stima in story point e reportistica. I codici `PM-n` nelle tabelle sottostanti sono gli identificativi dei ticket Jira.

---

## Come leggere questo registro

Ogni sprint ha una cartella dedicata (`sprint_1` … `sprint_4`) contenente:

- un **README di sprint**, che riporta lo stato delle user story, i deliverable prodotti e la copertura dei test di accettazione;
- una **retrospettiva**, con la verifica delle azioni dello sprint precedente e le azioni decise per quello successivo;
- una **cartella per deliverable**, ciascuna con il proprio README che riporta il testo del test di accettazione e spiega dove è soddisfatto.

Il backlog completo — personas, epiche, user story e test di accettazione — si trova in [`backlog/`](backlog/).

### Stati della board

| Stato | Significato attribuito dal gruppo |
|---|---|
| Da fare | Il ticket è entrato nello sprint e il lavoro è stato avviato |
| In corso | La lavorazione è attiva |
| Completato | Il lavoro è stato svolto ed è in attesa di revisione |
| Approvato | La revisione è stata superata e il lavoro è accettato |

L'approvazione è avvenuta in una **sessione collettiva di fine sprint**: tutti i componenti esaminano insieme il lavoro prodotto e lo accettano come un unico corpo. La scelta e le sue conseguenze sono discusse nelle retrospettive.

---

## Sprint 1 (20 agosto – 24 agosto)

Primo sprint dopo la ripartenza del progetto. Obiettivo: costruire le fondamenta della catena di pubblicazione — i dati grezzi e il modello semantico che li descrive — e le prime schermate del portale.

| User Story | Ticket | Priorità | Stima (SP) | Epic | Deliverable |
|---|---|---|---|---|---|
| US1.1 - Home page chiara | PM-10 | Medium | 5.0 | Home page e presentazione dell'iniziativa | [Mockup/HomePage](sprint_1/Mockup/HomePage) |
| US2.1 - Produzione dati in CSV | PM-9 | High | 4.0 | Pubblicazione del dataset opere d'arte | [CSV](sprint_1/CSV) |
| US2.2 - Creazione dell'ontologia delle opere d'arte | PM-16 | Highest | 10.0 | Semantica e ontologie | [Ontologia](sprint_1/Ontologia) |

**Ulteriori deliverable presenti nel repository:** [Mockup/Footer](sprint_1/Mockup/Footer), relativo alla US1.8 (*Informazioni utili e immediate*).

**Esito.** Sprint chiuso con i deliverable approvati. La creazione dell'ontologia è stata portata a completamento nello Sprint 2: il responsabile, per problemi personali, non ha potuto caricare il lavoro nei tempi previsti e il gruppo ha deciso collettivamente di approvarla nell'iterazione successiva.

📄 [Report dello sprint](sprint_1/README.md) · 🔄 [Retrospettiva](sprint_1/Retrospettiva.md)

---

## Sprint 2 (24 agosto – 28 agosto)

Sprint a maggiore densità tecnica: trasformazione dei dati in RDF, pubblicazione dell'endpoint SPARQL e avvio dell'informativa privacy.

| User Story | Ticket | Priorità | Stima (SP) | Epic | Deliverable |
|---|---|---|---|---|---|
| US1.3 - Consultare il modello semantico | PM-18 | Low | 4.0 | Semantica e ontologie | [Mockup/Semantica](sprint_2/Mockup/Semantica) |
| US1.4 - Accesso ai dati via API/SPARQL con esempi pronti | PM-21 | High | 4.0 | Accesso ai dati via API e SPARQL | [SPARQL](sprint_2/SPARQL) |
| US2.3 - Trasformazione CSV → RDF/Turtle con YARRRML | PM-20 | Highest | 10.0 | Pubblicazione del dataset opere d'arte | [Ontologia](sprint_2/Ontologia) |
| US2.5 - Informativa privacy: tracciamento del sito | PM-28 | High | 6.0 | Privacy e protezione dei dati personali | [Privacy](sprint_2/Privacy) · [Mockup/Privacy](sprint_2/Mockup/Privacy) |
| US2.2 - Creazione dell'ontologia delle opere d'arte (completamento) | PM-16 | Highest | 10.0 | Semantica e ontologie | [sprint_1/Ontologia](sprint_1/Ontologia) |

**Ulteriori deliverable presenti nel repository:** [Mockup/ilProgetto](sprint_2/Mockup/ilProgetto), relativo alla US1.9, e [Mockup/DomandeFrequenti](sprint_2/Mockup/DomandeFrequenti), relativo alla US1.10.

**Esito.** Sprint chiuso senza criticità. È lo sprint in cui il gruppo ha preso confidenza con Git e Jira.

📄 [Report dello sprint](sprint_2/README.md) · 🔄 [Retrospettiva](sprint_2/Retrospettiva.md)

---

## Sprint 3 (28 agosto – 1 settembre)

Sprint che chiude la catena richiesta dalla consegna con la metadatazione, e realizza le due modalità di accesso ai dati.

| User Story | Ticket | Priorità | Stima (SP) | Epic | Deliverable |
|---|---|---|---|---|---|
| US1.5 - Download dei dati | PM-23 | High | 6.0 | Pubblicazione del dataset opere d'arte | [Mockup/Scarica_dati](sprint_3/Mockup/Scarica_dati) |
| US2.4 - Metadatazione DCAT-AP_IT | PM-25 | Highest | 7.0 | Pubblicazione del dataset opere d'arte | [Metadati](sprint_3/Metadati) |
| US2.6 - Esposizione di API e SPARQL endpoint | PM-31 | Medium | 6.0 | Accesso ai dati via API e SPARQL | [Mockup/API_SPARQL](sprint_3/Mockup/API_SPARQL) |
| US3.3 - Destinatari e accesso ai messaggi | PM-17 | Medium | 4.0 | Privacy e protezione dei dati personali | [Privacy](sprint_3/Privacy) · [Mockup/Privacy](sprint_3/Mockup/Privacy) |

**Esito.** Lavoro ben diviso e collaborazione proficua sulla metadatazione. Lo sprint è però segnato dalla perdita del deliverable della **US1.2** (*Ricerca dataset nel catalogo*), approvato e successivamente sparito dal repository per una causa che non è stato possibile accertare: la cartella `Mockup/Dataset` ne conserva solo lo scheletro vuoto. Il gruppo ha deciso di ricrearlo nello Sprint 4.

📄 [Report dello sprint](sprint_3/README.md) · 🔄 [Retrospettiva](sprint_3/Retrospettiva.md)

---

## Sprint 4 (1 settembre – 5 settembre)

Sprint conclusivo: la scheda dataset consultabile, la pagina Contatti e il completamento dell'informativa privacy.

| User Story | Ticket | Priorità | Stima (SP) | Epic | Deliverable |
|---|---|---|---|---|---|
| US1.6 - Consultare i metadati per citazione, riuso e affidabilità | PM-27 | High | 4.0 | Pubblicazione del dataset opere d'arte | [Mockup/Metadati Dataset](sprint_4/Mockup/Metadati%20Dataset) |
| US1.7 - Invio di un messaggio dalla pagina contatti | PM-29 | Low | 4.0 | Pagina contatti e gestione dei messaggi | [Contatti](sprint_4/Contatti) |
| US3.1 - Tempi di conservazione dei messaggi | PM-26 | Medium | 4.0 | Privacy e protezione dei dati personali | [Mockup/Privacy](sprint_4/Mockup/Privacy) |
| US3.2 - Base giuridica del trattamento dei messaggi | PM-15 | Highest | 4.0 | Privacy e protezione dei dati personali | [Privacy](sprint_4/Privacy) |
| US3.4 - Cancellazione su richiesta dell'interessato | PM-19 | High | 6.0 | Privacy e protezione dei dati personali | [Privacy](sprint_4/Privacy) |

**Ulteriori deliverable presenti nel repository:** [Mockup/Dataset](sprint_4/Mockup/Dataset), che ricrea il deliverable della US1.2 perduto nello Sprint 3, e [Mockup/Licenza_Footer](sprint_4/Mockup/Licenza_Footer), seconda versione del footer relativa alla US1.12.

**Esito.** Tutti i deliverable completati. L'informativa privacy è stata assemblata nel documento unico [`Informativa_sul_trattamento_dei_dati_personali.pdf`](sprint_4/Informativa_sul_trattamento_dei_dati_personali.pdf), che raccoglie le sezioni prodotte dallo Sprint 2 in poi.

📄 [Report dello sprint](sprint_4/README.md) · 🔄 [Retrospettiva](sprint_4/Retrospettiva.md)

---

## Le due catene di lavorazione

Il progetto si legge meglio seguendo i due filoni che lo attraversano, entrambi costruiti per incrementi successivi.

**Catena dei dati.** I CSV prodotti nello Sprint 1 sono gli stessi che, trasformati in RDF/Turtle nello Sprint 2, descritti da metadati DCAT-AP_IT nello Sprint 3 e presentati all'utente nello Sprint 4, risultano alla fine scaricabili, interrogabili e citabili:

```
CSV (US2.1) → ontologia (US2.2) → RDF/Turtle (US2.3) → metadati DCAT-AP_IT (US2.4)
                                        ↓                        ↓
                          endpoint SPARQL (US1.4, US2.6)   scheda dataset (US1.6)
                                        ↓
                              download dei dati (US1.5)
```

**Catena della privacy.** L'informativa non è stata scritta in una volta, ma composta sezione dopo sezione: dati di navigazione e relativa base giuridica (US2.5, Sprint 2), destinatari dei dati (US3.3, Sprint 3), tempi di conservazione, gestione delle segnalazioni e diritti dell'interessato (US3.1, US3.2, US3.4, Sprint 4). Le accompagnano due note di motivazione della base giuridica e una procedura interna di cancellazione.

---

## Stato finale del backlog

Su **23 user story**: 21 completate e approvate, 2 non pianificate in alcuno sprint (US1.11 — *Formato visibile nella sezione dataset*, la cui copertura da parte dei badge di formato nella pagina Dataset è da verificare, e US1.13 — *Lasciare un commento*).

Nota sui contenuti delle FAQ: nel mockup della US1.10 domande e risposte sono testi segnaposto. È una scelta progettuale e non un lavoro incompleto — un mockup rappresenta la struttura e il comportamento della pagina, non i suoi contenuti editoriali definitivi, che in un contesto reale sarebbero forniti dalla redazione.## Sprint 1 (20 agosto - 24 agosto)
