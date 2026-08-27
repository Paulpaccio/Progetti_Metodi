
# US1.3 — Consultare il modello semantico

Documentazione dell'incremento di prodotto relativo alla User Story **US1.3 — Consultare il modello semantico**, nell'ambito del progetto **SHELL**, sotto-progetto **dati.cultura**.

> **Come ricercatrice, voglio comprendere come sono strutturati e collegati i dati sulle opere d'arte, per poterli interpretare correttamente e formulare interrogazioni sui dati.**

L'incremento consiste nella pagina **Ontologia** nell'ambito del rifacimento del catalogo, che espone in forma divulgativa il modello concettuale formalizzato nella US2.2 (Sprint 1). Non produce nuovi dati: riusa il diagramma Graffoo e le competency question già prodotti.

---

## 1. Struttura della pagina

La pagina è organizzata in quattro sezioni, navigabili da un indice laterale sempre visibile:

| Sezione | Contenuto |
|---|---|
| **L'ontologia delle opere d'arte** | Inquadramento: che cosa documenta la sezione, perché il modello è la chiave di lettura dei dataset, riferimento agli standard W3C (RDF, RDFS, OWL) |
| **Esplora il modello** | Diagramma semplificato delle cinque classi, legenda con identificativo di ciascuna classe, approfondimento sul trattamento del tempo |
| **A quali domande risponde** | Tre domande in linguaggio naturale, in accordion, con risposta ed esempio sui dati pubblicati |
| **Scarica il modello** | Ontologia in RDF/Turtle, diagramma Graffoo in PNG, PDF delle dieci competency question |

La scelta di articolare la pagina in sezioni brevi con indice risponde al requisito di progetto di **ridurre il testo** rispetto al sito attuale: ogni sezione è autonoma e raggiungibile direttamente, senza obbligare a una lettura sequenziale.

---

## 2. Schermate

### 2.1 L'ontologia delle opere d'arte
![Intro](Immagini/06-ontologia-intro.png)

<img width="1920" height="1080" alt="10" src="https://github.com/user-attachments/assets/09187bfa-88ad-40cb-baa0-84f5b0751867" />

Testo di apertura con il rimando alla sezione *Accesso ai dati*, che collega la comprensione del modello alla sua interrogazione pratica (US1.4).

### 2.2 Esplora il modello
![Esplora il modello](Immagini/07-ontologia-esplora.png)


<img width="1920" height="1080" alt="11" src="https://github.com/user-attachments/assets/505a412b-2904-4e2f-b829-e7af1e879f02" />


Diagramma semplificato: `Painting` come sottoclasse di `Artwork`, la catena `Artwork → CulturalInstituteOrSite → Place`, il ramo `TimeReference` con le tre sottoclassi `ExactDate`, `YearRange`, `CenturyReference`. È una rappresentazione volutamente ridotta; la versione completa di proprietà, tipi di dato e assiomi è scaricabile in formato Graffoo.

### 2.3 Legenda delle classi
![Legenda](Immagini/08-ontologia-legenda.png)

<img width="1920" height="1080" alt="12" src="https://github.com/user-attachments/assets/92ef2037-b036-4cbc-a9e3-564c54320aca" />


Tabella con, per ciascuna classe, che cosa rappresenta e da quale proprietà è identificata (`hasCode`, `hasISTATCode`, `hasEDTFValue`). Segue il box sul trattamento del tempo, che motiva la scelta di modellare il riferimento temporale come entità autonoma anziché come valore testuale.

### 2.4 A quali domande risponde
![Domande](Immagini/09-ontologia-domande.png)

<img width="1920" height="1080" alt="13" src="https://github.com/user-attachments/assets/b7db1002-2c16-452c-ae6c-b80ec2527e5f" />

<img width="1920" height="1080" alt="14" src="https://github.com/user-attachments/assets/8d6d8b65-c1f0-4801-895b-defe6ab72bcf" />

Le domande esposte sul sito sono riformulazioni divulgative delle competency question prodotte nella US2.2. La forma originale, con la variabile `X`, è corretta come artefatto di progettazione ma risulta incomprensibile a un visitatore: sul sito le domande sono quindi poste come se le formulerebbe l'utente, mentre l'elenco integrale in forma originale resta disponibile nel PDF scaricabile.

Le tre domande, nel loro insieme, percorrono ogni arco del diagramma semplificato: la specializzazione `Painting`/`Artwork` con le proprietà identificative, le relazioni `isHostedIn` e `isLocatedIn` con le rispettive inverse, e il ramo `hasTimeReference` con le tre sottoclassi.

### 2.5 Scarica il modello
![Scarica](Immagini/10-ontologia-scarica.png)


<img width="1920" height="1080" alt="15" src="https://github.com/user-attachments/assets/5a6389e9-ec35-42f9-9927-4b8654506cf6" />


Tre card di download (TTL, PNG, PDF) con formato e dimensione dichiarati, coerenti con il principio di pubblicazione in formato aperto e riutilizzabile.

---





## 4. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| Diagramma dell'ontologia con `ArtWork`, `Painting`, `CulturalInstituteOrSite`, `Place`, `TimeReference` | Sezione *Esplora il modello* |
| Legenda delle classi | Sezione *Esplora il modello*, tabella |
| Almeno 3 competency question documentate | Sezione *A quali domande risponde* (3 domande), più il PDF con le dieci CQ in *Scarica il modello* |
| Mockup della pagina Semantica | Cartella `Immagini/` |
| Dati/documenti: nessuno — riuso del Graffoo e delle CQ prodotti in US2.2 | Nessun nuovo artefatto di dati prodotto |

---

## 5. Deliverable

- Mockup della pagina Ontologia, cinque schermate (`Immagini/`)
- Testi definitivi delle tre domande e delle relative risposte (sezione 3 di questo documento)

Nessun nuovo dato o documento: il diagramma Graffoo e le competency question sono riusati dalla US2.2 (Sprint 1).

---

## 6. Relazione con altre User Story

- **US2.2 (Sprint 1)** — fornisce l'ontologia OWL, il diagramma Graffoo e le dieci competency question riusate in questa pagina.
- **US1.4** — la pagina *Accesso ai dati* espone le query SPARQL di esempio, derivate dalle stesse competency question. La separazione è voluta: la pagina Ontologia spiega **che cosa** il modello permette di sapere, la pagina Accesso ai dati mostra **come** interrogarlo. Le query non sono quindi duplicate in questa US, dove il campo Dati/documenti è esplicitamente vuoto.

