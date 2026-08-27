# Accesso ai dati — SPARQL endpoint e query di esempio
Questa cartella documenta l'accesso al dataset RDF delle opere d'arte tramite endpoint SPARQL,
realizzato per la User Story **US1.4 — Accesso ai dati via API/SPARQL con esempi pronti**.

L'obiettivo è permettere a chi consulta i dati di interrogare il dataset senza dover costruire 
tutto da capo, con *query* pronte all'uso e un *endpoint* funzionante generato da GraphDB.

---

## 1. Endpoint SPARQL
I dati (ontologia + istanze) sono stati caricati sulla versione gratuita per computer di GraphDB
(Ontotext), uno dei triple store visti a lezione. Il repository creato si chiama *dati-cultura*
e contiene **337 statement** (ontologia + dati dei dipinti, istituti e luoghi).

**Endpoint SPARQL (query):**
http://localhost:7200/repositories/dati-cultura
> Nota: l'endpoint funziona solo in locale, sul computer di chi lo esegue.

---

## 2. Query di esempio
> **Nota**: prefisso comune a tutte le query
```PREFIX dco: <http://www.progetto-shell.org/dati-cultura-ontology#>```

### Query 1 — Catena dipinto → istituto → luogo (CQ 2, 3, 6, 7)
```
PREFIX dco: <http://www.progetto-shell.org/dati-cultura-ontology#> 
SELECT ?titoloOpera ?nomeIstituto ?nomeLuogo 
WHERE { 
?opera a dco:Painting ; dco:hasTitle 
?titoloOpera ; dco:isHostedIn ?istituto . 
?istituto dco:hasName ?nomeIstituto ; dco:isLocatedIn ?luogo . 
?luogo dco:hasName ?nomeLuogo . 
} 
ORDER BY ?nomeLuogo ?titoloOpera
```
