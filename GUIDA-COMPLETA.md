# 📦 STRUTTURA COMPLETA PROGETTO POSTER AR

## 📁 Organizzazione File

Crea questa struttura di cartelle sul tuo PC:

```
poster-ar-cilla/
│
├── index.html                    (file HTML Mind-AR fornito)
│
├── markers/
│   └── targets.mind             (il file che hai scaricato)
│
├── video/
│   └── animazione.mp4           (il tuo video - vedi istruzioni sotto)
│
└── README.md                     (opzionale - info progetto)
```

---

## 🎬 PREPARARE IL VIDEO

### Requisiti tecnici:
- **Formato**: MP4 (codec H.264)
- **Dimensione**: Max 10-15 MB
- **Risoluzione**: 1280x720 o 1920x1080
- **Durata consigliata**: 5-15 secondi (il video andrà in loop)
- **Aspect ratio**: 16:9 (orizzontale come il poster)
- **Frame rate**: 30fps

### Opzioni per creare/ottimizzare il video:

#### OPZIONE A - Video già pronto
Se hai già un video:
1. Rinominalo in `animazione.mp4`
2. Mettilo nella cartella `video/`
3. Se è troppo grande (>15MB), comprimilo con uno dei metodi sotto

#### OPZIONE B - Creare animazione da immagine statica
Puoi animare elementi del poster stesso:
- **CapCut** (gratis, mobile/desktop): effetti movimento, zoom, parallax
- **Canva** (online): template video con animazioni
- **Adobe Express** (online, gratis): anima foto con motion

#### OPZIONE C - Video generato con AI
- **Runway ML**: https://runwayml.com (text/image to video)
- **Pika Labs**: https://pika.art (animazione AI)
- **Stability AI**: video generation

### Come comprimere il video:

**Metodo 1 - Online (facilissimo):**
1. Vai su: https://www.freeconvert.com/video-compressor
2. Carica il video
3. Imposta:
   - Formato: MP4
   - Codec: H.264
   - Target size: 10 MB
4. Scarica il video compresso

**Metodo 2 - HandBrake (software gratuito):**
1. Scarica: https://handbrake.fr/
2. Importa il video
3. Preset: "Fast 720p30"
4. Video codec: H.264
5. Quality: RF 28
6. Esporta

**Metodo 3 - FFmpeg (riga di comando, avanzato):**
```bash
ffmpeg -i input.mp4 -c:v libx264 -crf 28 -preset fast -vf "scale=1280:720" -c:a aac -b:a 128k animazione.mp4
```

---

## ⚙️ PERSONALIZZAZIONE

### Regolare dimensioni del video sul poster

Nel file `index-mindar.html`, trova questa riga:

```html
<a-video
    ...
    width="1.77"
    height="1"
```

**Calcolo:**
- Il poster ha aspect ratio 3:4 (verticale)
- Se vuoi che il video copra tutto il poster: `width="0.75" height="1"`
- Se vuoi che il video sia orizzontale centrato: `width="1.77" height="1"` (default)
- Sperimenta con i valori finché non è perfetto

### Cambiare posizione del video

```html
position="0 0 0"    <!-- Centrato -->
position="0 0.2 0"  <!-- Spostato in alto -->
position="0 -0.2 0" <!-- Spostato in basso -->
```

### Aggiungere effetti al video

**Esempio: Video con bordo luminoso**
```html
<a-video
    src="#video-animazione"
    position="0 0 0"
    width="1.77"
    height="1"
    material="shader: flat; side: double; opacity: 1"
    animation="property: opacity; from: 0; to: 1; dur: 500; easing: easeInOutQuad">
</a-video>
```

---

## 🚀 PUBBLICAZIONE ONLINE (GitHub Pages - GRATUITO)

### Perché serve HTTPS:
- I browser richiedono HTTPS per accedere alla fotocamera
- GitHub Pages offre HTTPS gratuito automatico

### Step by step:

#### 1. Crea account GitHub (se non ce l'hai)
- Vai su: https://github.com
- Clicca "Sign up"
- Segui la procedura di registrazione

#### 2. Crea nuovo repository
1. Clicca sul "+" in alto a destra → "New repository"
2. Nome repository: `poster-ar-cilla` (o quello che vuoi)
3. Descrizione: "Poster AR animato per Cilla"
4. Visibilità: **Public** ✓
5. ❌ NON spuntare "Add a README file"
6. Clicca "Create repository"

#### 3. Carica i file

**Metodo A - Drag & Drop (più facile):**
1. Nella pagina del repository appena creato
2. Clicca "uploading an existing file"
3. Trascina TUTTA la cartella `poster-ar-cilla` nella finestra
4. Scrivi un messaggio: "Upload progetto AR"
5. Clicca "Commit changes"

**Metodo B - GitHub Desktop (consigliato se fai modifiche frequenti):**
1. Scarica GitHub Desktop: https://desktop.github.com/
2. Installa e fai login
3. File → "Add local repository" → seleziona `poster-ar-cilla`
4. Clicca "Publish repository"

#### 4. Attiva GitHub Pages
1. Nel repository, vai su "Settings" (icona ingranaggio)
2. Scorri nel menu laterale fino a "Pages"
3. Source: "Deploy from a branch"
4. Branch: seleziona "main" → folder: "/ (root)"
5. Clicca "Save"

#### 5. Attendi deploy (2-3 minuti)
La tua pagina sarà disponibile su:
```
https://tuo-username.github.io/poster-ar-cilla/
```

Esempio: se il tuo username è "mario.rossi", l'URL sarà:
```
https://mario.rossi.github.io/poster-ar-cilla/
```

---

## 📱 CREARE IL QR CODE

Una volta pubblicato il sito:

### Opzione 1 - Online (gratuito):
1. Vai su: https://www.qr-code-generator.com/
2. Incolla l'URL del tuo sito GitHub Pages
3. Personalizza il design (colori, logo)
4. Scarica in alta risoluzione (PNG, 300 DPI minimo)

### Opzione 2 - Con logo personalizzato:
1. Vai su: https://www.qrcode-monkey.com/
2. Incolla URL
3. Upload logo (opzionale)
4. Scegli colori che si abbinino al poster
5. Scarica

### Dimensioni consigliate per stampa:
- QR code: minimo 3x3 cm
- Risoluzione: 300 DPI
- Formato: PNG o SVG (vettoriale meglio)

---

## 🖨️ STAMPA DEL POSTER

### Posizionamento QR code:
- **Angolo in basso a destra** (classico)
- **In basso centrato** (moderno)
- **Integrato nel design** (più elegante)

### Consigli di stampa:
1. Stampa il poster in **alta qualità** (minimo 300 DPI)
2. Aggiungi il QR code con spazio bianco intorno
3. Testa il QR code prima di stampare (scansiona con il telefono)
4. Carta consigliata: patinata opaca o lucida

### Test prima della stampa finale:
1. Stampa una versione A4 di prova
2. Testa il QR code con vari smartphone
3. Verifica che il tracking funzioni
4. Solo dopo procedi con la stampa finale

---

## ✅ CHECKLIST FINALE

Prima di pubblicare, verifica:

- [ ] File `targets.mind` nella cartella `markers/`
- [ ] Video `animazione.mp4` nella cartella `video/` (max 15MB)
- [ ] File `index.html` (Mind-AR) nella root
- [ ] Video testato (si apre e funziona)
- [ ] Dimensioni video corrette nel codice HTML
- [ ] Repository GitHub creato
- [ ] GitHub Pages attivato
- [ ] Sito raggiungibile via HTTPS
- [ ] QR code generato con URL corretto
- [ ] QR code testato su smartphone
- [ ] AR funziona inquadrando il poster sul computer

---

## 🔧 TEST LOCALE (opzionale)

Se vuoi testare prima di pubblicare online:

### Opzione 1 - Live Server (VS Code):
1. Installa VS Code
2. Installa estensione "Live Server"
3. Tasto destro su `index.html` → "Open with Live Server"
4. Apri da smartphone usando l'IP locale

### Opzione 2 - Python Simple Server:
```bash
cd poster-ar-cilla
python -m http.server 8000
```
Poi apri: `http://localhost:8000`

⚠️ **ATTENZIONE**: Il test locale potrebbe non funzionare per la fotocamera (serve HTTPS)

---

## 📞 PROSSIMI PASSI

Cosa ti serve ora:

1. **Hai il video?** → Sì / No
2. **Vuoi che ti aiuti a ottimizzarlo?**
3. **Vuoi aiuto con la pubblicazione su GitHub?**
4. **Vuoi un design del QR code personalizzato?**

Fammi sapere e procediamo!
