# Privacy - protezione dei dati personali - US 2.5

Questa cartella contiene i deliverable testuali relativi alla protezione dei dati personali prodotti per la User Story **US2.5 - Informativa privacy: tracciamento del sito**, nell'ambito del progetto SHELL, sotto-progetto dati.cultura.

> **Come titolare del trattamento, voglio informare gli utenti su come vengono trattati i dati di navigazione, indicando finalità, tempi di conservazione e base giuridica, per garantire trasparenza e conformità alla normativa.**

## Contenuto della cartella

```
Privacy/
├── README.md                              ← questo file
└── nota-motivazione-base-giuridica.md     ← motivazione della base giuridica (art. 6.1.e GDPR)
```

Il mockup grafico della sezione (tre schermate) si trova invece in [`Mockup/Privacy/`](../Mockup/Privacy/), non qui: questa cartella contiene solo i testi.

---

## 1. Nota di motivazione della base giuridica

Il file [`nota-motivazione-base-giuridica.md`](nota-motivazione-base-giuridica.md) spiega perché il trattamento dei dati di navigazione (indirizzi IP, nomi a dominio, parametri tecnici della connessione) si fonda sull'**art. 6, par. 1, lett. e) del GDPR** (compito di interesse pubblico), invece che su altre basi giuridiche possibili:

- **Perché non il consenso (art. 6.1.a)**: i dati sono acquisiti automaticamente dai protocolli di Internet, non per scelta dell'utente; un consenso non sarebbe né libero né tecnicamente sensato. Non si tratta comunque di un trattamento che richiede consenso ai sensi dell'art. 122 del d.lgs. 196/2003, perché non c'è profilazione né uso di strumenti di terze parti.
- **Perché non il legittimo interesse (art. 6.1.f)**: il GDPR esclude esplicitamente questa base per i trattamenti delle autorità pubbliche nell'esecuzione dei propri compiti, e il Ministero della Cultura agisce proprio in quella veste.
- **Perché il compito di interesse pubblico (art. 6.1.e)**: rilevare statistiche sull'uso del sito e garantirne funzionamento e sicurezza rientra tra i compiti istituzionali del Ministero. La base è integrata dall'art. 2-ter del d.lgs. 196/2003, in combinato con il Codice dell'amministrazione digitale (d.lgs. 82/2005).

La nota chiude spiegando le conseguenze pratiche di questa scelta sui diritti dell'interessato: diritto di **opposizione** (art. 21 GDPR) sì, diritto alla **portabilità** (art. 20) no, perché quest'ultimo si applica solo ai trattamenti fondati su consenso o contratto.

---

## 2. Copertura del test di accettazione

| Requisito | Dove è soddisfatto |
|---|---|
| La sezione indica finalità, base giuridica e tempi di conservazione per il trattamento dei dati di navigazione | Mockup in [`Mockup/Privacy/`](../Mockup/Privacy/) |
| La base giuridica è motivata con riferimento all'art. 6 GDPR e alla natura pubblica del titolare | [`nota-motivazione-base-giuridica.md`](nota-motivazione-base-giuridica.md), in questa cartella |

---

## 3. Deliverable

- Nota di motivazione della base giuridica → questa cartella
- Mockup pagina informativa, sezione dati di navigazione (tre schermate) → [`Mockup/Privacy/Immagini/`](../Mockup/Privacy/Immagini/): `05-privacy-dati-navigazione.png`, `05.1-privacy-dati-navigazione.png`, `05.2-privacy-dati-navigazione.png`

---

## 4. Relazione con altre User Story

US2.5 fa parte della stessa epic di US3.1-US3.4 (Privacy e protezione dei dati personali, PM-6), ma riguarda una cosa diversa: qui si tratta dei dati di navigazione raccolti automaticamente dal sito, mentre le altre riguardano i messaggi che gli utenti inviano dalla pagina Contatti.
