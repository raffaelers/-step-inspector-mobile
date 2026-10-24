# STEP Inspector Mobile — prototipo 0.1

## Che cosa funziona
- Interfaccia mobile a tutto schermo con rotazione, zoom, viste, inquadratura.
- Apertura locale di file `.step` / `.stp` con `occt-import-js` (motore OpenCascade WebAssembly) e triangolazione visualizzata con Three.js.
- Ingombro della geometria triangolata e distanza **indicativa** fra due punti toccati sul modello.
- Demo 3D iniziale.
- Installazione come PWA quando ospitata su HTTPS.

## Limiti IMPORTANTI
- **Non è ancora un'app pronta per il collaudo dimensionale.** Le distanze derivano dalla mesh, non da B-Rep esatta; diametri, raggi, interassi, volume e angoli CAD non sono ancora implementati.
- Unità STEP assunte in millimetri: controllare la scala sul disegno originale.
- Il supporto offline richiede che l'app e le dipendenze siano state caricate e memorizzate; su iOS Safari può rimuovere cache e dati. Non è garantito per ogni file.
- Le librerie Three.js e occt-import-js vengono scaricate da CDN al primo utilizzo. La libreria STEP potrebbe non essere presente in cache se non si è mai aperto un STEP online.
- La versione CDN specificata potrebbe richiedere adattamenti a seconda della disponibilità/versione del pacchetto; prototipo non verificato su iPhone reale in questo ambiente.
- Non carica i modelli su server applicativi: il file viene letto nel browser. Il caricamento delle librerie richiede comunque richieste a CDN esterni.

## Come provarla su iPhone
1. Estrai la cartella e pubblica i file su un sito statico HTTPS, ad esempio GitHub Pages o Netlify. Non basta aprire `index.html` dall'app File: PWA e WebAssembly richiedono un server web.
2. Apri l'indirizzo HTTPS in **Safari** su iPhone.
3. Tocca **Condividi → Aggiungi alla schermata Home**.
4. Apri l'app, quindi mentre sei online apri un piccolo file STEP per inizializzare e memorizzare le librerie.
5. Prova in modalità aereo: la disponibilità offline dipende dalla cache di iOS.

## Prova locale su PC/Mac
Dalla cartella, avvia `python -m http.server 8000` e apri `http://localhost:8000` nel browser. Per provarla da iPhone serve invece HTTPS.

## Passo successivo
Distribuzione delle librerie come asset locali versionati, test su iPhone, misura geometrica B-Rep esatta, rilevamento cerchi/cilindri, unità di misura, gestione errori e file complessi.
