# Retrospettiva Sprint 3 — Progetto SHELL (dati.cultura.gov.it)

**Periodo dello sprint:** 28 agosto – 1 settembre
**Formato adottato:** Mad / Sad / Glad
**Partecipanti:** l'intero gruppo di progetto

> **Perché questo formato.** Lo Sprint 3 ha avuto un risultato tecnico solido e un incidente che ha inciso sul morale del gruppo. Un formato centrato sulle azioni avrebbe registrato la perdita della US1.2 come un problema da risolvere, perdendo però il dato più rilevante: l'effetto che ha avuto sulle persone. Mad/Sad/Glad separa **ciò che ha fatto arrabbiare**, **ciò che ha demoralizzato** e **ciò che ha dato soddisfazione**, e permette di tenere insieme le due facce dello sprint senza che l'incidente cancelli il lavoro riuscito.
>
> *Nota sul metodo:* "Mad" non indica rabbia verso una persona. Indica ciò che il gruppo giudica inaccettabile a livello di processo e che non vuole rivedere.

---

## 1. Sintesi dello sprint

Sul piano dei deliverable, il lavoro è stato **ben diviso** e ha chiuso la catena `CSV → ontologia → RDF/Turtle → metadatazione` richiesta dalla consegna: la metadatazione DCAT-AP_IT (US2.4) ha richiesto una collaborazione stretta fra chi conosceva il profilo e chi aveva prodotto i dati. Le due modalità di accesso ai dati (US1.5 download, US2.6 endpoint) sono state realizzate in parallelo e allineate alla stessa versione del dataset.

Lo sprint è però segnato dalla perdita della **US1.2 — Ricerca dataset nel catalogo**, approvata e successivamente sparita dal repository. Il gruppo ha deciso di ricrearla nello Sprint 4.

---

## 2. Verifica delle azioni dello Sprint 2

| # | Azione | Esito |
|---|---|---|
| A2.1 | Marcare in Jira le user story con contenuto provvisorio | Fatto |
| A2.2 | Completare i contenuti reali delle FAQ (US1.10) | Non completata: rinviata |
| A2.3 | Mantenere attivo l'impegno sulla segnalazione degli impedimenti | Rispettata: la perdita della US1.2 è stata comunicata subito al gruppo e gestita collettivamente |

> A2.3 ha superato la sua prima prova reale. Il problema è stato portato al gruppo appena rilevato e la decisione su come rimediare è stata presa insieme: è esattamente il comportamento che la retrospettiva dello Sprint 1 chiedeva.

---

## 3. Mad / Sad / Glad

### MAD — cosa non deve ripetersi

- **Un deliverable approvato è sparito dal repository.** Non è stato possibile stabilire se all'origine ci sia un errore tecnico o umano — un push andato perduto, una cartella sovrascritta, un commit su un branch poi non integrato. Nella cartella `sprint_3/Mockup/Dataset/` resta solo lo scheletro vuoto: due README senza contenuto e nessuna immagine. La traccia del deliverable c'è, il deliverable no.
- **Non sappiamo cosa sia successo.** Questo è l'aspetto più irritante, più della perdita in sé: senza una causa accertata non possiamo escludere che si ripeta. Non abbiamo un modo per ricostruire a posteriori cosa è stato caricato e quando.
- **L'approvazione non ha intercettato l'assenza.** La US1.2 è stata approvata su qualcosa che poi non c'era. L'approvazione collettiva introdotta nello Sprint 1 si è basata sulla dichiarazione di chi aveva svolto il lavoro: senza un controllo sul repository, approva un'intenzione.

### SAD — cosa ci ha demoralizzato

- **Rifare un lavoro già fatto e già approvato.** Non è il tempo perso a pesare, è il tipo di lavoro: rifare qualcosa di sbagliato ha un senso, rifare qualcosa che era giusto no. Il gruppo lo ha registrato come il momento più basso del progetto.
- **Doverci discostare dalla pianificazione.** Ricreare la US1.2 nello Sprint 4 significa portare in un altro sprint una user story che non gli appartiene. Il gruppo lo ha deciso consapevolmente, ma resta uno scostamento da sanare fra board e repository: la US1.2 non compare nella tabella dello Sprint 4 nel worklog.
- **I contenuti delle FAQ sono slittati di nuovo**, per il secondo sprint consecutivo, senza che sia stata presa una decisione esplicita: né completarli, né dichiararli fuori dal perimetro del progetto. Non è grave, ma è il tipo di cosa che si trascina fino alla fine.
- **La sproporzione fra sostanza ed effetto.** Uno sprint in cui quattro user story su quattro sono state chiuse bene viene ricordato per l'unica cosa che è andata storta.

### GLAD — cosa ci ha dato soddisfazione

- **La collaborazione sulla metadatazione DCAT-AP_IT.** È stata la parte più proficua dello sprint: nessuno l'avrebbe chiusa da solo con la stessa qualità, perché richiedeva insieme la conoscenza del profilo nazionale e quella dei dati prodotti negli sprint precedenti.
- **Aver chiuso la catena richiesta dalla consegna.** Con la US2.4 il percorso `CSV → ontologia → RDF/Turtle → metadatazione` è completo: i dati prodotti nello Sprint 1 e trasformati nello Sprint 2 sono ora descritti, scaricabili e interrogabili.
- **La divisione del lavoro.** Quattro user story su tre epiche diverse portate avanti in parallelo, senza sovrapposizioni e senza tempi morti.
- **La comunicazione ha funzionato.** Il problema è stato detto subito e la soluzione decisa insieme: rispetto allo Sprint 1, dove il ritardo era emerso a scadenza superata, è un miglioramento concreto e misurabile.
- **La nota di trasparenza sull'uso dell'IA** nel README della US2.4, con l'elenco delle quattro difformità individuate e corrette e la verifica del gruppo su ogni correzione prima di applicarla. È una pratica da estendere agli altri deliverable in cui sono stati usati strumenti di IA.
- **Aver deciso in fretta come rimediare**, senza cercare responsabilità individuali e senza che l'episodio generasse attriti nel gruppo.

---

## 4. Azioni per lo Sprint 4

| # | Azione | Responsabile | Verificabile in |
|---|---|---|---|
| A3.1 | Controllo del repository su ogni cartella prima dell'approvazione di fine sprint | tutte | Retrospettiva Sprint 4 |
| A3.2 | Ricreare il deliverable della US1.2 | Scrum Master | Report Sprint 4 |
| A3.3 | Allineare la board Jira alla ripianificazione della US1.2 | Scrum Master | Board Jira |
| A3.4 | Decidere esplicitamente il destino dei contenuti FAQ (completare o dichiarare fuori perimetro) | tutte | Retrospettiva Sprint 4 |
| A3.5 | Verificare che il lavoro sia sul remoto e visibile a un altro membro, non solo in locale | tutte | Retrospettiva Sprint 4 |
