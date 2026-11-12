# Dalla tesi ai rigori ⚽

Gioco di rigori da browser: ognuno crea il suo giocatore (nome, numero, colore) e tira contro Dello (col braccio ingessato). Se ti chiami Dello, scegli tu chi va in porta.

**Gioca qui:** https://theonlybzfx.github.io/dalla-tesi-ai-rigori/

- Modalità Soft / Medium / Hard
- Punti, scegli dove tirare (sinistra, centro, destra) e il portiere si tuffa a caso
- Ogni gol aumenta la vincita: incassa quando vuoi o arriva a 10 gol di fila per il premio massimo

Soldi finti, solo per divertimento.

## Ricariche (per Bazoo)

Quando un giocatore arriva a zero vede il suo **codice dispositivo** (es. `XE79N`) e il pulsante "Chiama Bazoo",
che apre WhatsApp con un messaggio già scritto (nome + codice).

Per ricaricarlo si aggiunge una voce in `ricariche.json` (ogni ricarica ha un `id` unico, così non viene mai applicata due volte):

```json
{
  "dispositivi": {
    "XE79N": { "nome": "Tommy", "ricariche": [ { "id": "r1", "importo": 100, "data": "2026-11-12" } ] }
  }
}
```

Si può ricaricare anche per **nome + numero di maglia** (utile se non si conosce il codice):

```json
"giocatori": {
  "tommy#10": { "ricariche": [ { "id": "tommy10-1", "importo": 100, "ts": "2026-11-12T16:30:00Z" } ] }
}
```

La ricarica per nome vale solo sui dispositivi già esistenti al momento `ts` (così un telefono nuovo con lo stesso nome non riceve le ricariche vecchie).

Il gioco controlla il file all'apertura e ogni 20 secondi: la ricarica arriva da sola.
