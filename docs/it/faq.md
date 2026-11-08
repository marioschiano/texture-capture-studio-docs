# FAQ

Risposte rapide sul workflow. Per altri controlli consulta [Risoluzione problemi](troubleshooting.md).

## Quale versione di Blender serve?

La versione documentata richiede Blender **4.2 o successivo**. Per installare lo ZIP consulta [Installazione](installation.md).

## Devo fare Match Perspective per estrarre una texture?

No. Puoi caricare la foto e usare **3. Capture → Texture**, **New Points** e **Extract Perspective Texture**. Match Perspective è utile per ricostruire la scena e stimare proporzioni 3D, ma non è obbligatorio per una cattura 2D.

## La qualità dipende dalla dimensione del monitor?

No. La cattura usa l'immagine sorgente, non uno screenshot della viewport. La correzione prospettica ricampiona i pixel e non può recuperare dettagli assenti nella foto.

## Perché il rettangolo estratto non ha le proporzioni reali?

Da una sola foto le proporzioni fisiche non sono sempre determinabili. In **Target UV Ratio**, prova **Custom Ratio** se conosci larghezza e altezza reali; se hai risolto la camera e creato la superficie 3D, puoi valutare **Solved 3D Surface**. Controlla sempre il risultato.

## Posso trasferire la foto a un cubo Blender?

Sì, per un cubo standard compatibile. Selezionalo, apri **Capture → Polygons** e usa **Extract & Map Visible Faces** in Object Mode oppure seleziona una sola faccia quadrangolare in Edit Mode. Il retro non visibile non può essere ricostruito dalla foto; **Opposite Face UV** può riutilizzare la texture sulla faccia opposta.

## Le mappe PBR sono misurazioni reali del materiale?

No. Sono stime derivate dalla foto: illuminazione, ombre e riflessi possono influenzarle. Vedi [Mappe PBR e displacement](pbr-maps.md).

## Come verifico una trim seamless?

In **5. Trim Sheet** abilita **Make Seamless X** e premi **Create Live Seamless Preview**: confronta le tre ripetizioni prima e dopo. Quando il risultato è soddisfacente premi **Build Trim Sheet**. Una giunzione può restare visibile in presenza di ombre o dettagli molto irregolari.

## Dove trovo assistenza?

Consulta [Supporto](support.md) o scrivi a [support.marioschiano3d@gmail.com](mailto:support.marioschiano3d@gmail.com), indicando versioni, passaggi e messaggio di errore completo.
