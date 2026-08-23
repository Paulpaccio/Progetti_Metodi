# Ontologia - Progetto SHELL

Questa cartella documenta il modello concettuale e l'ontologia OWL sviluppati per il sotto-progetto **dati.cultura** del progetto SHELL (rifacimento del catalogo [dati.cultura.gov.it](https://dati.cultura.gov.it/)), con particolare riferimento al dataset delle opere d'arte (dipinti) conservate in istituti e luoghi della cultura.

## Contenuto della cartella

```
ontologia/
├── README.md                         ← questo file
├── ontologia_dati_cultura.ttl        ← ontologia OWL (Turtle)
└── Diagrammi/
    ├── graffoo.drawio                ← disegno graffoo, sorgente editabile
    ├── graffoo.svg                   ← disegno graffoo, per la visualizzazione
    ├── er_diagram.drawio              ← schema E-R, sorgente editabile
    └── er_diagram.svg                 ← schema E-R, per la visualizzazione
```

I file relativi alla pubblicazione dei dati (CSV, RDF/Linked Open Data, mapping YARRRML, metadati DCAT-AP_IT) si trovano nelle cartelle dedicate del repository, non qui — questa cartella riguarda solo il modello concettuale e la sua formalizzazione.

---

## 1. Il modello concettuale in breve

L'ontologia descrive quattro concetti principali:

- **`Artwork`** — opera d'arte generica, con codice identificativo, titolo e descrizione; specializzata in **`Painting`** (dipinto), l'unico sottotipo popolato in questo progetto, che porta invece le relazioni verso l'istituto e verso il riferimento temporale
- **`CulturalInstituteOrSite`** — l'istituto o luogo della cultura che ospita un dipinto
- **`Place`** — il luogo geografico (comune) in cui si trova un istituto, identificato dal codice ISTAT
- **`TimeReference`** — il riferimento temporale di un dipinto, specializzato in tre sottoclassi **mutuamente disgiunte**: **`ExactDate`** (una data AAAA-MM-DD), **`YearRange`** (un intervallo tra due anni), **`CenturyReference`** (un secolo, con numero e parte opzionale: inizio/metà/fine/prima metà/seconda metà)

Il file [`RDF_Ontologia-PM.ttl`](./RDF_Ontologia-PM.ttl) contiene la formalizzazione completa: classi, object property, datatype property, disgiunzioni, chiavi (`owl:hasKey`) e proprietà inverse (`owl:inverseOf`).

Il disegno [`Diagrammi/Graffoo_Onto-PM.drawio.png`](./Diagrammi/Graffoo_Onto-PM.drawio.png) rappresenta graficamente questo stesso modello secondo la notazione Graffoo; lo schema [`Diagrammi/DiagrammaER_Onto-PM.drawio.png`](./Diagrammi/DiagrammaER_Onto-PM.drawio.png) ne dà una lettura più semplice, orientata alla progettazione dei dati piuttosto che alla formalizzazione OWL — coerentemente con quanto indicato nel testo del progetto ("il modello può essere espresso con uno schema E/R semplificato [...] da finalizzare poi in un'ontologia"), i due diagrammi descrivono lo **stesso** modello concettuale a due livelli di formalizzazione diversi, non due modelli distinti.

### Diagramma Entity-Relation
![E-R](Diagrammi/DiagrammaER_Onto-PM.drawio.png)

### Graffoo
![E-R](Diagrammi/Graffoo_Onto-PM.drawio.png)

---

## 2. Competency Question

Le CQ sono state riviste più volte nel corso dello sviluppo, mano a mano che il modello si affinava -- un percorso iterativo dichiarato esplicitamente qui invece che nascosto, perché riflette il reale processo di modellazione seguito.

| # | Competency Question | Cosa giustifica nel modello |
|---|---|---|
| 1 | Qual è il codice, il titolo e la descrizione di un'opera d'arte? | `hasCode`, `hasTitle`, `hasDescription` su `Artwork` |
| 2 | In quale istituto/luogo della cultura è conservato il dipinto X? | `isHostedIn` |
| 3 | In quale luogo geografico si trova l'istituto X? | `isLocatedIn` |
| 4 | Qual è il tempo di riferimento del dipinto X, sia esso una data esatta, un intervallo di anni o un secolo? | la gerarchia `TimeReference` / `ExactDate` / `YearRange` / `CenturyReference` e la loro disgiunzione |
| 5 | Quali opere d'arte hanno un riferimento temporale compreso in un dato intervallo di anni, indipendentemente dal formato originale del dato (data esatta, intervallo o secolo)? | `hasEDTFValue` senza un valore standardizzato comune alle tre sottoclassi, una query di questo tipo richiederebbe tre logiche di confronto diverse |
| 6 | Quali dipinti sono conservati presso l'istituto X? | `hosts` (inversa di `isHostedIn`) |
| 7 | Quali istituti della cultura si trovano nel luogo geografico X? | `hasCulturalInstitute` (inversa di `isLocatedIn`) |
| 8 | Dato un codice identificativo, esiste un'unica opera d'arte (o istituto, o luogo) a cui corrisponde? | `owl:hasKey` su `Artwork`, `CulturalInstituteOrSite`, `Place` |
| 9 | Per un'opera datata genericamente a un secolo, è nota anche la parte del secolo (inizio, metà, fine, prima/seconda metà) a cui risale? | `hasCenturyPart`, distinta da `hasCenturyNumber` |
| 10 | Quali sono il codice, il titolo e la descrizione di un'opera d'arte, indipendentemente dal suo tipo specifico? | `hasCode`, `hasTitle`, `hasDescription` su `Artwork` perché sono affini su tutte le opere d'arte e non sono esclusive della classe `Painting` (ad esempio un ipotetica classe `Sculpture` |

---

## 3. Scelte di design e criticità affrontate
Questa sezione riassume le principali decisioni di modellazione prese durante lo sviluppo dell’ontologia, con particolare attenzione alle esigenze reali del dataset fornito.

#### `Artwork` vs `Painting`: attributi generali e relazioni specifiche
Gli attributi comuni (`hasCode`, `hasTitle`, `hasDescription`) sono stati collocati su Artwork perché rappresentano caratteristiche condivise da qualunque opera d’arte. Le relazioni (`isHostedIn`, `hasTimeReference`) invece sono su `Painting` perché derivano direttamente dal contenuto del CSV, che contiene solo dipinti. Altri tipi di opere (come sculture o digital artworks) potrebbero non avere le stesse relazioni, quindi abbiamo modellato solo ciò che era realmente presente nei dati.

#### `Painting` come sottoclasse, non come tipo controllato
Abbiamo scelto `Painting` come sottoclasse di `Artwork` perché il dataset contiene esclusivamente dipinti. Un approccio alternativo (una singola classe con un tipo controllato, come in DCAT-AP o EDM) sarebbe più flessibile in un contesto con molti tipi diversi di opere, ma per questo progetto la sottoclasse è la soluzione più semplice e coerente con i dati disponibili.

#### `hasCode` e `hasName` con dominio “union”
Le proprietà `hasCode` e `hasName` sono condivise tra più classi tramite `owl:unionOf`, evitando duplicazioni inutili. Questa scelta mantiene il modello più pulito e riduce la ripetizione di proprietà equivalenti.

#### TimeReference suddiviso in tre sottoclassi disgiunte
Il dataset assegna a ogni dipinto un solo tipo di riferimento temporale: data esatta, intervallo di anni o secolo. Per riflettere questa struttura, `ExactDate`, `YearRange` e `CenturyReference` sono state rese disgiunte. Avevamo considerato anche la possibilità di ricavare automaticamente il secolo dalle date per uniformare i valori, ma l’idea è stata scartata per non introdurre logiche aggiuntive non richieste dal progetto.

#### `hasEDTFValue` per uniformare il confronto temporale
`hasEDTFValue` è stato aggiunto a `TimeReference` per fornire un valore temporale uniforme (EDTF) indipendentemente dal tipo di riferimento. Senza questa proprietà, confrontare date, intervalli e secoli richiederebbe tre logiche diverse. Il datatype è xsd:string perché EDTF non ha un tipo nativo in OWL.

#### Chiavi (`owl:hasKey`) per garantire l’univocità dei codici
Il progetto richiede che ogni codice identifichi uno e un solo soggetto (opera, istituto o luogo). Per questo motivo, `owl:hasKey` è stato dichiarato su `Artwork`, `CulturalInstituteOrSite` e `Place`, in modo da garantire l’univocità globale dei codici presenti nel dataset.

#### `hasCenturyPart` come stringa vincolata
I valori ammessi per `hasCenturyPart` sono stati modellati come stringhe vincolate tramite `owl:oneOf`. L’alternativa (usare individui dedicati) avrebbe evitato problemi di maiuscole/minuscole, ma avrebbe introdotto una classe e una proprietà aggiuntiva. Per semplicità, è stata scelta la versione a stringhe, con una convenzione documentata nel file [`RDF_Ontologia-PM.ttl`](./RDF_Ontologia-PM.ttl)

#### Costruzioni dei diagrammi e del graffoo - Fonti
Siccome ci si è imbattuti in situazioni non viste a lezione, sono state utilizzati due siti come riferimento
[Per costruzione Graffoo](https://essepuntato.it/graffoo/specification/)
[Per costruzione Diagramma E-R](https://www.slideserve.com/kaelem/progettazione-concettuale-il-modello-entit-relazioni)

---

## 4. Come consultare l'ontologia

Il file [`RDF_Ontologia-PM.ttl`](./RDF_Ontologia-PM.ttl) si apre direttamente in [Protégé](https://protege.stanford.edu/) (File → Open). Per verificare i vincoli (chiavi, disgiunzioni) è necessario lanciare un reasoner OWL2 DL — è stato verificato con HermiT.
