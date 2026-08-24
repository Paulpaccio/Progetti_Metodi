# Ontologia — Modello concettuale, CSV, YARRRML e RDF/Turtle

Questa cartella contiene il modello concettuale, l’ontologia OWL, i CSV puliti, i mapping YARRRML e il grafo RDF/Turtle relativi al dataset dei dipinti del Ministero della Cultura.
L’obiettivo è fornire una rappresentazione formale, interrogabile e interoperabile dei dati, conforme ai principi dei Linked Open Data.

--- 
## 1 CSVs
[I file CSVs](worklog/sprint_2/Ontologia/CSVsworklog/sprint_2/Ontologia/CSVs) contiene non solo il file CSV (in UTF-8) della tabella presente nelle indicazioni del progetto ([opere_arte_completo.csv](worklog/sprint_2/Ontologia/CSVs/opere_arte_completo.csv), ma ne sono inseriti altri sei divisi per categorie. Questo è stato fatto per facilitare la scrittura dell'RDF in YARRRML in quanto è stato garantire i valori diversi appartenenti alle diverse classi, specialmente per il padre (`TimeReference`) e le tre diverse sottoclassi `ExactDate`, `YearRange`, `CenturyReference`.

## Mapping YARRRML
I mapping sono stati generati con [Matey/RML.io](https://rml.io/yarrrml/matey/#) e potete trovare lo [script YARRRML qui](worklog/sprint_2/Ontologia/RDF_OpereArte_Onto-PM.ttl.txt.). 
**I prefissi presenti**
```
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix sd: <http://www.w3.org/ns/sparql-service-description#> .
@prefix dco: <http://www.progetto-shell.org/dati-cultura-ontology#> .
@prefix data: <http://www.progetto-shell.org/data/> .
```

## 2. Note
Questa cartella contiene l’intero flusso di modellazione e trasformazione dei dati:
`CSV → YARRRML → RDF/Turtle → Ontologia OWL`
ed è la base per le fasi successive di pubblicazione SPARQL e documentazione DCAT-AP-IT.
