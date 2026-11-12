# Dalla tesi ai rigori ⚽

Gioco di rigori da browser: Bazoo, Tommy, Sicci e Cino contro Dello (col braccio ingessato).

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

Il gioco controlla il file all'apertura e ogni 20 secondi: la ricarica arriva da sola.
