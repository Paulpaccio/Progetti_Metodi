# Home page chiara - US 1.1

Questa cartella documenta il mockup della home page, realizzato per la User Story **US1.1 - Home page chiara**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come ricercatrice, voglio vedere una home page sintetica con la presentazione dell'iniziativa, per capire rapidamente cosa offre il sito senza leggere troppo testo.**

L'obiettivo è dare a chi arriva sul sito un'idea rapida di cosa offre dati.cultura.gov.it, senza dover leggere molto testo: un'introduzione breve e i collegamenti verso le sezioni principali.

## Contenuto della cartella

```
Mockup/HomePage/
├── README.md                          ← questo file
└── Immagini/
    ├── 01-home.png                    ← home page
    └── 02-menu-dropdown.png           ← home page, menu a tendina aperto (DA SISTEMARE)
```

---

## 1. Home page
![Home page](Immagini/01-home.png)

La home introduce il progetto con un titolo, una breve descrizione e due link di approfondimento. Sotto, due pulsanti principali portano subito a due azioni: **Catalogo e ricerca tra dataset** e **Accesso ai dati - API e SPARQL**. A destra due numeri riassuntivi (dataset pubblicati, entità collegate) della dimensione del progetto.

Il menu in alto (Il progetto, Dataset, Ontologia, Accesso ai dati, Contatti) resta sempre visibile e raggiunge tutte le sezioni del sito.

## 2. Menu a tendina aperto
![Menu a tendina](Immagini/02-menu-dropdown.png)

La voce **Accesso ai dati** del menu si apre in una tendina con due opzioni: **API e SPARQL** e **Scarica Dati**, per distinguere subito chi vuole interrogare i dati da chi vuole scaricarli. In alto a destra compare anche un riquadro per la scelta della lingua (Italiano/English).

---

## 3. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| La home mostra le sezioni principali: catalogo | Voce menu **Dataset**, pulsante **Catalogo e ricerca tra dataset** |
| La home mostra le sezioni principali: semantica | Voce menu **Ontologia** |
| La home mostra le sezioni principali: API/SPARQL | Voce menu **Accesso ai dati** (tendina), pulsante **Accesso ai dati - API e SPARQL** |
| La home mostra le sezioni principali: contatti | Voce menu **Contatti** |
| Testo introduttivo di poche righe | Titolo e breve descrizione |

---

## 4. Deliverable

- Mockup della home page, con menu di navigazione (`Immagini/`)

---

## 5. Relazione con altre User Story

Questa cartella fa parte dell'epic **Home page e presentazione dell'iniziativa** (PM-1). Il footer, visibile anche in questa pagina, è documentato a parte nella US1.8 - Informazioni utili e immediate, perché è un elemento condiviso da tutte le pagine del sito, non specifico della home. (DA RIVEDERE)
