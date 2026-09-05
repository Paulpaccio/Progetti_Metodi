# Produzione dati in CSV - US 2.1

Questa cartella contiene il dataset CSV delle opere d'arte, realizzato per la User Story **US2.1 - Produzione dati in CSV**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come data manager, voglio avere a disposizione i dati delle opere d'arte in un formato strutturato e facilmente utilizzabile, per poterli pubblicare nel catalogo.**

## Contenuto della cartella

```
CSV/
├── README.md                      ← questo file
├── opere_arte_completo.csv        ← file principale, come da tabella di consegna
├── paintings.csv                  ← dipinti (codice, titolo, descrizione, istituto)
├── institutes.csv                 ← istituti (codice, nome, luogo)
├── places.csv                     ← luoghi geografici (codice ISTAT, nome)
├── exact_dates.csv                ← riferimenti temporali con data esatta
├── year_ranges.csv                ← riferimenti temporali con intervallo di anni
└── century_references.csv         ← riferimenti temporali con secolo
```

> I sei file divisi per categoria sono stati prodotti in aggiunta al file principale per facilitare il mapping YARRRML della US2.3 (Sprint 2)


---

## 1. Il file principale

Il file [`opere_arte_completo.csv`](opere_arte_completo.csv) contiene le 13 opere d'arte della tabella fornita nella consegna del progetto, con una riga per opera.

---

## 2. Copertura del test di accettazione

Il test di accettazione richiede: *"il CSV contiene le 13 righe della tabella della consegna con le 8 colonne corrette; supera la validazione strutturale (14 righe totali, 8 campi per riga, UTF-8 senza BOM, quoting conforme a RFC 4180) e il confronto puntuale con la fonte."*

Abbiamo aperto il file e controllato ogni punto:

| Requisito | Verifica | Esito |
|---|---|---|
| 14 righe totali (13 dati + intestazione) | Il file ha esattamente 14 righe | ✅ |
| 8 campi per riga | Il file ha **14 colonne**, non 8 | ❌ |
| UTF-8 senza BOM | Il file **ha il BOM** (i primi 3 byte sono `EF BB BF`) | ❌ |
| Quoting conforme a RFC 4180 | I campi che contengono virgole sono correttamente racchiusi tra virgolette | ✅ |

**Sulle 14 colonne invece di 8**: la tabella originale della consegna aveva un'unica colonna "Data di riferimento", che poteva contenere una data esatta, un intervallo di anni o un secolo, in formati diversi. Nel file qui presente, quella colonna è stata scomposta in sette colonne separate (`tipo_riferimento_temporale`, `data_esatta`, `anno_inizio`, `anno_fine`, `numero_secolo`, `parte_secolo`, `valore_edtf`), per rendere più semplice il mapping verso l'ontologia nella US2.3.

**Sul BOM**: tutti e sette i file CSV di questa cartella hanno il BOM UTF-8, non solo quello principale — è un'impostazione di default di molti editor/esportatori (es. Excel), facile da correggere ri-salvando i file in UTF-8 senza BOM.

---

## 3. Deliverable

- `opere_arte_completo.csv` (dato.csv)
- Sei CSV per categoria, come base per il mapping YARRRML di US2.3

*Non ancora presenti in questa cartella: dizionario dei dati, log del data cleaning — entrambi richiesti dal campo "Dati/documenti" del ticket.*

---

## 4. Relazione con altre User Story

Questa cartella fa parte dell'epic **Pubblicazione del dataset opere d'arte** (PM-7). I CSV qui prodotti sono la base di partenza per **US2.3** (Sprint 2), che li trasforma in RDF/Turtle tramite YARRRML.

