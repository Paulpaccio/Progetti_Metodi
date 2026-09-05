# Trasformazione CSV → RDF/Turtle con YARRRML - US 2.3

Questa cartella contiene il mapping YARRRML e il grafo RDF/Turtle relativi al dataset dei dipinti del Ministero della Cultura, realizzati per la User Story **US2.3 - Trasformazione CSV → RDF/Turtle con YARRRML**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

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
> **Prefissi RDF**: in un file RDF, ogni classe o proprietà ha un indirizzo web completo come nome (es. `http://www.progetto-shell.org/dati-cultura-ontology#Painting`), troppo lungo da scrivere ogni volta. I prefissi sono delle scorciatoie e si dichiarano una volta sola all'inizio del file, poi si usano al posto dell'indirizzo intero. Qui ce ne sono cinque: `rdf` e `xsd` (i vocabolari di base del web semantico), `sd` (per i servizi SPARQL), `dco` (il vocabolario della nostra ontologia, con le classi e le proprietà che abbiamo definito noi, come `dco:hasTitle`) e `data` (i dati veri e propri: i singoli dipinti, istituti e luoghi).

---

## 2. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| Il Turtle rispetta classi e proprietà dell'ontologia | `RDF_OpereArte_Onto-PM.ttl` |
| È generato con YARRRML | [`mapping.yarrrml.yml`](mapping.yarrrml.yml), tramite Matey/RML.io |

---

## 3. Deliverable

- `mapping.yarrrml.yml` (mapping YARRRML)
- `RDF_OpereArte_Onto-PM.ttl` (grafo RDF/Turtle)


---

## 4. Relazione con altre User Story

Questa cartella fa parte dell'epic **Pubblicazione del dataset opere d'arte** (PM-7). Riceve in input i CSV prodotti in **US2.1** (Sprint 1) e li trasforma in RDF/Turtle secondo l'ontologia di **US2.2**. È a sua volta la base per la pubblicazione dell'endpoint SPARQL (**US1.4**) e per la documentazione DCAT-AP-IT (**US2.4**).
