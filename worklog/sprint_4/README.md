# Riepilogo Sprint 4 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il quarto e ultimo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Periodo: 1 settembre – 5 settembre.

Repository: [Paulpaccio/Progetti_Metodi — sprint_4](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4)

---

## Struttura della cartella

```
worklog/sprint_4/
├── README.md                                            ← questo file
├── Informativa_sul_trattamento_dei_dati_personali.pdf   ← informativa privacy completa
├── Contatti/
│   ├── README.md
│   └── Immagini/
├── Mockup/
│   ├── Dataset/
│   │   ├── README.md
│   │   └── Immagini/
│   ├── Licenza_Footer/
│   │   ├── README.md
│   │   └── Footer_V2.png
│   ├── Metadati Dataset/
│   │   ├── README.md
│   │   └── 13.png, 14.png, 15.png
│   └── Privacy/
│       ├── README.md
│       └── Immagini/
└── Privacy/
    ├── README.md
    ├── nota-motivazione-base-giuridica-2.md
    └── procedura-interna-cancellazione-dati.md
```

---

## 1. Stato delle User Story (board Trello/Jira)

| US | Titolo | Ticket | Priorità | Stima (SP) | Stato |
|---|---|---|---|---|---|
| US1.6 | Consultare i metadati per citazione, riuso e affidabilità | PM-27 | High | 4.0 | Approvato |
| US1.7 | Invio di un messaggio dalla pagina contatti | PM-29 | Low | 4.0 | Approvato |
| US3.1 | Tempi di conservazione dei messaggi | PM-26 | Medium | 4.0 | Approvato |
| US3.2 | Base giuridica del trattamento dei messaggi | PM-15 | Highest | 4.0 | Approvato |
| US3.4 | Cancellazione su richiesta dell'interessato | PM-19 | High | 6.0 | Approvato |

**Totale story point dello sprint: 22.0**

---

## 2. Deliverable prodotti

### 2.1 US1.6 — Consultare i metadati per citazione, riuso e affidabilità
Cartella: [`worklog/sprint_4/Mockup/Metadati Dataset`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Mockup/Metadati%20Dataset)

Mockup della **scheda del dataset**, la pagina che si apre selezionando un dataset dall'elenco del catalogo. Riporta in forma leggibile i metadati DCAT-AP_IT prodotti in **US2.4** (Sprint 3) e le due distribuzioni scaricabili.

La pagina risponde a tre esigenze distinte di chi consulta il catalogo: **citare** correttamente il dataset in una pubblicazione, **valutarne l'affidabilità** attraverso la data di ultimo aggiornamento, **sapere se può essere riutilizzato** verificando la licenza. Ogni valore visualizzato corrisponde a una tripla di `metadati_dcat-ap_it.ttl`: la pagina non introduce informazioni che il metadato non contenga.

Lo stesso dataset è offerto in CSV e in RDF/Turtle, secondo il modello DCAT — un unico dataset e due **distribuzioni**, che ne sono l'incarnazione in formati diversi. Licenza e formato sono dichiarati sulla distribuzione, mentre titolare, tema e date valgono per entrambe.

> Questa pagina *non produce nuovi metadati*: visualizza il deliverable di **US2.4**. Le entità `Dataset`, `Distribution`, `Publisher` e `License` erano già presenti nel modello concettuale, quindi la user story non lo estende ulteriormente.

### 2.2 US1.7 — Invio di un messaggio dalla pagina contatti
Cartella: [`worklog/sprint_4/Contatti`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Contatti)

Mockup ad alta fedeltà, statico, della pagina **Contatti**, in quattro schermate:

1. **Modulo di contatto**: campi obbligatori Nome, Cognome, Email e Messaggio, campo facoltativo *Tipologia di richiesta*, captcha a immagine e pulsante *Invia messaggio*. Non è richiesta la creazione di un account.
2. **Tipologia di richiesta**: tendina che classifica il messaggio in ingresso fra sei opzioni (feedback su un dataset, richiesta dataset, segnalazione di riuso, segnalazione malfunzionamento portale, segnalazione generica, altro).
3. **Modulo compilato**: esempio con i dati di *Elena Marchetti*, bibliotecaria comunale, che segnala un link non funzionante fra le pagine *Scarica Dati* e *API e SPARQL*.
4. **Conferma di ricezione**: messaggio personalizzato con nome e cognome, numero di riferimento univoco (es. `MSG-1757`) e stato **da lavorare**, a indicare la presa in carico.

Questa pagina introduce il trattamento di dati personali su cui si fondano le tre user story privacy dello sprint.

### 2.3 US3.1 — Tempi di conservazione dei messaggi
Cartelle: [`worklog/sprint_4/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Privacy) e [`worklog/sprint_4/Mockup/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Mockup/Privacy)

Sezione **"Periodo di conservazione"** dell'informativa (sezione 9 del PDF completo) e relativo mockup. La schermata integra e completa la tabella già avviata con **US2.5** (Sprint 2): alla riga sui dati di navigazione si aggiunge quella sulle segnalazioni inviate tramite la pagina dei contatti, portando la tabella alla versione completa con entrambi i trattamenti.

| Trattamento | Conservazione |
|---|---|
| Segnalazioni inviate tramite la pagina dei contatti | tempo necessario alla gestione, comunque non oltre 24 mesi |
| Dati di navigazione | non oltre 7 giorni |

Deliverable: sezione nell'informativa completa (`Informativa_sul_trattamento_dei_dati_personali.pdf`) e mockup `07-tempi-conservazione.png`.

### 2.4 US3.2 — Base giuridica del trattamento dei messaggi
Cartelle: [`worklog/sprint_4/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Privacy) e [`worklog/sprint_4/Mockup/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Mockup/Privacy)

Sezione **"Gestione delle segnalazioni inviate tramite la pagina dei contatti"** (sezione 4.1 del PDF), che completa la parte *Trattamenti effettuati, finalità e base giuridica* avviata con **US2.5**. Il blocco è articolato in **Dati trattati** (nome, cognome, email e contenuto del messaggio), **Finalità** (ricezione e riscontro delle segnalazioni) e **Base giuridica**.

La nota `nota-motivazione-base-giuridica-2.md` argomenta la scelta dell'**art. 6, par. 1, lett. e) GDPR** (esecuzione di un compito di interesse pubblico) su tre punti:

- **perché non il consenso**, benché il dato sia conferito volontariamente: l'EDPB ne sconsiglia l'uso in presenza di uno squilibrio di potere fra cittadino e autorità pubblica, e la revocabilità (art. 7, par. 3) renderebbe l'attività istituzionale dipendente dall'utente;
- **perché non il legittimo interesse**: l'art. 6, par. 1, ultimo periodo lo esclude espressamente per le autorità pubbliche nell'esecuzione dei loro compiti;
- **fondamento normativo** (art. 6, par. 3): art. 2-*ter* del d.lgs. 196/2003, in combinato con il d.lgs. 82/2005 (Codice dell'amministrazione digitale) e i compiti di comunicazione istituzionale del Ministero.

Ne discende, sul piano dei diritti, la spettanza del diritto di **opposizione** (art. 21) e la non applicabilità della **portabilità** (art. 20).

Deliverable: sezione nell'informativa completa, nota di motivazione (`nota-motivazione-base-giuridica-2.md`) e mockup `08-gestione-segnalazioni-contatti.png`.

### 2.5 US3.4 — Cancellazione su richiesta dell'interessato
Cartelle: [`worklog/sprint_4/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Privacy) e [`worklog/sprint_4/Mockup/Privacy`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Mockup/Privacy)

Sezione **"Diritti dell'interessato"** dell'informativa (sezione 11 del PDF): elenco dei diritti esercitabili (accesso, rettifica, cancellazione, limitazione, opposizione), precisazione che la portabilità non è applicabile trattandosi di trattamento fondato sul compito di interesse pubblico, e modalità di esercizio (richiesta al Titolare o al RPD, riscontro entro un mese).

Il documento `procedura-interna-cancellazione-dati.md` è un **documento interno**, non destinato alla pubblicazione nell'informativa, e definisce il flusso operativo con cui il Ministero dà seguito alle richieste ex art. 17 GDPR:

1. **Ricezione**: la richiesta perviene ai recapiti del Titolare o del RPD, viene registrata e assegnata al funzionario addetto ai contatti.
2. **Verifica**: identità del richiedente ed eventuali obblighi di legge o esigenze di accertamento di responsabilità che impongano la conservazione (nel qual caso la cancellazione è differita o rifiutata con motivazione).
3. **Esecuzione**: cancellazione irreversibile di nome, cognome, email e contenuto del messaggio, inclusi i backup secondo i relativi cicli.
4. **Tempi di risposta**: senza ingiustificato ritardo e comunque entro un mese, prorogabile di due mesi nei casi complessi con comunicazione motivata (art. 12, par. 3).
5. **Tracciabilità**: registrazione di ogni richiesta e del relativo esito ai fini di accountability (art. 5, par. 2), senza conservare i dati cancellati.

Deliverable: sezione nell'informativa completa, procedura interna (`procedura-interna-cancellazione-dati.md`) e mockup `09-diritti-interessato.png`.

### 2.6 Materiali aggiuntivi prodotti nello sprint

Nella cartella sono presenti due mockup che non rientrano nelle user story pianificate per lo sprint:

- **Pagina Dataset** ([`Mockup/Dataset`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Mockup/Dataset)) — riferita a **US1.2 Ricerca dataset nel catalogo**, in due schermate: pannello *Cerca tra dataset* con ricerca per titolo e per parola chiave, selettore *Ordina per* e filtri per categorie (Temi, Cataloghi, Categorie HVD); elenco delle schede dataset con titolo, descrizione, badge dei formati disponibili, ente pubblicatore, data di ultima modifica, tema e tag; paginazione e footer.
- **Licenza nel footer** ([`Mockup/Licenza_Footer`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/worklog/sprint_4/Mockup/Licenza_Footer)) — seconda versione del footer (`Footer_V2.png`), che aggiorna il mockup prodotto in **US1.8** (Sprint 1).

---

## 3. Copertura dei test di accettazione

| US | Requisito | Dove è soddisfatto |
|---|---|---|
| US1.6 | Titolare (`dct:rightsHolder`) | Ministero della Cultura |
| US1.6 | Editore (`dct:publisher`) | Ministero della Cultura |
| US1.6 | Identificativo (`dct:identifier`) | `m_bac:D.1` |
| US1.6 | Licenza (`dct:license`) | CC BY 4.0, URI dal vocabolario italiano |
| US1.6 | Data di aggiornamento (`dct:modified`) | 25/08/2026 |
| US1.7 | Modulo con campi obbligatori e invio senza account | Prima schermata, `Contatti_Vuoto.png` |
| US1.7 | Classificazione della richiesta | Seconda schermata, sei opzioni in tendina |
| US1.7 | Conferma di ricezione con riferimento univoco | Quarta schermata, `MSG-1757`, stato *da lavorare* |
| US3.1 | Tempi di conservazione dichiarati per entrambi i trattamenti | Sezione 9 dell'informativa, mockup `07-tempi-conservazione.png` |
| US3.2 | Base giuridica esplicitata e motivata | Sezione 4.1 dell'informativa, `nota-motivazione-base-giuridica-2.md` |
| US3.4 | Diritti dell'interessato elencati con modalità di esercizio | Sezione 11 dell'informativa, mockup `09-diritti-interessato.png` |
| US3.4 | Procedura interna di cancellazione formalizzata | `procedura-interna-cancellazione-dati.md` |

---

## Nota

Con questo sprint si chiude il progetto. L'**informativa privacy completa** ([`Informativa_sul_trattamento_dei_dati_personali.pdf`](https://github.com/Paulpaccio/Progetti_Metodi/blob/main/worklog/sprint_4/Informativa_sul_trattamento_dei_dati_personali.pdf)) è il documento che assembla le sezioni prodotte in modo incrementale nei quattro sprint: dati di navigazione e relativa base giuridica (**US2.5**, Sprint 2), destinatari dei dati (**US3.3**, Sprint 3), tempi di conservazione, gestione delle segnalazioni e diritti dell'interessato (**US3.1**, **US3.2**, **US3.4**, questo sprint).

Sul versante dati, **US1.6** completa la catena della epic *Pubblicazione del dataset opere d'arte*: i CSV di **US2.1** (Sprint 1), la trasformazione in RDF/Turtle di **US2.3** (Sprint 2), la metadatazione DCAT-AP_IT di **US2.4** e il download di **US1.5** (Sprint 3) trovano qui la loro presentazione all'utente finale, nella scheda dataset consultabile dal catalogo.
