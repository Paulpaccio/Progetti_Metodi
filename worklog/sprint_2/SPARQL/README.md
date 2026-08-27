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
`http://localhost:7200/repositories/dati-cultura`
> Nota: l'endpoint funziona solo in locale, sul computer di chi lo esegue.

---

## 2. Query di esempio
> **Nota**: prefisso comune a tutte le query
```PREFIX dco: <http://www.progetto-shell.org/dati-cultura-ontology#>```

### Query 1 — Catena dipinto → istituto → luogo (CQ 2, 3, 6, 7)
> CQ2: "In quale istituto/luogo della cultura è conservato il dipinto X?"
> 
> CQ3: "In quale luogo geografico si trova l'istituto X?"
> 
> CQ6: "Quali dipinti sono conservati presso l'istituto X?"
> 
> CQ7: "Quali istituti della cultura si trovano nel luogo geografico X?"
```sparql
SELECT ?titoloOpera ?nomeIstituto ?nomeLuogo 
WHERE { 
?opera a dco:Painting ; dco:hasTitle 
?titoloOpera ; dco:isHostedIn ?istituto . 
?istituto dco:hasName ?nomeIstituto ; dco:isLocatedIn ?luogo . 
?luogo dco:hasName ?nomeLuogo . 
} 
ORDER BY ?nomeLuogo ?titoloOpera
```
![Risultati Query 1](Immagini/query1-risultati.png)
> **Risultato verificato**: 13 righe, una per ciascun dipinto del dataset, con istituto e luogo
correttamente collegati (es. "Adorazione dei Magi" → "Casa Privata" → "Omegna").

### Query 2 — Dipinti datati per intervallo di secoli (CQ 4, 5, 9)
> CQ4: "Qual è il tempo di riferimento del dipinto X, sia esso una data esatta, un intervallo di anni o un secolo?"
> 
> CQ5: "Quali opere d'arte hanno un riferimento temporale compreso in un dato intervallo di anni, indipendentemente dal formato originale del dato?"
> 
> CQ9: "Per un'opera datata genericamente a un secolo, è nota anche la parte del secolo a cui risale?"
```sparql
SELECT ?titoloOpera ?secolo ?partesecolo
WHERE {
  ?opera a dco:Painting ;
         dco:hasTitle ?titoloOpera ;
         dco:hasTimeReference ?tempo .
  ?tempo a dco:CenturyReference ;
         dco:hasCenturyNumber ?secolo .
  OPTIONAL { ?tempo dco:hasCenturyPart ?partesecolo }
  FILTER (?secolo >= 17 && ?secolo <= 19)
}
ORDER BY ?secolo
```
![Risultati Query 2](Immagini/query2-risultati.png)
> **Risultato verificato**: 7 righe (5 dipinti del XVII secolo, 2 del XIX secolo); i dipinti
datati al XX secolo sono correttamente esclusi dal filtro.

---
## 3. Come provare le query

### Metodo 1 — Da browser, con l'interfaccia grafica (Workbench)
Aprendo un browser qualsiasi (Safari, Chrome, ecc.) e navigando all'indirizzo
`http://localhost:7200/sparql?repositoryId=dati-cultura` 
si apre l'editor SPARQL del Workbench di GraphDB, dove il testo di una query può essere incollato in un apposito
riquadro. Una volta eseguita, i risultati compaiono in una tabella, come nello screenshot
mostrato sopra per la Query 1.

### Metodo 2 — Come chiamata API (esempio via URL)

Questo secondo metodo mostra come un altro programma, anziché una persona, potrebbe leggere
i nostri dati senza passare dall'interfaccia grafica del Workbench. 
A differenza del Metodo 1, dove l'indirizzo e la query sono due cose separate (prima si apre
la pagina, poi si scrive la query in un riquadro), qui l'intero indirizzo e la
query scelta, vanno scritti tutti insieme e incollati direttamente nella barra degli indirizzi del
browser. Un esempio pronto, che restituisce le prime cinque triple del dataset, è il seguente:
`[http://localhost:7200/repositories/dati-cultura?query=PREFIX%20dco%3A%20%3Chttp%3A%2F%2Fwww.progetto-shell.org%2F
dati-cultura-ontology%23%3E%20SELECT%20%3FtitoloOpera%20%3FnomeIstituto%20WHERE%20%7B%20%3Fopera%20a%20dco%3APainting%
20%3B%20dco%3AhasTitle%20%3FtitoloOpera%20%3B%20dco%3AisHostedIn%20%3Fistituto%20.%20%3Fistituto%20dco%3AhasName%20%3F
nomeIstituto%20%7D%20LIMIT%2010](http://localhost:7200/repositories/dati-cultura?query=SELECT%20*%20WHERE%20%7B%20%3Fs%20%3Fp%20%3Fo%20%7D%20LIMIT%205)`

> **Nota**: L'indirizzo è pieno di simboli `%` perché un URL non può contenere direttamente certi
caratteri, come gli spazi o le parentesi graffe: vanno tradotti in un codice speciale,
chiamato *URL encoding*.
> 
> **Nota sulla trasparenza**: per la sezione sopra è stato utilizzato uno strumento di IA (Claude) per
costruire questo esempio, verificandone poi il funzionamento nel browser:
> 
> [esempio-risposta-api.srx](Immagini/esempio-risposta-api.srx)
