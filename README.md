# Wellivery

Wellivery è la pagina di prenotazione pranzi salutari con consegna in azienda: menu del giorno dopo, ricerca e filtri, carrello e modulo di consegna.

È un unico file statico (`index.html`), senza dipendenze da installare.

## Come modificare il menu
Apri `index.html` e cerca `MENU`, `SLOTS` e `CUTOFF` all'inizio dello script: lì ci sono piatti, prezzi, fasce di consegna e orario limite.

## Pubblicare con GitHub Pages
Settings → Pages → Branch `main` / cartella `/ (root)` → Save.

## Da collegare
L'invio reale degli ordini non è implementato: cerca il commento `invio reale dell'ordine` in `index.html`.
Il sito invia gli ordini a un Google Form (con risposte in un Google Sheet): segui `GUIDA-GOOGLE-FORM.md`. Finché `FORM.action` (all'inizio dello script) è vuoto, il sito resta in modalità dimostrativa e mostra l'avviso "Versione dimostrativa".

## Privacy
In fondo alla pagina c'è l'informativa privacy e nel modulo la casella da spuntare. Prima di pubblicare, compila l'email del referente in `PRIVACY` (all'inizio dello script). Il testo è una bozza da far controllare alla scuola.
