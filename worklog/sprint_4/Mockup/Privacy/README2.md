# Cancellazione su richiesta dell'interessato - US 3.4

Questa cartella documenta la sezione dell'informativa privacy sui diritti dell'interessato, realizzata per la User Story **US3.4 - Cancellazione su richiesta dell'interessato**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come funzionaria, voglio sapere come cancellare i dati di un utente che ne fa richiesta, per gestire correttamente l'esercizio dei suoi diritti.**

## Contenuto della cartella

```
Mockup/Privacy/
├── README.md                                  ← questo file
└── Immagini/
    └── 09-diritti-interessato.png             ← sezione "Diritti dell'interessato"
```

Il file [`procedura-interna-cancellazione-dati.md`](../../Privacy/procedura-interna-cancellazione-dati.md) (procedura interna con i tempi di risposta) si trova invece in [`Privacy/`](../../Privacy/): questa cartella contiene solo il mockup grafico.

---

## 1. Diritti dell'interessato

![Diritti dell'interessato](Immagini/09-diritti-interessato.png)

La sezione dell'informativa che elenca i diritti dell'interessato è mostrata in un'unica schermata. Elenca i diritti esercitabili: **accesso**, **rettifica**, **cancellazione**, **limitazione** e **opposizione**, con la precisazione che il diritto alla **portabilità** non è applicabile, trattandosi di un trattamento fondato sul compito di interesse pubblico (coerente con la stessa base giuridica già usata in US2.5 e US3.2).

Indica anche le modalità di esercizio: la richiesta va rivolta al **Titolare** o al **Responsabile della protezione dei dati**, con riscontro entro un mese.

---

## 2. Copertura del test di accettazione


| Requisito | Dove è soddisfatto |
|---|---|
| La procedura è documentata con tempi di risposta definiti | [`procedura-interna-cancellazione-dati.md`](../../Privacy/procedura-interna-cancellazione-dati.md), in `Privacy/` |
| L'informativa elenca tutti i diritti dell'interessato | Schermata, cinque diritti elencati (accesso, rettifica, cancellazione, limitazione, opposizione) |
| Le modalità di esercizio | Schermata, richiesta al Titolare/RPD con riscontro entro un mese |

---

## 3. Deliverable

- Mockup della sezione "Diritti dell'interessato", una schermata (`Immagini/`)
- Procedura interna di cancellazione dei dati, in [`Privacy/procedura-interna-cancellazione-dati.md`](../../Privacy/)

---

## 4. Relazione con altre User Story

Questa cartella fa parte della stessa epic di **US2.5**, **US3.1**, **US3.2** e **US3.3** (Privacy e protezione dei dati personali, PM-6). La base giuridica citata (compito di interesse pubblico, art. 6 par. 1 lett. e GDPR) è la stessa già motivata in US2.5 e ripresa in US3.2: qui se ne trae la conseguenza pratica sui diritti esercitabili, in particolare l'esclusione della portabilità.
