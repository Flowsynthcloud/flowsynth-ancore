# flowsynth-ancore

Ancore esterne della catena degli atti di FlowSynth (registro append-only `RATIFICHE.jsonl`, DR-060).

Ogni firma di un atto produce **un commit** che accoda una riga a `ancore.txt`:

```
<data dell'atto> · seq=<numero progressivo> · <hash della riga, sha256> · <DR> · chiave <identificativo a 16 cifre>
```

- Il commit e' creato via API con il token dell'account: **datato dal server** (`committer.date`), **non firmato** (`verification.reason = unsigned` — misurato il 2026-08-29: i commit via API non ricevono la firma web-flow di GitHub). L'autenticita' la danno il token dell'account e la protezione del ramo; nessuna chiave di firma locale, per scelta: non si crea una cosa nuova da custodire.
- Il ramo `main` e' protetto: nessun force-push, nessuna cancellazione.
- Qui non c'e' nulla di riservato: hash, numeri, date e identificativi pubblici delle chiavi (mai valori).
- Prima di ogni firma il referente legge **a occhio** l'ultima riga qui e la confronta con la testa attesa: la verifica esterna resta un gesto umano.
- Decisa nella seduta del 2026-08-29 (sostituisce l'ancora su carta, dichiarata irreperibile).
