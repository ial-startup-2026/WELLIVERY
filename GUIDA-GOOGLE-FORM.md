# Come ricevere gli ordini di Wellivery (gratis, senza carta)

Gli ordini arrivano in un **Google Form**; le risposte finiscono in un **Google Sheet** (un foglio di calcolo). Serve solo un account Google. Non serve nessuna carta di credito.

## 1. Crea il modulo
1. Vai su <https://forms.google.com> e clicca **Modulo vuoto**.
2. Dai un nome, per esempio "Ordini Wellivery".
3. Aggiungi queste **11 domande**, tutte di tipo **Risposta breve**, tranne "Ordine" che è **Paragrafo**. Scrivi i titoli esattamente così:

| Titolo della domanda | Tipo |
|---|---|
| Codice ordine | Risposta breve |
| Nome e cognome | Risposta breve |
| Telefono | Risposta breve |
| Azienda | Risposta breve |
| Piano / reparto | Risposta breve |
| Fascia di consegna | Risposta breve |
| Note o allergie | Paragrafo |
| Ordine | Paragrafo |
| Totale | Risposta breve |
| Data di consegna | Risposta breve |
| Consenso privacy | Risposta breve |

   Non usare menu a tendina né caselle: il sito scrive del testo libero, e Google rifiuta le risposte che non coincidono con le opzioni.
4. **Non** attivare "Limita a una risposta" e **non** attivare "Richiedi l'accesso": chi ordina non ha un account Google.

## 2. Collega il foglio delle risposte
Nel modulo apri la scheda **Risposte** e clicca **Collega a Fogli** (icona verde). Ogni ordine sarà una riga nuova.

## 3. Prendi i codici delle domande
1. Nel modulo clicca i tre puntini **⋮** in alto a destra → **Ottieni link precompilato**.
2. Compila **ogni domanda** con una parola facile da riconoscere (per esempio: "CODICE", "NOME", "TELEFONO"…), nello stesso ordine della tabella.
3. Clicca **Ottieni link**, poi **Copia link**.
4. Incolla il link a Claude: dal link si ricavano i codici `entry.123456789` di ogni domanda e l'indirizzo del modulo.

## 4. Collega il sito
Nel file `index.html`, cerca `var FORM` all'inizio dello script:
- in `action` metti l'indirizzo che finisce con `/formResponse`;
- in `campi` metti il codice `entry.…` di ogni domanda.

Appena `action` non è più vuoto, il sito esce dalla modalità dimostrativa e invia gli ordini davvero. Prima di pubblicare, compila anche l'email del referente in `PRIVACY`.

## 5. Prova
Fai un ordine di prova dal sito e controlla che compaia una riga nel foglio. Poi cancella la riga di prova.

## Cose da sapere
- Il foglio contiene nomi e telefoni: tienilo **privato** e condividilo solo con chi serve.
- Se cambi una domanda del modulo (la elimini o la rifai), il suo codice `entry.…` cambia: aggiorna `index.html`.
- Il sito non può leggere la risposta di Google: se la connessione manca, l'ordine non parte e il cliente vede un messaggio di errore. Se invece parte ma il modulo rifiuta i dati (per esempio una domanda diventata obbligatoria con regole strane), il cliente vede comunque "inviato". Per questo la prova al punto 5 è importante.
