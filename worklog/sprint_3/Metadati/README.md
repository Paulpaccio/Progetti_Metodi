# Metadatazione DCAT-AP_IT

Deliverable di **US2.4 — Metadatazione DCAT-AP_IT**.

Il file [`metadati_dcat-ap_it.ttl`](metadati_dcat-ap_it.ttl) descrive il dataset delle opere d'arte secondo il profilo nazionale **DCAT-AP_IT**, adottato da AgID come specializzazione italiana di DCAT-AP europeo, a sua volta derivato dal vocabolario DCAT del W3C.

---

## Che cosa descrive

È utile distinguere due livelli. I file CSV e `RDF_OpereArte_Onto-PM.ttl` contengono i **dati**: le opere, gli istituti, i luoghi. Questo file contiene i **metadati**: descrive il dataset in quanto tale — chi lo pubblica, con quale licenza, in quali formati è disponibile, quando è stato aggiornato.


---

## Struttura del file

| Classe | Che cosa rappresenta |
|---|---|
| `dcatapit:Catalog` | il catalogo nel suo insieme |
| `dcatapit:Dataset` | il dataset delle opere d'arte |
| `dcatapit:Distribution` | due distribuzioni, una per formato |
| `dcatapit:Agent` | titolare ed editore del dataset |
| `dcatapit:Organization` | punto di contatto, in formato vCard |
| `dcatapit:LicenseDocument` | descrizione della licenza applicata |

La distinzione fra **dataset** e **distribuzione** è il concetto strutturale di DCAT: il dataset è l'informazione, la distribuzione è la sua incarnazione in un formato concreto. Lo stesso contenuto esiste in CSV e in RDF/Turtle, ed è per questa ragione che licenza e formato sono dichiarati sulla distribuzione e non sul dataset.

Il dataset è identificato secondo la convenzione DCAT-AP_IT `codiceIPA:codiceDataset`.

---

## Vocabolari controllati

Un metadato non è testo libero: dove esiste un vocabolario controllato si impiega il suo URI. La ragione è la stessa che governa i linked data — una stringa come «Creative Commons Attribuzione 4.0» può essere scritta in decine di modi diversi e nessuna macchina può confrontarli, mentre un URI è univoco e globale.

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

## Nota di trasparenza sull'uso dell'IA

Per la stesura di questo deliverable è stato impiegato uno strumento di intelligenza artificiale (Claude), con il quale sono state discusse la struttura del profilo DCAT-AP_IT e la scelta dei vocabolari controllati, e sono state eseguite verifiche di conformità sul file prodotto.

Le verifiche hanno consentito di individuare e correggere quattro difformità:

1. l'URI della licenza, inizialmente tratto dal dominio Creative Commons anziché dal vocabolario delle licenze italiane;
2. gli indirizzi delle distribuzioni, che puntavano al sito reale del Ministero anziché al namespace del progetto;
3. un'incoerenza fra il formato dichiarato per la distribuzione RDF/Turtle e l'estensione del file indicato nel `downloadURL`;
4. alcune annotazioni provvisorie rimaste nel testo.

Ogni correzione è stata verificata dal gruppo prima di essere applicata, e il file finale è stato ricontrollato sintatticamente.
