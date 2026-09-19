# CT Scaligero · Preparazione fisica

Web app per smartphone a uso dei preparatori del Circolo Tennis Scaligero.
Mostra il **tema del giorno** secondo la rotazione settimanale, gli **esercizi per fascia d'età**
e il **calendario dei corsi Plus**.

---

## Sezioni

| Sezione | Cosa contiene |
|---|---|
| **OGGI** | Tema del giorno calcolato in automatico, esercizi del gruppo selezionato e corsi Plus della giornata |
| **ROTAZIONE** | Griglia delle 5 settimane (A–E) con la settimana in corso evidenziata |
| **PLUS** | Griglia settimanale dei corsi agonisti con la rotazione degli orari |
| **TEST** | Valutatore dei risultati (1 Ottimo → 4 Scarso) per sesso e fascia d'età, con tabella riferimenti |
| **LIVELLI** | Fasce scuola tennis (FITP) e categorie agonisti (Under) |

## Gruppi

- **Scuola tennis** — livelli FITP: Delfino 5-8, Cerbiatto 8-11, Coccodrillo 11-14, Canguro 14-18
- **Agonisti** — categorie: Under 12, Under 14, Under 16, Under 18

Stessi cinque macro argomenti per tutti (velocità, forza, resistenza, giochi, coordinazione/ritmo),
contenuti diversi per gruppo. La forza è sempre a corpo libero: gradoni, salite, lanci, circuiti.

## Rotazione settimanale

Ogni settimana contiene tutti e cinque i temi: cambia solo il giorno in cui cadono.
Chi frequenta una volta sola trova un tema diverso ogni settimana e in cinque settimane li ha fatti tutti.

La settimana (A–E) e' calcolata dalla data, partendo dal lunedi' di riferimento impostato in
`DEFAULT_ANCHOR` dentro `index.html` (`2026-10-05` = settimana A).
Se la rotazione si disallinea (pausa, festivita'), si corregge dall'app:
**Rotazione → Correggi la settimana in corso**. La scelta resta salvata sul telefono.

## Corsi Plus

Tre moduli al giorno che ruotano di orario: 15:30, 16:30, 17:30.
Il venerdi' alle 17:30 c'e' il calcettone. Forza: massimo 5 posti. Gli atleti si iscrivono dalla app Corsi Plus (https://bit.ly/PLUSSCALIGERO).

## Test

I valori di riferimento sono distinti per **maschi e femmine** su cinque fasce d'eta'
(8-9, 10-11, 12-13, 14-15, 16-18) e coincidono con quelli del file Excel su Drive.
Sono valori indicativi di partenza: dopo la prima campagna di test vanno ritarati sui dati reali del circolo.

---

## Pubblicare su Vercel

1. Crea un repository su GitHub e carica questi file (`index.html`, `README.md`).
2. Vai su [vercel.com](https://vercel.com) → **Add New… → Project** → importa il repository.
3. Framework Preset: **Other**. Nessun comando di build, nessuna cartella di output.
4. **Deploy**. Vercel restituisce il link pubblico.

Ogni modifica caricata su GitHub viene ripubblicata da Vercel in automatico.

## Aggiungere l'app alla schermata del telefono

- **iPhone**: apri il link in Safari → Condividi → *Aggiungi a Home*.
- **Android**: apri in Chrome → menu ⋮ → *Aggiungi a schermata Home*.

---

## Modificare i contenuti

Tutto e' in fondo a `index.html`, dentro il tag `<script>`:

| Cosa | Dove |
|---|---|
| Esercizi per tema e livello | oggetto `EX` |
| Visual training | oggetto `VISUAL` |
| Gruppi e fasce d'eta' | array `LEVELS` |
| Rotazione dei temi | oggetto `GRID` |
| Corsi Plus e orari | oggetti `PLUS` e `SLOTS` |
| Soglie dei test | oggetto `REF` (separato per `M` e `F`) |

Sono normali liste di testo: si modificano senza toccare il resto del codice.
