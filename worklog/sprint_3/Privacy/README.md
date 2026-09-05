# Destinatari e accesso ai messaggi - US 3.3

Questa cartella contiene il testo della sezione dell'informativa privacy dedicata ai destinatari dei dati, realizzato per la User Story **US3.3 - Destinatari e accesso ai messaggi**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come funzionaria, voglio sapere quali risorse interne possono accedere ai messaggi ricevuti, per rispettare il principio di minimizzazione e gestire correttamente gli accessi.**

Questa sezione fa parte dell'**informativa privacy condivisa del sito**: insieme alle altre sezioni, compone l'informativa completa disponibile [`Informativa_sul_trattamento_dei_dati_personali.pdf`](https://github.com/Paulpaccio/Progetti_Metodi/blob/main/worklog/Informativa_sul_trattamento_dei_dati_personali.pdf).

## Contenuto della cartella

```
Privacy/
├── README.md                          ← questo file
└── sezione-destinatari-dati.md        ← testo della sezione, in Markdown
```

Il mockup grafico della stessa sezione si trova invece in [`Mockup/Privacy/`](../Mockup/Privacy/).

---

## 1. Testo della sezione

Il file [`sezione-destinatari-dati.md`](sezione-destinatari-dati.md) è diviso in due parti:
La schermata mostra la sezione "Destinatari dei dati" dell'informativa, in continuità con la pagina già presentata per la US2.5. È articolata in due blocchi:

- **Comunicazione a terzi**: i dati personali conferiti tramite la pagina dei contatti non sono diffusi né comunicati a soggetti terzi, salvo obblighi di legge o richieste dell'autorità giudiziaria o di altre autorità competenti.
- **Accesso interno ai messaggi**: in applicazione del principio di minimizzazione (art. 5, par. 1, lett. c GDPR), l'accesso è limitato al personale autorizzato e istruito ai sensi degli artt. 29 GDPR e 2-quaterdecies del d.lgs. 196/2003. Possono accedere ai messaggi solo tre ruoli:
  - **Funzionario addetto alla gestione dei contatti**: presa in carico, esame e riscontro delle segnalazioni; è l'unico ruolo che accede al contenuto dei messaggi nel merito.
  - **Personale tecnico/amministratore di sistema**: accesso limitato alle sole attività di manutenzione e sicurezza dei sistemi, senza trattamento nel merito del contenuto.
  - **Responsabile della protezione dei dati (RPD)**: accesso eventuale e circoscritto ai fini della verifica di conformità e della gestione delle istanze degli interessati.

Il file dichiara che la dashboard interna di gestione dei messaggi è accessibile unicamente al personale autorizzato, con credenziali individuali e profili di accesso.

---

## 2. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| L'elenco dei ruoli con accesso è dichiarato nell'informativa | Sezione "Accesso interno ai messaggi" del file, tre ruoli elencati |
| La dashboard interna è accessibile solo al personale autorizzato | Ultimo paragrafo del file |

---

## 3. Deliverable

- Sezione "destinatari dei dati" → questa cartella (`sezione-destinatari-dati.md`)
- Mockup pagina informativa, sezione destinatari → [`Mockup/Privacy/`](../Mockup/Privacy/), screenshot `06-privacy-destinatari-dati.png`

---

## 4. Relazione con altre User Story

Questa cartella fa parte della stessa epic di **US2.5** e delle altre user story sulla privacy (**Privacy e protezione dei dati personali**, PM-6). Il testo qui contenuto è una delle sezioni che, assemblate insieme, compongono l'informativa privacy completa del sito.
