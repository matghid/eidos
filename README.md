# Eidos

**Eidos** è un'app web e desktop offline-first per scrivere note modulari e costruire board investigative con collegamenti visuali e semantici.

> Stato: prototipo V1 in sviluppo. Il repository è pubblico per documentare l'evoluzione del progetto, ma Eidos non è ancora pronto per un uso di produzione.

## Funzioni disponibili

- editor a blocchi con testo, titoli, liste, checklist, citazioni, codice, divisori e tabelle;
- immagini, allegati, link, note incorporate e contenitori a colonne;
- cartelle, tag, preferiti, cestino e operazioni multiple;
- board infinita con note, immagini, file, forme, cornici, etichette e tabelle;
- frecce con etichette modificabili e collegamenti tra gli elementi;
- salvataggio locale tramite IndexedDB;
- coda offline e sincronizzazione Supabase opzionale;
- tema chiaro, scuro e automatico;
- esportazione di note e board;
- app web/PWA e shell desktop Electron.

## Demo

La demo autonoma si trova in [`demo/index.html`](demo/index.html). Può essere scaricata e aperta direttamente nel browser, senza installare dipendenze.

Quando GitHub Pages sarà attivo, la demo sarà disponibile su:

**https://matghid.github.io/eidos/**

## Avvio locale

Requisiti consigliati:

- Node.js 22 LTS;
- npm 10 o successivo.

```bash
npm install
npm run dev
```

Vite mostrerà un indirizzo locale, normalmente `http://localhost:5173`.

## App desktop

```bash
npm run dev:desktop
```

Build desktop:

```bash
npm run dist:mac
npm run dist:win
```

Il DMG deve essere generato su macOS e l'installer Windows su Windows. Per la distribuzione pubblica su macOS serviranno firma e notarizzazione Apple.

## Build e controlli

```bash
npm run build
npm run lint
```

## Sincronizzazione Supabase

Eidos funziona anche senza configurazione cloud. Per attivare la sincronizzazione:

1. copia `.env.example` in `.env`;
2. crea un progetto Supabase;
3. esegui `supabase/schema.sql`;
4. inserisci URL e chiave anonima nel file `.env`;
5. configura i redirect URL per il magic link.

```env
VITE_SUPABASE_URL=https://YOUR_PROJECT.supabase.co
VITE_SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_KEY
```

Non pubblicare mai il file `.env` o chiavi riservate.

## Struttura principale

```text
src/components/       Interfaccia, editor e board
src/extensions/       Blocchi personalizzati Tiptap
src/lib/              Database, immagini, sincronizzazione e azioni
src/store/            Stato applicativo Zustand
electron/             Shell desktop
supabase/schema.sql   Schema cloud e policy
demo/                  Demo offline autonoma
```

## Roadmap

Le priorità successive includono:

- pagina libera per le singole note;
- cronologia completa e confronto tra versioni;
- gestione visuale dei conflitti di sincronizzazione;
- allegati cloud e miniature;
- audio, video, disegno a mano, timeline e mappe;
- condivisione tramite link;
- animazioni e microinterazioni moderne;
- test automatici e ottimizzazione del bundle.

La situazione tecnica dettagliata è descritta in [`HANDOFF.md`](HANDOFF.md).

## Tecnologie

React, TypeScript, Vite, Tiptap, React Flow, Dexie, Zustand, Supabase ed Electron.

## Autore

Mattia Ghidelli — [@matghid](https://github.com/matghid)

## Licenza

Al momento il progetto non è distribuito con una licenza open source. Tutti i diritti sono riservati.
