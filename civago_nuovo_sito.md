# Civago — Proposta Nuovo Sito Web
> Documento di design e architettura — maggio 2026

---

## OBIETTIVO

Trasformare un sito CMS vecchio stile in un **portale moderno, veloce e mobile-first** che:
- Preservi e valorizzi tutto il patrimonio culturale accumulato
- Attragga turisti e villeggianti con informazioni pratiche
- Sia facile da aggiornare dalla comunità locale
- Duri anni senza manutenzione tecnica pesante

---

## TECNOLOGIA CONSIGLIATA

### Opzione A — **Astro + Netlify/Cloudflare Pages** ✅ *Consigliata*
- Sito statico generato da file Markdown/MDX
- Velocità massima, SEO perfetto, zero costi hosting
- I contenuti si aggiornano modificando file di testo (o tramite CMS headless gratuito come Decap CMS)
- Nessun database da gestire

### Opzione B — **WordPress con tema moderno**
- Più familiare per chi ha già gestito siti
- Plugin per gallerie, news, mappe
- Richiede hosting a pagamento (~5–10€/mese) e aggiornamenti periodici

### Opzione C — **Notion + Super.so**
- Editing ultra-semplice (come un documento)
- Meno flessibilità grafica
- Buono se la priorità è che chiunque possa aggiornare

---

## NUOVA ARCHITETTURA DEL SITO

### Prima (sito attuale) — struttura piatta
20 voci di menu tutte allo stesso livello, nessuna gerarchia, navigazione confusa.

### Dopo (proposta) — struttura a 5 sezioni principali

```
civago.it/
│
├── 🏔️  SCOPRI CIVAGO
│   ├── Il paese (storia, geografia, popolazione)
│   ├── Come arrivare + mappa interattiva
│   ├── Dormire e mangiare
│   └── Webcam live della piazza
│
├── 🥾  ESPLORA
│   ├── 13 sentieri e borgate (con mappa interattiva + GPX download)
│   ├── Da fare, da vedere, da sapere
│   ├── Rifugi e punti di interesse
│   └── Area di pesca Torrente Dolo
│
├── 🏺  CULTURA E TRADIZIONI
│   ├── Storia di Civago (Cafari + Romano Marchi + documenti)
│   ├── Tradizioni popolari (Maggio, Carnevale, ecc.)
│   ├── Ricettario (19 ricette con foto)
│   ├── Dizionario dialettale
│   └── Poesie (Ralfo Monti + altri)
│
├── 📸  ARCHIVIO FOTOGRAFICO
│   ├── Gallerie fotografiche (21 gallerie)
│   ├── Civago in cartolina (1929–1955)
│   ├── Amarcord (foto storiche comunità)
│   ├── Le foto di Don Paolo (~500 immagini)
│   └── Le tue foto (contributi della comunità)
│
└── 📢  COMUNITÀ
    ├── News ed eventi
    ├── Calendario eventi
    ├── Link utili
    └── Contatti
```

---

## NUOVE IDEE E FUNZIONALITÀ

### 🗺️ Mappa interattiva dei sentieri
- Visualizzazione OpenStreetMap (gratuita) con i 13 percorsi tracciati
- Click su ogni tappa → popup con descrizione e foto
- Download file GPX per ogni sentiero (da creare con app tipo Komoot)
- Mobile-friendly per chi cammina

### 📅 Calendario eventi
- Sezione news trasformata in calendario visuale
- Festa del Fungo, Castagnata, Mangialonga, eventi estivi
- Possibilità di aggiungere eventi da parte dei gestori
- Widget embed da Google Calendar o iCal

### 🌡️ Widget meteo + webcam
- Meteo locale (integrazione free con OpenWeatherMap o Yr.no)
- Webcam della piazza già esistente — da integrare nella homepage
- Eventualmente una seconda webcam sul monte

### 🍄 Ricettario moderno
- Ogni ricetta con: foto, ingredienti evidenziati, procedimento passo-passo
- Tag: dolce/salato, castagne, forno a legna, tradizionale, ecc.
- Funzione "stampa ricetta" ottimizzata
- Possibilità di aggiungere commenti/varianti dalla comunità

### 📖 Dizionario dialettale interattivo
- Ricerca per lettera o parola (filtro JS lato client)
- Possibilità di aggiungere nuovi termini con moderazione
- Audio pronuncia (opzionale, se qualcuno vuole registrare)

### 🎵 Poesie con ascolto
- Testo delle poesie con impaginazione tipografica curata
- Tag: dialetto / italiano, tema, autore
- Audio opzionale (lettura delle poesie — già esiste una registrazione con Mara Radeghieri)

### 📸 Galleria fotografica moderna
- Lightbox responsive (senza plugin pesanti)
- Filtro per anno, autore, tema
- Modalità "Amarcord": timeline cronologica dal 1920 ad oggi
- "Le tue foto": upload guidato con moderazione

### 🔍 Ricerca globale
- Barra di ricerca che copre tutti i contenuti (news, ricette, poesie, storia)
- Implementabile con Pagefind (gratuito, funziona su siti statici)

### 🌍 Mappa dei Civaghesi nel mondo
- Sezione "In America voglio andar" (già esistente nelle ricerche di Romano Marchi)
- Mappa interattiva con punti dove si sono trasferiti gli emigrati
- Storie personali di emigrazione

### 📱 App-like su mobile
- PWA (Progressive Web App): si può "installare" sul telefono
- Funziona parzialmente offline (utile in montagna con segnale debole)
- Notifiche push per eventi (opzionale)

---

## DESIGN VISIVO

### Palette colori suggerita
```
Verde bosco:     #2D5016  (testo su chiaro, elementi primari)
Verde salvia:    #6B8F3C  (accenti, bottoni)
Beige naturale:  #F5F0E8  (sfondo principale)
Marrone terra:   #8B6914  (titoli, elementi decorativi)
Bianco neve:     #FAFAFA  (card, sfondo secondario)
```

### Tipografia
- **Titoli:** Playfair Display o Lora (serif elegante, senso di tradizione)
- **Corpo:** Inter o Source Sans Pro (leggibilità moderna)
- **Dialetto/poesie:** Georgia o Garamond (calore letterario)

### Hero della homepage
- Foto a schermo intero della valle o del paese nevoso
- Titolo: *"Civago — la perla verde dell'Alto Appennino"*
- Sottotitolo con stagione attuale
- 3 CTA rapidi: [Esplora i sentieri] [Guarda la webcam] [Scopri la storia]

### Card modulari
- Ogni contenuto (ricetta, poesia, articolo) presentato come card
- Immagine, titolo, breve estratto, link "leggi tutto"
- Griglia responsive (1 colonna mobile, 2-3 colonne desktop)

---

## STRUTTURA HOMEPAGE

```
┌─────────────────────────────────────┐
│  HERO — foto panoramica + titolo    │
│  webcam live (piccola)              │
└─────────────────────────────────────┘
┌──────────┬──────────┬───────────────┐
│ Meteo    │ Prossimo │ Ultima news   │
│ attuale  │ evento   │               │
└──────────┴──────────┴───────────────┘
┌─────────────────────────────────────┐
│  SEZIONE: Scopri Civago             │
│  Testo introduttivo + 3 card:       │
│  [Il Paese] [Come arrivare] [Dormi] │
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│  SEZIONE: Esplora                   │
│  Mappa mini + 3 sentieri in evidenza│
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│  SEZIONE: Cultura                   │
│  Ricetta del mese + Poesia + Storia │
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│  SEZIONE: Galleria in evidenza      │
│  4-6 foto recenti in griglia        │
└─────────────────────────────────────┘
┌─────────────────────────────────────┐
│  FOOTER                             │
│  Link, contatti, info              │
└─────────────────────────────────────┘
```

---

## PIANO DI MIGRAZIONE

### Fase 1 — Struttura e contenuti base (1–2 settimane)
- [ ] Setup repository (GitHub) + hosting (Netlify gratis)
- [ ] Importare tutti i testi dal file `civago_contenuti.md`
- [ ] Homepage con hero, meteo, webcam
- [ ] Sezione "Il paese" e "Scopri Civago"
- [ ] Ricettario completo (19 ricette)

### Fase 2 — Contenuti ricchi (2–3 settimane)
- [ ] Recuperare e caricare tutte le immagini delle gallerie
- [ ] Mappa interattiva sentieri
- [ ] Sezione storica completa
- [ ] Poesie (almeno quelle estratte)
- [ ] Dizionario dialettale interattivo

### Fase 3 — Funzionalità avanzate (opzionale)
- [ ] Calendario eventi
- [ ] Ricerca globale (Pagefind)
- [ ] Upload foto dalla comunità
- [ ] PWA / installazione mobile
- [ ] Mappa emigrati (Romano Marchi)

---

## COSTI STIMATI

| Voce | Costo |
|---|---|
| Dominio civago.it (già esistente) | €0 (già pagato) |
| Hosting Netlify/Cloudflare Pages | €0 (gratuito) |
| Template Astro (open source) | €0 |
| OpenStreetMap per mappe | €0 |
| OpenWeatherMap (free tier) | €0 |
| **Totale infrastruttura** | **€0/anno** |
| Design e sviluppo (se fai da te) | €0 |
| Design e sviluppo (se commissioni) | €500–2.000 |

---

## PROSSIMI PASSI

1. **Decidi la tecnologia** (Astro statico? WordPress?)
2. **Raccogli le immagini** — HTTrack può scaricare in automatico tutte le foto dal sito vecchio
3. **Scegli un template** di base da cui partire
4. Iniziamo a costruire!

---

> Per scaricare tutte le immagini dal sito vecchio in automatico:
> ```bash
> httrack https://www.civago.it/ -O ./civago_backup -r3 --mirror
> ```
> Questo crea una copia completa in locale (testi + immagini + PDF).
