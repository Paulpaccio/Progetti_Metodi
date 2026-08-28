
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


<img width="1920" height="1080" alt="Muckup Cultura" src="https://github.com/user-attachments/assets/c81f4db3-c3ed-440e-984c-1b9706cdbf1b" />

Cinque classi principali. Un dipinto è un caso particolare di opera d'arte, da cui eredita codice, titolo e descrizione; ogni dipinto è conservato in un istituto, che si trova in un comune, e ha un riferimento temporale che può assumere tre forme. Il diagramma qui riportato è una rappresentazione semplificata del modello: la versione completa, comprensiva di proprietà, tipi di dato e assiomi, è disponibile in formato Graffoo nella sezione Scarica il modello.

Diagramma semplificato: Diagramma semplificato: Painting come sottoclasse di Artwork, da cui eredita codice, titolo e descrizione; la catena Painting → CulturalInstituteOrSite → Place; il ramo TimeReference con le tre sottoclassi ExactDate, YearRange e CenturyReference.

### 2.3 Legenda delle classi
![Legenda](Immagini/08-ontologia-legenda.png)

<img width="1920" height="1080" alt="Muckup Cultura" src="https://github.com/user-attachments/assets/8f34fd67-55a8-46f9-89ba-21e81512ea1d" />



La sezione presenta la struttura dell'ontologia in forma tabellare: per ciascuna classe sono indicati che cosa rappresenta e da quale proprietà è identificata univocamente.
Le cinque classi principali — Artwork, Painting, CulturalInstituteOrSite, Place, TimeReference — sono seguite dalle tre sottoclassi di TimeReference.
Artwork porta le proprietà descrittive comuni a qualunque opera d'arte — codice identificativo, titolo, descrizione — mentre Painting, unico tipo di opera attualmente pubblicato, è la classe da cui partono le relazioni verso l'istituto conservatore e verso il riferimento temporale.

Il tempo viene trattato come entità autonoma anziché come valore testuale: nelle fonti di catalogazione la datazione compare in forme eterogenee — date complete, intervalli di anni, riferimenti di secolo con eventuali specificazioni di parte — che una singola proprietà testuale non consentirebbe di confrontare. Alle tre sottoclassi si affianca un valore espresso secondo lo standard EDTF, destinato all'interoperabilità con sistemi esterni.

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

