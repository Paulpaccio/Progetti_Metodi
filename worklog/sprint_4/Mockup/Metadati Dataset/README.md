
# Scheda del dataset

Deliverable di **US1.6 — Consultare i metadati per citazione, riuso e affidabilità**.



## Che cosa mostra

La pagina che si apre selezionando un dataset dall'elenco del catalogo. Riporta in forma
leggibile i metadati DCAT-AP_IT prodotti in US2.4 e le due distribuzioni scaricabili.

La sezione risponde a tre esigenze distinte di chi consulta il catalogo: **citare**
correttamente il dataset in una pubblicazione, **valutarne l'affidabilità** attraverso la
data di ultimo aggiornamento, e **sapere se può essere riutilizzato** verificando la licenza.

## Copertura del test di accettazione

| Campo richiesto | Proprietà DCAT | Valore |
|---|---|---|
| Titolare | `dct:rightsHolder` | Ministero della Cultura |
| Editore | `dct:publisher` | Ministero della Cultura |
| Identificativo | `dct:identifier` | `m_bac:D.1` |
| Licenza | `dct:license` | CC BY 4.0 — URI dal vocabolario italiano |
| Data di aggiornamento | `dct:modified` | 25/08/2026 |

La tabella riporta inoltre tema, parole chiave, data di rilascio e lingua del dataset,
anch'essi presenti nel file dei metadati. Ogni valore visualizzato corrisponde a una tripla
di [`metadati_dcat-ap_it.ttl`](../../Metadati/metadati_dcat-ap_it.ttl): la pagina non
introduce informazioni che il metadato non contenga.


## Le distribuzioni

Lo stesso dataset è offerto in CSV e in RDF/Turtle. La distinzione riflette il modello DCAT:
un unico dataset e due **distribuzioni**, che ne sono l'incarnazione in formati diversi. È
per questa ragione che licenza e formato sono dichiarati sulla distribuzione e non sul
dataset, mentre titolare, tema e date valgono per entrambe.

## Riuso

La pagina non produce nuovi metadati: visualizza il deliverable di **US2.4**. Le entità
`Dataset`, `Distribution`, `Publisher` e `License` erano già state introdotte nel modello
concettuale con **US1.2**, quindi questa user story non estende ulteriormente il modello.
