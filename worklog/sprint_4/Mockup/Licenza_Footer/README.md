# Licenza utilizzata nel footer e banner commenti - US 1.12 e US 1.13

Questa cartella documenta il mockup del footer aggiornato, che copre insieme due User Story: **US1.12 - Licenza utilizzata nel footer** e **US1.13 - Lasciare un commento**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura. Entrambe sono rappresentate dallo stesso screenshot, perché riguardano due elementi diversi dello stesso footer aggiornato.

> **US1.12 - Come ricercatrice, voglio vedere subito la licenza applicata ai dati del catalogo, per sapere a colpo d'occhio a quali condizioni posso riutilizzarli.**

> **US1.13 - Come utente, voglio poter trovare subito un link commenti perché io possa avvisare il Ministero di eventuali problemi o necessità.**


## Contenuto della cartella

```
Mockup/Licenza_Footer/
├── README.md               ← questo file
└── Immagini/
    └── Footer_V2.png       ← footer con indicazione della licenza e banner commenti
```

---

## 1. Il footer con la licenza

![Footer con licenza](Immagini/Footer_V2.png)

Il footer è organizzato in quattro colonne: 
- contatti istituzionali (logo, indirizzo, email, PEC),
- **Link utili** (amministrazione trasparente, privacy, note legali, accessibilità),
- una colonna dedicata alla **licenza** con il simbolo CC BY 4.0, la dicitura "i contenuti del sito sono rilasciati con licenza CC-BY 4.0" e il rimando alla pagina interna "Licenze e condizioni d'uso" per le eventuali eccezioni, 
- i collegamenti social.

> **Che cos'è la licenza CC BY 4.0**: è una licenza aperta che permette a chiunque di usare, copiare, modificare e persino vendere questi dati, anche per scopi commerciali. L'unica condizione è citare la fonte (il Ministero della Cultura). È lo standard consigliato per i dati della Pubblica Amministrazione italiana, ed è la stessa licenza già dichiarata nei metadati DCAT-AP_IT.

> Rispetto al footer di **US1.8** (Sprint 1), questa versione ("V2") aggiunge proprio la colonna della licenza che prima assente.

---
## 2. Il banner "lascia un commento"

In cima al footer è presente una fascia con l'invito a segnalare difficoltà o suggerimenti: *"Hai avuto qualche difficoltà o hai qualche suggerimento? Aiutaci a migliorare, lascia la tua opinione"*, con un link cliccabile su "lascia la tua opinione".

Questo banner dà a qualunque utente un modo immediato e sempre visibile per segnalare un problema al Ministero, senza dover prima navigare fino alla pagina Contatti.

---

## 3. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| US1.12 — Indicazione della licenza aperta applicata ai dati | Colonna "CC BY 4.0" nel footer, con simbolo e testo |
| US1.12 — Link alla licenza | Link "Licenze e condizioni d'uso" nella stessa colonna |
| US1.13 — Nel footer è presente un banner per invitare gli utenti a lasciare un commento | Fascia in cima al footer, "lascia la tua opinione" |

---

## 4. Deliverable

- Mockup del footer con licenza e banner commenti, una schermata (`Immagini/`)

---

## 5. Relazione con altre User Story

Questa cartella fa parte dell'epic **Home page e presentazione dell'iniziativa** (PM-1), la stessa di **US1.1** e **US1.8**. Aggiorna il footer già documentato in US1.8 (Sprint 1), aggiungendo sia la licenza già dichiarata nei metadati DCAT-AP_IT di **US2.4** (Sprint 3) sia il banner per i commenti degli utenti.
