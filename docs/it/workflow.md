# Workflow completo

Questa guida descrive il workflow di Texture Capture Studio; le schermate dell'interfaccia sono della versione 0.3.130. Match Perspective e le fasi PBR sono opzionali: per estrarre una porzione di foto puoi passare direttamente da **Source Photo** a **Capture**.

## 1. Source Photo

<div class="te-ui-row" markdown="1">
<div class="te-ui-text" markdown="1">

- **Load Photo**: apre il selettore per caricare la fotografia originale da cui estrarre le texture.
- **Freccia della sezione**: apre o chiude Source Photo senza eliminare la foto.

La schermata mostra lo stato iniziale. Dopo il caricamento compaiono il nome della foto e il relativo cestino per rimuoverla.

</div>
<div class="te-ui-image" markdown="1">

![Pannello Source Photo con il pulsante Load Photo](images/source-photo.png)

</div>
</div>

Premi **Load Photo** e scegli la fotografia. Per rimuoverla usa il cestino accanto al nome. **Lock Camera View**, in Advanced, mantiene la vista dedicata al lavoro sulla foto; disattivalo quando vuoi navigare liberamente nella scena.

La cattura usa l'immagine originale, non la risoluzione dello schermo. La dimensione dell'output dipende dalla porzione selezionata e dal metodo di estrazione: la correzione prospettica può interpolare i pixel e non può ricostruire dettagli assenti nella foto.

## 2. Match Perspective

<div class="te-ui-row" markdown="1">
<div class="te-ui-text" markdown="1">

- **Enable Perspective Match**: attiva o disattiva il workflow di ricostruzione prospettica e mostra i controlli per le guide.
- **Messaggio informativo**: segnala che devi caricare una foto prima di disegnare le guide; non è un pulsante.
- **Freccia della sezione**: apre o chiude il pannello.

La schermata mostra lo stato iniziale, senza foto; le guide e i pulsanti di solve compaiono proseguendo nel workflow descritto sotto.

</div>
<div class="te-ui-image" markdown="1">

![Pannello Match Perspective prima del caricamento della foto](images/match-perspective.png)

</div>
</div>

Usa questa fase se vuoi ricostruire la prospettiva della foto per modellare geometrie allineate o stimare le proporzioni di una superficie. Non è necessaria per una semplice cattura 2D.

![Schema delle guide X, Y e Z su un edificio](images/guide-prospettiche.svg)

*Schema illustrativo: le guide dello stesso colore seguono bordi paralleli nel mondo reale, non necessariamente paralleli nella foto.*

1. Attiva **Enable Perspective Match**.
2. Premi **Draw X Guides** e disegna due linee sui bordi della prima direzione, evidenziata in rosso.
3. Con **Draw Y Guides** disegna due linee sui bordi della seconda direzione orizzontale, in verde.
4. Disegna due guide verticali con **Draw Z Guides**. In modalità 2-Point il calcolo può partire anche senza Z; in 3-Point sono richieste.
5. Premi **Solve Camera**. Se le guide non corrispondono bene ai bordi, usa **Edit Guides**, correggile e ripeti il calcolo.

**Auto Detect Guides** propone un posizionamento automatico: verifica sempre le linee sulla foto e correggile prima del solve. Per ripartire usa **Clear All Guides**.

<div class="te-image-placeholder"><strong>Immagine da aggiungere: guide sulla foto</strong><span>Schermata reale di Blender con le due guide X, Y e Z e i controlli Match Perspective aperti.</span></div>

In **Advanced → Perspective Mode**, **2-Point Perspective** è il valore predefinito ed è adatto a foto con verticali approssimativamente parallele. **3-Point Perspective** considera anche la convergenza verticale: usa due linee per ciascuno degli assi X, Y e Z. Tre punti di fuga non significano tre linee per asse.

### Perspective Geometry

Dopo il solve puoi usare **Create Box** oppure creare un piano con **Auto Plane**, **Ground**, **Front** o **Side**. Durante la creazione si impostano le dimensioni progressivamente; **Extrude** aggiunge un passaggio per la profondità e **Snapping** abilita l'aggancio. Con un oggetto dell'addon selezionato puoi regolare **Wireframe**, **Wire Opacity** e **Base Opacity**. In Advanced sono disponibili anche i controlli di visibilità delle facce posteriori per i box compatibili.

La precisione della ricostruzione dipende dalla qualità delle guide e dalle ipotesi geometriche: controlla l'allineamento sulla foto e non considerare le dimensioni fisiche assolute automaticamente misurate.

<div class="te-image-placeholder"><strong>Immagine da aggiungere: geometria prospettica</strong><span>Un box o due piani creati sulla foto, con snapping lungo uno spigolo dell'edificio.</span></div>

## 3. Capture → Texture

<div class="te-ui-row" markdown="1">
<div class="te-ui-text" markdown="1">

- **Texture / Polygons**: alterna la cattura di aree alla gestione dei poligoni e al trasferimento sulle facce compatibili.
- **New Points**: avvia una nuova selezione sulla foto.
- **Edit Points**: permette di correggere i punti della selezione.
- **Cestino accanto ai punti**: cancella la selezione corrente.
- **Aligned Rectangle**: definisce un rettangolo allineato alla foto tramite due angoli; tieni premuto Shift per un quadrato.
- **Extraction Method**: sceglie come trasformare l'area selezionata; i tre metodi sono confrontati sotto.
- **Target UV Ratio**: sceglie come determinare il rapporto larghezza/altezza del risultato.
- **Output Folder** e pulsante cartella: impostano la destinazione dei file estratti.
- **Texture Name**: imposta il nome base dei risultati.
- **Extract Perspective Texture**: estrae la selezione corrente dalla foto.
- **Extract Selected Polygon / Extract All Polygons**: estraggono rispettivamente il poligono selezionato o tutti quelli disponibili per la foto.

Le righe con icona informativa sono messaggi di stato, non pulsanti. La schermata mostra l'interfaccia senza una foto caricata; alcuni testi sono abbreviati dalla larghezza della sidebar.

</div>
<div class="te-ui-image" markdown="1">

![Pannello Capture nella modalità Texture](images/capture.png)

</div>
</div>

Premi **New Points** e indica quattro angoli consecutivi dell'area. Usa **Edit Points** per correggerli; nella modalità **Polygons** puoi gestire le aree già create. **Aligned Rectangle** permette invece di definire un rettangolo con due angoli.

<div class="te-image-placeholder"><strong>Immagine da aggiungere: selezione e cattura</strong><span>Foto reale con i quattro punti sulla superficie e, accanto, la texture rettangolare estratta dall'addon.</span></div>

### Extraction Method

| Metodo | Risultato |
| --- | --- |
| **Perspective Correct** | Raddrizza un quadrilatero in una texture rettangolare; è il punto di partenza per pareti, pavimenti e altre superfici piane. |
| **Projection Paint — Tessellated** | Trasferisce la proiezione della foto su UV rettangolari tramite una griglia triangolata; **Projection Grid** ne regola la suddivisione. |
| **Camera Projected** | Conserva la proiezione vista dalla camera: non produce necessariamente un rettangolo riempito e raddrizzato. |

Il tipo di contenuto — per esempio acqua o pavimentazione — non garantisce da solo un metodo migliore. La geometria, la prospettiva e i punti scelti influenzano il risultato: confronta le anteprime.

### Target UV Ratio

- **Automatic** sceglie una stima dalle informazioni disponibili e usa la superficie 3D risolta quando disponibile.
- **Selected Pixels** usa l'ampiezza e l'altezza della selezione nella foto.
- **Solved 3D Surface** usa le proporzioni della superficie ricostruita e richiede Match Perspective risolto.
- **Custom Ratio** permette di inserire larghezza divisa per altezza, utile quando conosci le proporzioni reali.

Senza informazioni aggiuntive, un rettangolo visto in prospettiva non rivela necessariamente le sue proporzioni reali. **New Points Surface**, mostrato con Perspective Match attivo, permette di scegliere la foto 2D o una superficie 3D; per le superfici 3D occorre prima risolvere la prospettiva.

Scegli **Output Folder** e **Texture Name**, poi premi **Extract Perspective Texture**. Per più aree puoi usare **Extract Selected Polygon** o **Extract All Polygons**.

## 3. Capture → Polygons: trasferire la foto a un box

La sezione **Polygons** gestisce i poligoni e il trasferimento sulle facce di geometrie compatibili: box o piani creati dall'addon e cubi standard di Blender.

1. Carica la foto, allinea la geometria alla vista e seleziona il box, il piano compatibile o il cubo.
2. Scegli **Capture → Polygons** e controlla **Opposite Face UV**: **None** non riusa la faccia opposta; **Stacked** riusa le UV; **Stacked Mirrored** le specchia.
3. In **Object Mode**, premi **Extract & Map Visible Faces** per elaborare le facce viste dalla camera. In **Edit Mode**, seleziona esattamente una faccia quadrangolare e premi **Extract & Map Selected Face**.

Per un cubo Blender standard l'addon applica la scala e crea una mappa UV **Photo Transfer** per la proiezione. Verifica il risultato e le facce opposte: la foto contiene solo le informazioni effettivamente visibili, quindi non può ricostruire automaticamente il retro nascosto.

<div class="te-image-placeholder"><strong>Immagine da aggiungere: trasferimento su cubo</strong><span>Confronto reale prima e dopo: cubo allineato alla foto e texture applicata alle facce visibili, con Capture → Polygons aperto.</span></div>

## Extracted Textures e Make Seamless

<div class="te-ui-row" markdown="1">
<div class="te-ui-text" markdown="1">

- **Lista**: raccoglie le texture estratte e consente di selezionare quella su cui lavorare; nello screenshot è vuota.
- **Occhio sulla riga**, quando disponibile: mostra o nasconde l'anteprima della texture.
- **Cestino laterale**: elimina la texture selezionata dall'addon.
- **X laterale**: svuota la lista delle texture estratte.
- **Icona Purge** e **Purge Unused Generated Data**: rimuovono i dati generati dall'addon che non sono più collegati; i file sul disco vengono conservati.
- **Messaggio informativo**: ricorda il comportamento della pulizia; non è cliccabile.

</div>
<div class="te-ui-image" markdown="1">

![Lista Extracted Textures vuota e comando di pulizia](images/extracted-textures.png)

</div>
</div>

<div class="te-ui-row" markdown="1">
<div class="te-ui-text" markdown="1">

- **Edge Blend Width**: ampiezza della zona di sfumatura ai bordi.
- **Noise Scale**: scala del rumore usato per rendere meno uniforme la transizione.
- **Warp Strength**: intensità della deformazione applicata alla transizione; valori più alti possono alterare di più il dettaglio.
- **Seed**: cambia la variazione casuale del rumore.
- **Sharpen**: aumenta la nitidezza del dettaglio locale nel risultato.
- **Create Live Seamless Preview**: crea un'anteprima del risultato modificabile.
- **Quick Edge Blend**: crea rapidamente una copia con i bordi sfumati.
- **Preview 3 x 3**: mostra la ripetizione per individuare le giunzioni.
- **Create Material From Selected**: crea un materiale usando la texture selezionata.

Dopo aver creato l'anteprima compaiono anche **Edit Mask in Image Editor** e **Bake Seamless Texture**. Il messaggio ricorda che viene creata una copia e che le eventuali mappe PBR vanno rigenerate per il risultato.

</div>
<div class="te-ui-image" markdown="1">

![Controlli Make Seamless per la singola texture](images/make-seamless.png)

</div>
</div>

In **Extracted Textures** puoi selezionare e visualizzare i risultati, eliminarli, pulire i dati generati inutilizzati e creare un materiale. Per una singola texture, apri **Make Seamless**:

1. Seleziona la texture e regola **Edge Blend Width**, **Noise Scale**, **Warp Strength**, **Seed** e, se necessario, **Sharpen**.
2. Premi **Create Live Seamless Preview** per verificare il risultato. Dopo la creazione puoi aprire **Edit Mask in Image Editor** per intervenire sulla maschera.
3. Premi **Bake Seamless Texture** per creare il risultato. In alternativa usa **Quick Edge Blend** per una sfumatura rapida e **Preview 3 x 3** per controllare la ripetizione.

<div class="te-image-placeholder"><strong>Immagine da aggiungere: seamless di una texture</strong><span>Confronto reale della texture singola ripetuta prima e dopo il bake seamless, con giunzioni visibili.</span></div>

Questi controlli lavorano su una singola texture; le opzioni per le fasce orizzontali sono nella pagina [Trim Sheet e Atlas](trim-atlas.md).

## Passaggi successivi

- [Mappe PBR e displacement](pbr-maps.md)
- [Trim Sheet e Atlas](trim-atlas.md)
- [Export e Advanced](export-advanced.md)
