# Retrospettiva Sprint 2 — Progetto SHELL (dati.cultura.gov.it)

**Periodo dello sprint:** 24 agosto – 28 agosto
**Formato adottato:** 4L — *Liked, Learned, Lacked, Longed for*
**Partecipanti:** l'intero gruppo di progetto

> **Perché questo formato.** Lo Sprint 2 non ha avuto criticità da rimuovere: uno schema centrato sui problemi (Start/Stop/Continue) avrebbe prodotto una retrospettiva quasi vuota. Il contenuto reale dello sprint è stato l'**apprendimento degli strumenti**, ed è quello che il modello 4L mette al centro: cosa ci è piaciuto, cosa abbiamo imparato, cosa ci è mancato, cosa avremmo voluto avere.

---

## 1. Sintesi dello sprint

Sprint senza intoppi. È stato lo sprint in cui il gruppo ha **preso confidenza con gli strumenti**: Jira per la gestione della board e GitHub per il versionamento e la pubblicazione dei deliverable. Il lavoro è scorso senza blocchi e senza necessità di rinegoziare il perimetro in corsa.

È anche lo sprint tecnicamente più denso del progetto: la trasformazione CSV → RDF/Turtle con YARRRML (US2.3) e la pubblicazione dell'endpoint SPARQL su GraphDB (US1.4) hanno prodotto la base dati su cui si appoggiano tutti gli sprint successivi. Il fatto che questo sia avvenuto senza criticità è il risultato più significativo dello sprint, non un dettaglio.

La user story rimasta aperta nello Sprint 1 è stata completata e approvata, come deciso nella retrospettiva precedente.

---

## 2. Verifica delle azioni dello Sprint 1

| # | Azione | Esito |
|---|---|---|
| A1.1 | Segnalare gli impedimenti entro il giorno in cui emergono | Non messa alla prova: nessun impedimento si è presentato in questo sprint |
| A1.2 | Approvazione collettiva delle user story | Applicata |
| A1.3 | Completare la user story rimasta aperta | Completata e approvata |

> Nota: A1.1 resta un'azione **non verificata**. Uno sprint senza impedimenti non dice se il canale di segnalazione funziona; lo si saprà solo alla prossima difficoltà.

---

## 3. Le quattro L

### LIKED — cosa ci è piaciuto

- **Lavorare senza attriti.** Per la prima volta il gruppo ha completato uno sprint senza dover rinegoziare nulla in corsa: cinque user story pianificate, cinque approvate.
- **Vedere i dati diventare un grafo interrogabile.** Il passaggio dalle tabelle CSV all'endpoint SPARQL con 337 statement è il momento in cui il progetto ha smesso di essere un insieme di file ed è diventato quello che le personas del backlog chiedevano.
- **La verifica delle query con risultati attesi.** Sapere in anticipo quante righe deve restituire una query — 13 per la prima, 7 per la seconda, con l'esclusione corretta delle opere del XX secolo — ha reso il controllo oggettivo invece che a impressione.
- **La divisione fra lavoro tecnico e lavoro documentale**, che ha permesso di procedere in parallelo su epiche diverse.

### LEARNED — cosa abbiamo imparato

- **YARRRML e il mapping dichiarativo.** Il passaggio da tabella a RDF non è una conversione una tantum ma una regola riutilizzabile: cambiando i dati di partenza, il mapping continua a valere. È la risposta diretta alla frustrazione di Luca nel backlog, che diffida delle conversioni fatte a mano perché non reggono al crescere del volume.
- **Che documentare un endpoint è parte del deliverable.** Indirizzo, repository, numero di triple e i due modi di eseguire una query (Workbench e chiamata API con URL encoding) sono informazioni senza le quali l'endpoint esiste ma non è usabile da nessun altro.
- **Il flusso Git di gruppo.** Commit più frequenti, struttura del repository coerente fra gli sprint, README per cartella: la curva di apprendimento iniziale si è ripagata già dentro questo sprint.
- **Che una user story può riusare invece di produrre.** La US1.3 non genera dati nuovi, riespone il diagramma e le competency question della US2.2: dichiararlo esplicitamente nel README ha reso leggibile la catena delle dipendenze.
- **Come si motiva una base giuridica.** La nota della US2.5 non si limita a citare l'articolo del GDPR ma spiega perché sono state escluse le alternative — un tipo di scrittura diverso da quello tecnico, con cui il gruppo non aveva esperienza.

### LACKED — cosa ci è mancato

- **Un modo per dichiarare le scelte progettuali, non solo i risultati.** Il mockup delle FAQ (US1.10) è stato approvato con testi segnaposto. La scelta è corretta — un mockup rappresenta la struttura della pagina, non i contenuti editoriali definitivi — ma il gruppo non l'ha mai discussa esplicitamente né messa a verbale: la nota lasciata nel README può quindi essere letta da un terzo come lavoro incompleto anziché come decisione.
- **Una verifica del lavoro sul repository al momento dell'approvazione.** In questo sprint non è servita perché non è mancato nulla, ma l'approvazione si è basata sulla dichiarazione di chi aveva svolto il lavoro, non su un controllo.
- **Il tempo per scrivere il report mentre lo sprint era in corso.** La documentazione di sprint è stata ricostruita a posteriori dalle sottocartelle.

### LONGED FOR — cosa avremmo voluto

- **Un ambiente condiviso per l'endpoint.** GraphDB gira in locale (`localhost:7200`): il risultato è verificabile solo sulla macchina di chi l'ha configurato, e questo rende impossibile a un altro membro del gruppo controllare le query in autonomia.
- **Una checklist di fine user story** — deliverable sul remoto, README compilato, test di accettazione riportato, board aggiornata — da spuntare prima di dichiarare il lavoro concluso.
- **Un verbale delle decisioni progettuali.** Diverse scelte — che cosa un mockup debba contenere, che cosa resti fuori dal perimetro — sono state prese di fatto senza essere registrate da nessuna parte.

---

## 4. Azioni per lo Sprint 3

| # | Azione | Responsabile | Verificabile in |
|---|---|---|---|
| A2.1 | Marcare in Jira le user story approvate con contenuto provvisorio, per non perderne traccia | Scrum Master | Board Jira |
| A2.2 | Mantenere A1.1 come impegno attivo, in attesa del primo impedimento reale | tutte | Retrospettiva Sprint 3 |
