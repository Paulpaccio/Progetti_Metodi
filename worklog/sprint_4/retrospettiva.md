# Retrospettiva Sprint 4 — Progetto SHELL (dati.cultura.gov.it)

**Periodo dello sprint:** 1 settembre – 5 settembre
**Formato adottato:** Start / Stop / Continue, preceduto dalla verifica delle azioni dello Sprint 3 e seguito da uno sguardo d'insieme sul progetto
**Partecipanti:** l'intero gruppo di progetto

---

## 1. Sintesi dello sprint

Ultimo sprint del progetto, condotto sotto la pressione della scadenza. L'arrivo di settembre ha portato **tensione e ansia di finire in tempo**, che è la condizione tipica dell'ultimo sprint e va registrata come tale: non ha compromesso i deliverable, ma ha condizionato il modo di lavorare, spingendo verso il fare più che verso il verificare.

Sul piano dei contenuti lo sprint ha chiuso due fronti:

- **la catena dei dati**, con la scheda dataset consultabile (US1.6) che espone all'utente finale i metadati DCAT-AP_IT prodotti nello Sprint 3;
- **la conformità privacy**, con le tre user story (US3.1, US3.2, US3.4) che completano l'informativa avviata nello Sprint 2 e proseguita nello Sprint 3, ora assemblata nel documento unico `Informativa_sul_trattamento_dei_dati_personali.pdf`.

È stato inoltre ricreato il deliverable della **US1.2**, perduto nello Sprint 3, e prodotta la seconda versione del footer.

### Il tema dello sprint: il controllo finale

Il bisogno emerso con più forza è quello di **fare il check di ogni cosa**: verificare che ci sia tutto e che tutto sia congruente. La verifica finale ha effettivamente individuato una serie di incongruenze:

| Incongruenza | Stato |
|---|---|
| `sprint_3/README.md` e `sprint_4/README.md` privi di contenuto | Da sanare |
| `Mockup/Licenza_Footer/README.md` privo di contenuto | Da sanare |
| `sprint_4/Privacy/README.md` cita nomi di file diversi da quelli reali | Da sanare |
| Lo stesso README colloca l'informativa PDF in `worklog/` anziché in `worklog/sprint_4/` | Da sanare |
| `sprint_4/Mockup/Privacy/README.md` inizia dalla sezione 3, numerazione non autoconsistente | Da sanare |
| Link del report Sprint 1 a `/tree/main/sprint_1` anziché `/tree/main/worklog/sprint_1` | Da sanare |
| `sprint_3/Mockup/Dataset/` rimasta vuota dopo lo spostamento della US1.2 | Da sanare |
| US1.2 e la seconda versione del footer non compaiono nella tabella dello Sprint 4 nel worklog | Da sanare |

Nessuna di queste riguarda la sostanza del lavoro: sono tutte questioni di **coerenza documentale**, ed è significativo che siano emerse tutte insieme alla fine invece che progressivamente. È la conferma che manca un criterio condiviso di "fatto".

---

## 2. Verifica delle azioni dello Sprint 3

| # | Azione | Esito |
|---|---|---|
| A3.1 | Controllo del repository prima dell'approvazione | Eseguita solo a fine progetto, non a fine sprint |
| A3.2 | Ricreare il deliverable della US1.2 | Completata: `sprint_4/Mockup/Dataset/` |
| A3.3 | Allineare la board Jira alla ripianificazione della US1.2 | Da verificare: la US1.2 non compare nella tabella dello Sprint 4 nel worklog |
| A3.4 | Decidere il destino dei contenuti FAQ | Non affrontata |

---

## 3. Start / Stop / Continue

### START

- **Definire una Definition of Done scritta e condivisa.** Una user story è "fatta" quando: il deliverable è sul remoto, il README della cartella è compilato, i test di accettazione sono riportati con la loro copertura, i link sono verificati e la board è aggiornata. Quasi tutte le incongruenze rilevate a fine progetto rientrano in uno di questi cinque punti.
- **Distribuire il controllo di coerenza lungo lo sprint** invece di concentrarlo alla fine. Il check finale ha funzionato, ma è arrivato quando il margine per intervenire era minimo, ed è proprio ciò che genera l'ansia da scadenza.
- **Scrivere il report di sprint durante lo sprint**, non dopo. I report degli Sprint 3 e 4 sono stati redatti a posteriori, quando le informazioni andavano recuperate dalle sottocartelle invece che annotate mentre il lavoro veniva svolto.
- **Tenere conto della pressione da scadenza in fase di pianificazione.** L'ultimo sprint di un progetto non ha la stessa capacità degli altri: parte della capacità va riservata alla chiusura, alla verifica e alla documentazione, non solo a nuovi incrementi.

### STOP

- **Rimandare la documentazione all'ultimo.** README vuoti e report rimasti in bianco sono il debito che si accumula quando la documentazione è trattata come un'attività successiva anziché come parte del deliverable.
- **Lasciare cartelle vuote nel repository** dopo lo spostamento di un deliverable: confondono chi legge e fanno sembrare incompleto un lavoro che è stato completato altrove.
- **Rinviare indefinitamente le decisioni piccole.** I contenuti FAQ sono passati per quattro sprint senza che nessuno decidesse se completarli o escluderli dal perimetro.

### CONTINUE

- **Il check finale sistematico**, che ha effettivamente individuato tutto ciò che non tornava. Va anticipato, non abbandonato.
- **La costruzione incrementale dell'informativa privacy.** Sezione dopo sezione, sprint dopo sprint, fino al documento unico: è il caso in cui il metodo incrementale ha dato il risultato migliore di tutto il progetto.
- **La produzione di documenti interni oltre a quelli pubblici** (nota di motivazione della base giuridica, procedura di cancellazione), che mostrano il ragionamento dietro le scelte e non solo il loro esito.
- **La consapevolezza degli scostamenti.** Il gruppo ha riconosciuto che ricreare la US1.2 nello Sprint 4 non era conforme alla pianificazione e l'ha dichiarato invece di nasconderlo.

---

## 4. Azioni di chiusura

| # | Azione | Responsabile | Stato |
|---|---|---|---|
| A4.1 | Compilare i README di sprint rimasti vuoti | PO | Da fare |
| A4.2 | Correggere i riferimenti a file e percorsi errati in `sprint_4/Privacy/README.md` | Privacy Expert | Da fare |
| A4.3 | Correggere il link rotto nel report dello Sprint 1 | PO | Da fare |
| A4.4 | Rimuovere o popolare le cartelle vuote (`sprint_3/Mockup/Dataset`, `Licenza_Footer`) | PO | Da fare |
| A4.5 | Allineare il worklog inserendo US1.2 e la seconda versione del footer nello Sprint 4 | PO | Da fare |
| A4.6 | Decidere e dichiarare lo stato finale dei contenuti FAQ | tutti | Da fare |

---

## 5. Sguardo d'insieme sul progetto

**Cosa ha funzionato.** La ripartenza secondo SCRUM decisa nello Sprint 1 è stata la scelta giusta, anche a costo di rifare del lavoro: senza board, sprint e incrementi verificabili il progetto non avrebbe retto quattro iterazioni. La costruzione incrementale ha dato i risultati migliori dove la dipendenza fra sprint era più stretta — la catena CSV → ontologia → RDF → metadati → scheda dataset, e l'informativa privacy composta sezione per sezione. La comunicazione interna è migliorata sprint dopo sprint: il problema dello Sprint 1 non si è più ripetuto e la perdita della US1.2 è stata gestita collettivamente e senza attriti.

**Cosa è costato di più.** Due cose, entrambe di processo e non di merito. La prima è la **gestione della configurazione**: un deliverable approvato e poi perduto è il tipo di incidente che una disciplina più rigorosa su commit e push avrebbe evitato. La seconda è la **documentazione trattata come attività finale**: i README vuoti, i report scritti a posteriori e le incongruenze emerse tutte insieme nell'ultimo giorno derivano dalla stessa causa.

**Cosa porteremmo in un progetto successivo.** Una Definition of Done scritta prima del primo sprint; il controllo del repository come parte della sessione di approvazione e non come attività di chiusura; il report di sprint compilato mentre lo sprint è in corso; una capacità ridotta pianificata per l'ultimo sprint.
