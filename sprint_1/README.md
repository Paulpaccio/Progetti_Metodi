# Riepilogo Sprint 1 — Progetto SHELL (dati.cultura.gov.it)

Riepilogo delle attività e dei deliverable prodotti durante il primo sprint del progetto **SHELL**, sotto-progetto **dati.cultura**, relativo al rifacimento del catalogo open data del Ministero della Cultura ([dati.cultura.gov.it](https://dati.cultura.gov.it/)), realizzato nell'ambito del corso *Metodi informatici per la trasformazione digitale* (a.a. 2025/2026).

Repository: [Paulpaccio/Progetti_Metodi — sprint_1](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1)

---

## 1. Stato delle User Story (board Trello/Jira)

| US | Titolo | Priorità | Stato |
|---|---|---|---|
| US1.1 | Home page chiara | Medium | Approved |
| US1.8 | Informazioni utili e immediate (footer) | Low | Approved |
| US2.2 | Creazione dell'ontologia delle opere d'arte | Highest | Approved |
| US2.1 | Produzione dati utili e immediate in CSV | High | Completed *(non ancora approvata)* |

Non ci sono User Story rimaste in colonna **To do**.

> **Nota sulla US2.1:** la User Story è stata completata dopo la chiusura formale dello Sprint 1 e prima dell'inizio dello Sprint 2. Verrà quindi valutata e approvata in sede di discussione di gruppo - approvazione peraltro necessaria anche per poter avviare la **US2.3 (Trasformazione CSV → RDF/Turtle con YARRRML)**, che dipende dai dati prodotti in questa User Story.

---

## 2. Deliverable prodotti

### 2.1 Mockup dell'interfaccia (bassa fedeltà)
Cartella: [`sprint_1/Mockup`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/Mockup)

Mockup a bassa fedeltà del rifacimento del catalogo, relativo alle User Story su navigazione, home page e catalogo dataset. Comprende quattro schermate principali più il footer:

1. **Home page / landing** — claim del progetto, due call-to-action (*Catalogo e ricerca tra dataset*, *Accesso ai dati - API e SPARQL*), contatori di dataset pubblicati ed entità collegate, link di approfondimento.
2. **Menu di navigazione** — testata con le voci Il progetto, Dataset, Ontologia, Accesso ai dati, Contatti; il menu "Accesso ai dati" si espande in tendina (*API e SPARQL* / *Scarica dati*); selettore lingua ITA/ENG.
3. **Catalogo dataset** — dataset presentati come card (titolo, tag tematico, descrizione, link "esplora il dataset").
4. **Aggiornamenti e novità** — tre colonne: Nuovi dataset, Aggiornamenti, Comunicazione.
5. **Footer** (presente su tutte le pagine) — contatti istituzionali, link utili (amministrazione trasparente, privacy, note legali, accessibilità), collegamenti social.

Il mockup copre lo stato del prodotto per le US relative a home, navigazione e catalogo, e sarà esteso negli sprint successivi (es. pagina Contatti, scheda di dettaglio dataset, pagina Ontologia).

### 2.2 Ontologia OWL
Cartella: [`sprint_1/Ontologia`](https://github.com/Paulpaccio/Progetti_Metodi/tree/main/sprint_1/Ontologia)

Modello concettuale e ontologia OWL per il dataset delle opere d'arte (dipinti) conservate in istituti e luoghi della cultura.

**Modello concettuale** — quattro concetti principali:
- **`Artwork`** — opera d'arte generica (codice, titolo, descrizione); specializzata in **`Painting`** (unico sottotipo popolato), che porta le relazioni verso istituto e riferimento temporale.
- **`CulturalInstituteOrSite`** — istituto/luogo della cultura che ospita un dipinto.
- **`Place`** — luogo geografico (comune), identificato dal codice ISTAT.
- **`TimeReference`** — riferimento temporale, specializzato in tre sottoclassi mutuamente disgiunte: `ExactDate`, `YearRange`, `CenturyReference`.

Il file [`RDF_Ontologia-PM.ttl`](https://github.com/Paulpaccio/Progetti_Metodi/blob/main/sprint_1/Ontologia/RDF_Ontologia-PM.ttl.txt) contiene la formalizzazione completa (classi, object/datatype property, disgiunzioni, `owl:hasKey`, `owl:inverseOf`), verificata con il reasoner **HermiT** in Protégé.

Il modello è documentato anche graficamente in due diagrammi complementari (cartella `Diagrammi/`):
- **Diagramma E-R**, per una lettura orientata alla progettazione dei dati;
- **Diagramma Graffoo**, per la formalizzazione OWL.

**Competency Question (10)** — hanno guidato la modellazione e sono state riviste iterativamente durante lo sviluppo; coprono tra l'altro l'identificazione univoca di opere/istituti/luoghi (`owl:hasKey`), la navigazione delle relazioni dirette e inverse (`isHostedIn`/`hosts`, `isLocatedIn`/`hasCulturalInstitute`) e l'interrogazione uniforme dei riferimenti temporali indipendentemente dal formato originale (`hasEDTFValue`).

**Principali scelte di design:**
- attributi comuni su `Artwork`, relazioni specifiche su `Painting` (derivate dal contenuto reale del CSV);
- `Painting` come sottoclasse di `Artwork` anziché tipo controllato, coerentemente con un dataset che contiene solo dipinti;
- `hasCode`/`hasName` a dominio "union" (`owl:unionOf`) per evitare duplicazioni tra classi;
- tre sottoclassi di `TimeReference` rese disgiunte per riflettere il fatto che ogni dipinto ha un solo tipo di riferimento temporale;
- `hasEDTFValue` (xsd:string) per un confronto temporale uniforme tra data, intervallo e secolo;
- `owl:hasKey` su `Artwork`, `CulturalInstituteOrSite`, `Place` per garantire l'univocità dei codici;
- `hasCenturyPart` modellato come stringa vincolata (`owl:oneOf`) per semplicità, invece che con individui dedicati.

---

## 3. Collegamento con lo Sprint 2

L'approvazione della **US2.1 (Produzione dati in CSV)** è un prerequisito per l'avvio della **US2.3 (Trasformazione CSV → RDF/Turtle con YARRRML)**, che rappresenta quindi il naturale punto di partenza dello Sprint 2 una volta chiusa la discussione di gruppo sulla US2.1.

