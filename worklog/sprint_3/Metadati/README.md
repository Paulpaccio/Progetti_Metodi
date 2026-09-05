# Metadatazione DCAT-AP_IT - US 2.4

Questa cartella contiene i metadati del dataset delle opere d'arte, realizzati per la User Story **US2.4 - Metadatazione DCAT-AP_IT**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come data manager, voglio che il dataset sia descritto con metadati standardizzati, per renderlo facilmente reperibile, interoperabile e riutilizzabile.**

Il file [`metadati_dcat-ap_it.ttl`](metadati_dcat-ap_it.ttl) descrive il dataset delle opere d'arte secondo il profilo nazionale **DCAT-AP_IT**, adottato da AgID come specializzazione italiana di DCAT-AP europeo, a sua volta derivato dal vocabolario DCAT del W3C. Come fonte per la realizzazione è stata usata la [Guida Pratica DCAT-AP_IT](https://github.com/giorgialodi/Guida-pratica-DCAT-AP_IT) della professoressa Lodi, disponibile su GitHub.

## Contenuto della cartella

```
Metadati/
├── README.md                      ← questo file
└── metadati_dcat-ap_it.ttl        ← metadati del dataset in RDF/Turtle
```

---

## 1. Che cosa descrive

È utile distinguere due livelli. I file CSV (in [`sprint_1/CSV/`](../../sprint_1/CSV/)) e [`RDF_OpereArte_Onto-PM.ttl`](https://github.com/Paulpaccio/Progetti_Metodi/blob/main/worklog/sprint_2/Ontologia/RDF_OpereArte_Onto-PM.ttl) contengono i **dati**: le opere, gli istituti, i luoghi. Questo file contiene i **metadati** quindi descrive il dataset in quanto tale, chi lo pubblica, con quale licenza, in quali formati è disponibile, quando è stato aggiornato.

---

## 2. Struttura del file

| Classe | Che cosa rappresenta |
|---|---|
| `dcatapit:Catalog` | il catalogo nel suo insieme |
| `dcatapit:Dataset` | il dataset delle opere d'arte |
| `dcatapit:Distribution` | due distribuzioni, una per formato |
| `dcatapit:Agent` | titolare ed editore del dataset |
| `dcatapit:Organization` | punto di contatto, in formato vCard |
| `dcatapit:LicenseDocument` | descrizione della licenza applicata |

La distinzione fra **dataset** e **distribuzione** è il concetto strutturale di DCAT: il dataset è l'informazione, la distribuzione è la sua incarnazione in un formato concreto. Lo stesso contenuto esiste in CSV e in RDF/Turtle, ed è per questa ragione che licenza e formato sono dichiarati sulla distribuzione e non sul dataset.

Il dataset è identificato secondo la convenzione DCAT-AP_IT `codiceIPA:codiceDataset` (nel file: `m_bac:D.1`).

---

## 3. Vocabolari controllati

Un metadato non è testo libero, dove esiste un vocabolario controllato si impiega il suo URI. La ragione è la stessa che governa i linked data, una stringa come "Creative Commons Attribuzione 4.0" può essere scritta in decine di modi diversi e nessuna macchina può confrontarli, mentre un URI è univoco e globale.

| Elemento | Vocabolario | Valore |
|---|---|---|
| Tema | data-theme UE | `EDUC` |
| Licenza | licenze italiane | `A21_CCBY40` |
| Formati | file-type UE | `CSV`, `RDF_TURTLE` |
| Lingua e paese | authority UE | `ITA` |
| Frequenza di aggiornamento | frequency UE | `UNKNOWN` |
| Titolare ed editore | codice IPA | `m_bac` |

La licenza adottata è CC BY 4.0, con tipo `Attribution` dal vocabolario ADMS.

---

## 4. Nota di trasparenza sull'uso dell'IA

Per la stesura di questo deliverable è stato impiegato uno strumento di intelligenza artificiale (Claude), con il quale sono state discusse la struttura del profilo DCAT-AP_IT e la scelta dei vocabolari controllati, e sono state eseguite verifiche di conformità sul file prodotto.

Le verifiche hanno consentito di individuare e correggere quattro difformità:
1. l'URI della licenza, inizialmente tratto dal dominio Creative Commons anziché dal vocabolario delle licenze italiane;
2. gli indirizzi delle distribuzioni, che puntavano al sito reale del Ministero anziché al namespace del progetto;
3. un'incoerenza fra il formato dichiarato per la distribuzione RDF/Turtle e l'estensione del file indicato nel `downloadURL`;
4. alcune annotazioni provvisorie rimaste nel testo.

Ogni correzione è stata verificata dal gruppo prima di essere applicata, e il file finale è stato ricontrollato sintatticamente.

---
## 5. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| Tema Education con URI dal vocabolario controllato | `dcat:theme <.../data-theme/EDUC>` sul Dataset |
| Licenza aperta con URI dal vocabolario delle licenze italiane | `dct:license <.../licences/A21_CCBY40>` su entrambe le Distribution |
| Due distribuzioni, con formati CSV e RDF_TURTLE dal vocabolario europeo file type | `dcatapit:Distribution` per CSV (`dct:format .../file-type/CSV`) e per RDF/Turtle (`dct:format .../file-type/RDF_TURTLE`) |
| Titolare Ministero della Cultura (IPA `m_bac`) | `dct:rightsHolder` sul Dataset, che punta all'Agent con `dct:identifier "m_bac"` |
| Editore Ministero della Cultura | `dct:publisher`, stesso Agent, sia su Catalog sia su Dataset |
| `dct:modified` presente | `dct:modified "2026-08-25"^^xsd:date` sul Catalog e sul Dataset |

---

## 6. Deliverable

- Metadati DCAT-AP_IT del dataset (`metadati_dcat-ap_it.ttl`)

---

## 7. Relazione con altre User Story

Questa cartella fa parte dell'epic **Pubblicazione del dataset opere d'arte** (PM-7). Descrive le due distribuzioni prodotte in **US2.1** (CSV, Sprint 1) e **US2.3** (RDF/Turtle, Sprint 2), chiudendo il flusso CSV → ontologia → RDF/Turtle → metadatazione richiesto dalla consegna del progetto.
