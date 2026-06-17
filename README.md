# The Shirt Hunter — Landing newsletter

Sito statico della newsletter **The Shirt Hunter** ("una maglia al giorno per 365 giorni").
Una sola pagina (`index.html`), nessuna build, nessuna dipendenza. Pronto da aprire in VSCode.

## Struttura

```
theshirthunter-site/
├── index.html        ← LA PAGINA (tutto qui: HTML, CSS, animazioni)
├── README.md         ← questo file
├── .gitignore
├── .vscode/
│   └── extensions.json   ← consiglia l'estensione Live Server per l'anteprima
└── docs/                 ← materiali di lavoro (non fanno parte del sito)
    ├── GUIDA-SYSTEME.md         ← come collegare il form + drip 365 email
    ├── prime-3-email.md         ← bozze delle prime 3 email
    └── pianificazione-365-maglie.xlsx
```

## Come aprire e lavorare in VSCode

1. Apri VSCode → **File → Apri cartella…** → scegli `theshirthunter-site`.
2. (Consigliato) Installa l'estensione **Live Server** (VSCode te la suggerisce in automatico).
3. Anteprima: clic destro su `index.html` → **Open with Live Server**. La pagina si apre nel browser e si aggiorna ad ogni salvataggio — comodo per vedere subito le animazioni.
   - In alternativa: doppio clic su `index.html` per aprirla nel browser.

## Cosa modificare facilmente

Tutto è dentro `index.html`, in italiano e commentato. Punti utili:

- **Form Systeme.io** — cerca il blocco tra i commenti `▼▼▼ INIZIO BLOCCO DA SOSTITUIRE` e `▲▲▲ FINE BLOCCO`. Lì incolli il form HTML di Systeme.io (vedi `docs/GUIDA-SYSTEME.md`).
- **Logo** — al momento c'è un emblema disegnato in SVG nello stile del brand. Per usare il logo vero: metti il file (es. `logo.png`) nella cartella, e sostituisci il blocco `<svg ...>...</svg>` con `<img src="logo.png" alt="The Shirt Hunter" class="emblem">`.
- **Testi** — titolo, sottotitolo, "Come funziona", footer: tutto in chiaro nell'HTML.
- **Colori** — nella sezione `:root` in alto trovi le variabili (`--oro`, `--nero`, ecc.).

## Come pubblicare (GitHub Pages)

Il sito è già online su `theshirthunter.github.io`. Il repo è `theshirthunter/theshirthunter.github.io`.
Per aggiornarlo dal tuo VSCode:

**Se parti da zero (consigliato):** clona il repo già esistente, così VSCode è collegato a GitHub.
1. VSCode → **Source Control** (icona dei rami) → **Clone Repository** → `theshirthunter/theshirthunter.github.io`.
2. Copia dentro questo `index.html` (sostituendo quello vecchio) e la cartella `docs/` se vuoi tenerla nel repo.
3. In **Source Control**: scrivi un messaggio (es. "Aggiunte animazioni") → **Commit** → **Sync/Push**.
4. GitHub Pages ripubblica da solo in ~1 minuto.

`index.html` deve restare nella **root** del repo: è da lì che GitHub Pages serve il sito.

## Note

- Il form ora è in modalità demo (mostra una conferma ma non salva le email) finché non colleghi Systeme.io.
- La pagina rispetta `prefers-reduced-motion`: chi ha le animazioni ridotte vede la versione statica.
