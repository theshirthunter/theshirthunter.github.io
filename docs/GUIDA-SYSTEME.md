# 365 MAGLIE — Setup con landing su misura + Systeme.io

Configurazione scelta: **landing page personalizzata** (il file `index.html` sportivo) ospitata gratis su **GitHub Pages**, collegata a **Systeme.io** come motore per i contatti e la sequenza automatica "una maglia al giorno".

Perché Systeme.io: piano gratuito con **email illimitate fino a 2.000 contatti** e **sequenze automatiche (drip) incluse anche nel free** — perfetto per i 365 giorni.

3 parti, in ordine:
1. **GitHub Pages** → pubblica la landing online
2. **Systeme.io: form** → colleghi il form della pagina ai tuoi contatti
3. **Systeme.io: Campaign drip** → la sequenza "una maglia al giorno per 365 giorni"

Tempo: ~40 minuti. Niente codice.

---

## PARTE 1 — Pubblicare la landing su GitHub Pages (account neutro)

> Obiettivo: un link tipo `https://365maglie.github.io` per la bio Instagram.

### 1.1 — Account GitHub neutro
1. Vai su **https://github.com/signup**
2. Usa un'**email neutra** (creane una nuova gratis, es. `365maglie@gmail.com`) così non compare il tuo nome.
3. Scegli uno **username = brand** (es. `365maglie`). ⚠️ Diventa parte dell'URL del sito.

### 1.2 — Crea il repository
1. In alto a destra **+** → **New repository**.
2. **Repository name**: esattamente `NOMEUTENTE.github.io` (es. `365maglie.github.io`).
3. **Public** → **Create repository**.

### 1.3 — Carica la pagina
1. **Add file** → **Upload files** → trascina **`index.html`** → **Commit changes**.

### 1.4 — Attiva Pages
1. **Settings** → **Pages** → Branch `main`, cartella `/ (root)` → **Save**.
2. Dopo 1-2 minuti compare: *"Your site is live at https://NOMEUTENTE.github.io"*.

✅ La landing è online. (Il form per ora mostra solo una conferma "demo": lo colleghiamo nella Parte 2.)

> 💡 Ogni volta che modifichi `index.html`, ricaricalo qui (Add file → Upload files → sovrascrivi → Commit).

---

## PARTE 2 — Collegare il form a Systeme.io

> Obiettivo: chi inserisce l'email sulla tua pagina finisce nei contatti Systeme.io.

### 2.1 — Account
1. Vai su **https://systeme.io** → crea l'account gratuito (piano **Free**).

### 2.2 — Crea il form (Inline form)
1. Menu **Funnels** → **Create** → tipo **Build an audience** (o simile) → crea un funnel chiamato *365 Maglie*.
2. Aggiungi uno step **Inline form** (categoria Opt-in) → scegli un template → **Edit page**.
3. Lascia i campi **Name** (Nome) e **Email**. Salva.
4. **Importante:** imposta che, all'iscrizione, al contatto venga assegnato un **tag** (es. `365maglie-iscritto`). Ci serve dopo per far partire la sequenza.
   - Lo trovi nelle impostazioni del form → *"After submission / Assign tag"*.

### 2.3 — Copia il codice HTML del form
1. Nel form clicca **Script** (o **Code**) → scegli l'opzione **"copy as HTML code"** (NON lo script JS, così possiamo dargli il nostro stile).
2. Copia tutto il codice.

### 2.4 — Incolla il form nella landing
1. Apri **`index.html`** con un editor di testo (Blocco note / TextEdit).
2. Trova questo blocco:
   ```
   <!-- ▼▼▼ INIZIO BLOCCO DA SOSTITUIRE CON IL FORM SYSTEME.IO ▼▼▼ -->
   <form id="signup" ...>
      ...
   </form>
   <!-- ▲▲▲ FINE BLOCCO DA SOSTITUIRE ▲▲▲ -->
   ```
3. **Cancella tutto ciò che sta tra i due commenti ▼▼▼ e ▲▲▲** e incolla al suo posto il codice HTML copiato da Systeme.io.
4. Salva il file e **ricaricalo su GitHub** (Parte 1.3).

> Il CSS della pagina dà automaticamente stile ai campi e al bottone del form Systeme, quindi resterà coerente con il look sportivo. Se qualche dettaglio non ti piace, scrivimi e lo sistemo.

### 2.5 — Link Instagram
Nel file trova `https://instagram.com/IL_TUO_AMICO` e mettici l'handle vero del tuo amico.

### 2.6 — Test
Apri il sito pubblicato, iscriviti con una tua email e verifica che il contatto compaia in Systeme.io (**Contacts**) con il tag `365maglie-iscritto`.

---

## PARTE 3 — La sequenza "una maglia al giorno per 365 giorni"

In Systeme.io la sequenza drip si chiama **Campaign**: una serie di email inviate a distanza di giorni dall'iscrizione. La facciamo partire in automatico con il tag della Parte 2.

### 3.1 — Crea la Campaign
1. Menu **Emails** → **Campaigns** → **Create**.
2. Nome: *365 Maglie — Sequenza*.
3. Aggiungi le email come **"Scheduled emails"**:
   - **Email 1 (Maglia #1):** invio dopo **0 giorni** (subito).
   - **Email 2 (Maglia #2):** dopo **1 giorno**.
   - **Email 3 (Maglia #3):** dopo **2 giorni**.
   - … e così via: ogni email a **+1 giorno** rispetto alla precedente, fino alla #365.
   > Il ritardo è calcolato dal momento dell'iscrizione: così ogni iscritto vive il suo viaggio di 365 giorni dal giorno zero.

### 3.2 — Fai partire la Campaign in automatico
1. Menu **Automations** → **Rules** → **Create**.
2. **Trigger:** *Tag added* → seleziona `365maglie-iscritto`.
3. **Action:** *Subscribe to campaign* → seleziona *365 Maglie — Sequenza*.

Così: appena qualcuno si iscrive dal form → riceve il tag → entra nella sequenza → parte la maglia #1.

### 3.3 — Consiglio pratico (importante)
- **Non scrivere 365 email prima di partire.** Prepara le prime **15-30 maglie**, lancia, e aggiungi le altre in coda con calma (la Campaign si modifica anche da attiva).
- Usa il foglio **`365-maglie-pianificazione.xlsx`** per tenere traccia (numero, squadra, particolare, stato). Le prime 3 le trovi già pronte in **`365-maglie-prime-3-email.md`**.
- Stai sempre **avanti di almeno 2 settimane** rispetto a chi è iscritto da più tempo.

### 3.4 — Attiva e prova
- Attiva la Campaign.
- Iscriviti dal sito con una tua email e verifica di ricevere la **Maglia #1**.

✅ Da qui la macchina gira da sola: tu aggiungi solo nuove maglie in coda.

---

## Checklist finale
- [ ] Account GitHub neutro (username = brand, email neutra)
- [ ] Repo `NOMEUTENTE.github.io` con `index.html` → Pages attivo → link funzionante
- [ ] Account Systeme.io (Free)
- [ ] Inline form con campi Nome + Email e **tag** `365maglie-iscritto`
- [ ] Codice HTML del form incollato in `index.html` (tra i commenti ▼/▲) e file ricaricato su GitHub
- [ ] Link Instagram aggiornato
- [ ] Campaign con email a +1 giorno (almeno le prime 15-30)
- [ ] Automation Rule: tag → Subscribe to campaign
- [ ] Test di iscrizione superato → ricevuta Maglia #1
- [ ] Link nella bio Instagram

## Note utili
- **Costi:** GitHub Pages gratis; Systeme.io gratis fino a **2.000 contatti** con email illimitate e drip incluso. Oltre i 2.000, si valuta un piano a pagamento.
- **GDPR:** Systeme.io gestisce link di disiscrizione e consenso. Valuta una mini privacy policy quando cresci.
- **Alternativa più rapida (meno custom):** in Parte 2.3 puoi scegliere lo **script JS** invece dell'HTML: il form si incolla com'è ma avrà lo stile di Systeme, non quello sportivo della pagina.
