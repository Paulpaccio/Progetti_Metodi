# Cancellazione su richiesta dell'interessato - US 3.4

Questa cartella contiene la procedura interna di cancellazione dei dati, realizzata per la User Story **US3.4 - Cancellazione su richiesta dell'interessato**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come funzionaria, voglio sapere come cancellare i dati di un utente che ne fa richiesta, per gestire correttamente l'esercizio dei suoi diritti.**


## Contenuto della cartella

```
Privacy/Cancellazione_Dati/
├── README.md                                  ← questo file
└── procedura-interna-cancellazione-dati.md    ← procedura interna di cancellazione
```

---

## 1. Procedura interna di cancellazione dei dati

Il file [`procedura-interna-cancellazione-dati.md`](procedura-interna-cancellazione-dati.md) è un **documento interno**, non destinato alla pubblicazione nell'informativa, che definisce le modalità operative con cui il Ministero dà seguito alle richieste di cancellazione (art. 17 GDPR) presentate tramite la pagina dei contatti. È diviso in cinque parti:

- **Scopo**: definire le modalità operative di risposta alle richieste di cancellazione.
- **Ricezione della richiesta**: arriva tramite i recapiti di Titolare o RPD, viene registrata e assegnata al funzionario addetto ai contatti.
- **Verifica**: il funzionario controlla l'identità del richiedente e l'assenza di obblighi di legge che impongano di conservare i dati (in tal caso la cancellazione è differita o rifiutata, con motivazione).
- **Esecuzione della cancellazione**: i dati (nome, cognome, email, contenuto del messaggio) sono cancellati in modo irreversibile, backup inclusi.
- **Tempi di risposta**: riscontro senza ingiustificato ritardo, entro un mese dalla richiesta, prorogabile di due mesi in casi complessi (art. 12, par. 3, GDPR).
- **Tracciabilità**: ogni richiesta e il suo esito sono registrati ai fini di accountability (art. 5, par. 2, GDPR), senza conservare i dati già cancellati.

---

## 2. Sezione "Diritti dell'interessato" nell'informativa

La sezione "Diritti dell'interessato" è presente nell'informativa privacy completa, [`Informativa_sul_trattamento_dei_dati_personali.pdf`](https://github.com/Paulpaccio/Progetti_Metodi/blob/main/worklog/Informativa_sul_trattamento_dei_dati_personali.pdf), sezione 11. Elenca i diritti esercitabili dall'interessato (accesso, rettifica, cancellazione, limitazione, opposizione), l'esclusione della portabilità, e le modalità di esercizio, con lo stesso termine di riscontro (un mese, prorogabile di due) usato nella procedura interna sopra descritta.

---

## 3. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| La procedura è documentata con tempi di risposta definiti | Sezione 1, "Tempi di risposta": entro un mese, prorogabile di due |
| L'informativa elenca tutti i diritti dell'interessato | Sezione 2, sezione 11 dell'informativa completa |
| Le modalità di esercizio | Sezione 2, e sezione 1 "Ricezione della richiesta" |

---

## 4. Deliverable

- Procedura interna di cancellazione, `procedura-interna-cancellazione-dati.md`
- Sezione "Diritti dell'interessato", presente nell'informativa privacy completa, sezione 11

---

## 5. Relazione con altre User Story

## 5. Relazione con altre User Story

Il mockup grafico di questa stessa sezione si trova in [`Mockup/Privacy/DirittiInteressato/`](../../Mockup/Privacy/DirittiInteressato/). Questa cartella fa parte della stessa epic di **US2.5**, **US3.1**, **US3.2** e **US3.3** (Privacy e protezione dei dati personali, PM-6).
