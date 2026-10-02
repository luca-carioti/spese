# Spese (PWA locale)

App per tracciare le spese: conti, categorie, movimenti, import/export Excel.
I dati restano **solo nel browser del tuo telefono** (IndexedDB). Su GitHub va solo il codice.

## Pubblicazione su GitHub Pages (una volta sola)
1. Crea un account su github.com e un nuovo repository pubblico, es. `spese`.
2. Carica **tutti i file di questa cartella** (Add file → Upload files).
3. Settings → Pages → Source: *Deploy from a branch* → branch `main`, cartella `/ (root)` → Save.
4. Dopo 1-2 minuti l'app è su `https://TUOUSER.github.io/spese/`.

## Installazione su Android
1. Apri l'indirizzo con **Chrome**.
2. Menu ⋮ → **Installa app** (o *Aggiungi a schermata Home*).
3. Da ora funziona anche offline, come un'app normale.

## Formato Excel / Google Sheets
Un file `.xlsx` con 3 fogli: `Conti` (nome, saldo_iniziale), `Categorie` (nome, tipo),
`Movimenti` (data, tipo, importo, conto, categoria, nota). Vedi `modello_spese.xlsx`.
- data `AAAA-MM-GG`; tipo `Uscita`/`Entrata`; importo sempre positivo.
- Conti e categorie si collegano per nome; se mancano vengono creati.
- Google Sheets: carica il file su Drive e aprilo; per importare, *File → Scarica → Microsoft Excel (.xlsx)*.
- Import: **Sostituisci** (cancella tutto e carica il file) o **Aggiungi** (può duplicare movimenti già presenti).

## Importante
- Se cancelli i dati del browser/app **perdi tutto**: esporta ogni tanto (l'app te lo ricorda dopo 14 giorni).
- Dopo aver modificato i file, aumenta `V='spese-v1'` in `sw.js` (es. `v2`) per forzare l'aggiornamento.
- Prova in locale sul PC: `python3 -m http.server` nella cartella, poi apri `http://localhost:8000`.
