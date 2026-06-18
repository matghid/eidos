# Eidos — handoff tecnico

## Stato attuale

Eidos è una base V1 web + desktop, offline-first, pensata per note modulari e board investigative.

## Architettura prevista

- React + TypeScript + Vite;
- Tiptap per l'editor a blocchi;
- React Flow per la board infinita;
- Dexie/IndexedDB per il salvataggio locale;
- Zustand per lo stato applicativo;
- Supabase opzionale per autenticazione e sincronizzazione;
- Electron per la versione desktop.

## Funzioni V1

- note a blocchi;
- immagini, allegati, link, tabelle e colonne;
- cartelle, tag, preferiti e cestino;
- board infinita;
- note, immagini, file, forme, cornici ed etichette;
- collegamenti visuali e semantici;
- testo delle frecce modificabile direttamente dalla board;
- esportazione note e board;
- tema chiaro, scuro e automatico;
- funzionamento offline con sincronizzazione opzionale.

## Priorità successive

1. Pagina libera per le singole note.
2. Cronologia completa e confronto tra versioni.
3. Risoluzione visuale dei conflitti.
4. Storage cloud per allegati e miniature.
5. Audio, video, disegno a mano, timeline e mappe.
6. Condivisione tramite link.
7. Animazioni e microinterazioni moderne.
8. Test automatici e ottimizzazione del bundle.

## Comandi del progetto completo

```bash
npm install
npm run dev
npm run dev:desktop
npm run build
npm run dist:mac
npm run dist:win
```

## Sicurezza

Non pubblicare file `.env`, chiavi API, credenziali Supabase o dati reali degli utenti.
