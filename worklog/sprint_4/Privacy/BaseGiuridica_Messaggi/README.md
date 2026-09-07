# Base giuridica del trattamento dei messaggi -  US 3.2

Questa cartella contiene la nota di motivazione della base giuridica per il trattamento dei dati conferiti tramite la pagina dei contatti, realizzata per la User Story **US3.2 - Base giuridica del trattamento dei messaggi**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come funzionaria, voglio sapere su quale base è possibile trattare i dati contenuti nei messaggi, per gestire correttamente le richieste degli utenti e fornire informazioni chiare.**


## Contenuto della cartella

```
Privacy/BaseGiuridica_Messaggi/
├── README.md                                  ← questo file
└── nota-motivazione-base-giuridica-2.md       ← motivazione della base giuridica
```

---

## 1. Nota di motivazione della base giuridica

Il file [`nota-motivazione-base-giuridica-2.md`](nota-motivazione-base-giuridica-2.md) spiega perché il trattamento dei dati conferiti tramite la pagina dei contatti (nome, cognome, indirizzo e-mail, testo del messaggio) si fonda sull'**art. 6, par. 1, lett. e) del GDPR** (compito di interesse pubblico). A differenza dei dati di navigazione trattati in US2.5, qui il dato è conferito **volontariamente** dall'utente, non raccolto automaticamente. Per questo la nota dedica una spiegazione specifica al perché non si usa il consenso come base:

- **Perché non il consenso (art. 6.1.a)**: qui l'utente fornisce i dati volontariamente, ma per un ente pubblico il consenso non è una base sicura. Il Comitato europeo per la protezione dei dati (EDPB) lo sconsiglia quando c'è uno squilibrio di potere tra le parti, come tra cittadino e Ministero, il consenso rischia di non essere davvero libero (art. 4, n. 11, e considerando 43 GDPR). C'è anche un problema pratico, ovvero se la base fosse il consenso, l'utente potrebbe ritirarlo in qualsiasi momento (art. 7, par. 3). Ma il Ministero deve poter gestire una segnalazione fino in fondo, senza che la revoca dell'utente blocchi il processo a metà.
- **Perché non il legittimo interesse (art. 6.1.f)**: la legge lo esclude espressamente per le autorità pubbliche nell'esercizio dei loro compiti (art. 6, par. 1, ultimo periodo GDPR).
- **Fondamento normativo (art. 6, par. 3)**: la base è confermata da altre norme italiane, art. 2-ter del d.lgs. 196/2003, Codice dell'amministrazione digitale (d.lgs. 82/2005) e i compiti di comunicazione istituzionale del Ministero.
- **Conseguenza sui diritti**: l'interessato ha diritto di opposizione (art. 21), ma non di portabilità (art. 20), quest'ultima vale solo per trattamenti basati su consenso o contratto.

## 2. Sezione "Gestione delle segnalazioni" nell'informativa
Questa stessa sezione compare anche nell'informativa privacy completa del sito, [`Informativa_sul_trattamento_dei_dati_personali.pdf`](https://github.com/Paulpaccio/Progetti_Metodi/blob/main/worklog/Informativa_sul_trattamento_dei_dati_personali.pdf), al punto 4.1 "Gestione delle segnalazioni inviate tramite la pagina dei contatti". Mentre la nota di motivazione qui sopra spiega *perché* abbiamo scelto quella base giuridica, ripercorrendo le alternative scartate e il ragionamento dietro la decisione, il PDF riporta invece la versione finale, sintetica, così come apparirà pubblicata sul sito: 
- tre righe con **Dati trattati** (cosa raccogliamo),
- **Finalità** (perché lo facciamo),
- **Base giuridica** (su quale norma ci basiamo).

> I due documenti si completano a vicenda perchè uno mostra il lavoro fatto per arrivare alla decisione mentre l'altro il risultato che l'utente vedrà davvero.

---

## 3. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| La base giuridica è esplicitata nell'informativa | Sezione 4.1 dell'informativa completa (PDF) |
| È motivata coerentemente con la natura pubblica del titolare | Nota di motivazione, sezione 1 sopra, tutti e quattro i punti |

---

## 4. Deliverable

- Nota di motivazione della base giuridica, in questa cartella (`nota-motivazione-base-giuridica-2.md`)
- Sezione "Gestione delle segnalazioni inviate tramite la pagina dei contatti", presente nell'informativa privacy completa, sezione 4.1

---
## 5. Relazione con altre User Story

Il mockup grafico di questa stessa sezione si trova in [`Mockup/Privacy/GestioneSegnalazioni/`](../../Mockup/Privacy/GestioneSegnalazioni/). Questa cartella fa parte della stessa epic di **US2.5**, **US3.1**, **US3.3** e **US3.4** (Privacy e protezione dei dati personali, PM-6). 
