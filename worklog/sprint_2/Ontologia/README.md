# Trasformazione CSV → RDF/Turtle con YARRRML - US 2.3

Questa cartella contiene il modello concettuale, l'ontologia OWL, i CSV puliti, i mapping YARRRML e il grafo RDF/Turtle relativi al dataset dei dipinti del Ministero della Cultura, realizzati per la User Story **US2.3 - Trasformazione CSV → RDF/Turtle con YARRRML**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come data manager, voglio che i dati del CSV siano disponibili anche come linked open data, per facilitarne il riuso e l'integrazione con altre fonti.**

L'obiettivo è fornire una rappresentazione formale, interrogabile e interoperabile dei dati, conforme ai principi dei Linked Open Data.

## Contenuto della cartella

```
Ontologia/
├── README.md                          ← questo file
├── mapping.yarrrml.yml                ← script di mapping YARRRML
└── RDF_OpereArte_Onto-PM.ttl          ← grafo RDF/Turtle generato dal mapping
```
> I CSV di partenza sono il deliverable di **US2.1** (Sprint 1), si trovano in [`sprint_1/CSV/`](../../sprint_1/CSV/)
---

## 1. Mapping YARRRML

I mapping sono stati generati con [Matey/RML.io](https://rml.io/yarrrml/matey/#): lo script si trova in [`mapping.yarrrml.yml`](mapping.yarrrml.yml).

**Prefissi presenti:**
```
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix sd: <http://www.w3.org/ns/sparql-service-description#> .
@prefix dco: <http://www.progetto-shell.org/dati-cultura-ontology#> .
@prefix data: <http://www.progetto-shell.org/data/> .
```

---

## 2. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| Il Turtle rispetta classi e proprietà dell'ontologia | `RDF_OpereArte_Onto-PM.ttl` |
| È generato con YARRRML | [`mapping.yarrrml.yml`](mapping.yarrrml.yml) |

---

## 3. Deliverable

- `mapping.yarrrml.yml` (mapping YARRRML)
- `RDF_OpereArte_Onto-PM.ttl` (grafo RDF/Turtle)
- Sette file CSV in `CSVs/`

---

## 4. Relazione con altre User Story

Questa cartella fa parte dell'epic **Pubblicazione del dataset opere d'arte** (PM-7). Contiene l'intero flusso di modellazione e trasformazione dei dati, CSV → YARRRML → RDF/Turtle → Ontologia OWL, ed è la base su cui si costruiscono le fasi successive: pubblicazione dell'endpoint SPARQL (US1.4) e documentazione DCAT-AP-IT.
