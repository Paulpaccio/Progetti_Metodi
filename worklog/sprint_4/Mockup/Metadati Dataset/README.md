# Scheda del dataset - US 1.6

Questa cartella documenta il mockup della scheda di dettaglio del dataset, realizzato per la User Story **US1.6 - Consultare i metadati per citazione, riuso e affidabilità**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come ricercatrice, voglio conoscere le informazioni principali sul dataset (titolare, editore, identificativo, licenza e data di aggiornamento), per citarlo correttamente, valutarne l'affidabilità e sapere se posso riutilizzarlo.**

## Contenuto della cartella

```
Mockup/Dataset/
├── README.md                          ← questo file
└── Immagini/
    ├── Dataset_Scheda_1.png           ← intestazione e metadati principali
    ├── Dataset_Scheda_2.png           ← metadati aggiuntivi e nota sul profilo DCAT-AP_IT
    └── Dataset_Scheda_3.png           ← le due distribuzioni (CSV, RDF/Turtle)
```

---

## 1. Che cosa mostra

![Intestazione e metadati principali](Immagini/Dataset_Scheda_1.png)

La pagina che si apre selezionando un dataset dall'elenco del catalogo. Riporta in forma leggibile i metadati DCAT-AP_IT prodotti in US2.4 e le due distribuzioni scaricabili.

La sezione risponde a tre esigenze distinte di chi consulta il catalogo: **citare** correttamente il dataset in una pubblicazione, **valutarne l'affidabilità** attraverso la data di ultimo aggiornamento, e **sapere se può essere riutilizzato** verificando la licenza.

![Metadati aggiuntivi](Immagini/Dataset_Scheda_2.png)

---

## 2. Copertura del test di accettazione

| Campo richiesto | Proprietà DCAT | Valore |
|---|---|---|
| Titolare | `dct:rightsHolder` | Ministero della Cultura |
| Editore | `dct:publisher` | Ministero della Cultura |
| Identificativo | `dct:identifier` | `m_bac:D.1` |
| Licenza | `dct:license` | CC BY 4.0 - URI dal vocabolario italiano |
| Data di aggiornamento | `dct:modified` | 25/08/2026 |

La tabella riporta inoltre tema, parole chiave, data di rilascio e lingua del dataset, anch'essi presenti nel file dei metadati. Ogni valore visualizzato corrisponde a una tripla di [`metadati_dcat-ap_it.ttl`](../../Metadati/metadati_dcat-ap_it.ttl), la pagina non introduce informazioni che il metadato non contenga.

---

## 3. Le distribuzioni

![Le due distribuzioni](Immagini/Dataset_Scheda_3.png)

Lo stesso dataset è offerto in CSV e in RDF/Turtle. La distinzione riflette il modello DCAT: un unico dataset e due **distribuzioni**, che ne sono l'incarnazione in formati diversi. È per questa ragione che licenza e formato sono dichiarati sulla distribuzione e non sul dataset, mentre titolare, tema e date valgono per entrambe.

---

## 4. Riuso

La pagina non produce nuovi metadati, visualizza il deliverable di **US2.4**. Le entità `Dataset`, `Distribution`, `Publisher` e `License` erano già state introdotte nel modello concettuale con **US1.2**, quindi questa user story non estende ulteriormente il modello.

---

## 5. Deliverable

- Mockup della scheda di dettaglio del dataset, tre schermate (`Immagini/`)

---

## 6. Relazione con altre User Story

Questa cartella fa parte dell'epic **Pubblicazione del dataset opere d'arte** (PM-7). Visualizza i metadati DCAT-AP_IT prodotti in **US2.4** e rimanda alle distribuzioni CSV e RDF/Turtle già scaricabili dalla pagina **Scarica Dati** (US1.5).
