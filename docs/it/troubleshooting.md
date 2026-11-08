# Risoluzione problemi

Se un'operazione non dà il risultato atteso, salva una copia del progetto e cambia un'impostazione alla volta. Per ricevere assistenza consulta [Supporto](support.md).

## Il pannello non compare

- Verifica che l'estensione sia installata e abilitata e che Blender sia almeno alla versione 4.2.
- Nella **3D Viewport** premi **N**, poi cerca la scheda **Texture Capture Studio**.
- Controlla la versione visualizzata nel titolo e, se necessario, riavvia Blender dopo l'installazione.

## Non riesco a creare i punti

Carica una foto con **Load Photo**, apri **3. Capture → Texture**, premi **New Points** e posiziona i punti sulla foto. Se hai attivato una superficie 3D in **New Points Surface**, risolvi prima Match Perspective oppure usa **Photo 2D**. Controlla anche eventuali messaggi dell'addon.

## Le guide o il box non coincidono con la foto

Usa bordi effettivamente paralleli nel mondo reale e ben distanziati. Verifica e correggi le guide suggerite con **Edit Guides**, poi premi nuovamente **Solve Camera**. In 3-Point servono due guide per ogni asse, comprese le verticali Z. La ricostruzione è una stima: foto con linee poco leggibili o prospettiva complessa possono richiedere correzioni manuali.

## La texture estratta è deformata o ha proporzioni inattese

Controlla che i quattro punti seguano gli angoli della stessa superficie piana e siano nell'ordine del perimetro. Prova **Perspective Correct** per un rettangolo raddrizzato e confronta gli altri metodi; **Camera Projected** non promette un rettangolo pieno. Regola **Target UV Ratio** o usa **Custom Ratio** se conosci le proporzioni. Acqua, riflessi e superfici non piane possono dare risultati difficili da interpretare.

## Non trovo la texture salvata

Controlla **Output Folder** e **Texture Name** in Capture o Trim Sheet. Verifica che la cartella esista o possa essere creata e che tu abbia permessi di scrittura. Con un percorso Blender relativo come `//textract_output`, salva prima il file `.blend` oppure scegli una cartella assoluta. Ricorda che un'anteprima non sostituisce **Build Trim Sheet**.

## Il trasferimento sulle facce non parte

Carica la foto e seleziona una geometria compatibile, come un box dell'addon o un cubo standard di Blender. In Object Mode usa **Extract & Map Visible Faces** e controlla che le facce siano inquadrate dalla camera sorgente. In Edit Mode seleziona esattamente una faccia con quattro vertici e usa **Extract & Map Selected Face**. Controlla eventuali errori mostrati da Blender.

## Lo snapping non si aggancia come previsto

In **Advanced → Snapping** controlla che l'aggancio desiderato sia abilitato e regola le distanze in pixel. Per la geometria prospettica verifica anche la spunta **Snapping** in **Perspective Geometry**. La vicinanza viene valutata nella viewport: ingrandisci la zona e controlla visivamente il punto finale.

## La giunzione della trim è ancora visibile

Attiva **Make Seamless X**, confronta **Edge Blend** e **Mirror & Blend** e modifica gradualmente **Edge Blend Width**. Controlla le tre ripetizioni dell'anteprima. Ombre, riflessi o elementi unici possono rimanere riconoscibili anche con bordi sfumati; prova un'altra porzione sorgente o un ritocco esterno.

## L'atlas automatico non entra nella dimensione scelta

Aumenta **Maximum Atlas Size** entro il limite disponibile, abilita **Allow 90° Rotation** o seleziona meno regioni. Il packing automatico mira a conservare l'ingombro in pixel: non rimpicciolisce automaticamente le regioni per farle entrare.

## Blender rallenta o usa troppa memoria

Prova con una foto più piccola o meno texture per volta, disattiva le mappe PBR non necessarie e parti con pochi **Subdivision Levels** nel displacement. Le immagini grandi, le anteprime e la suddivisione possono aumentare molto l'uso di memoria.

## Compare un errore Python

Copia il traceback completo, annota le operazioni appena eseguite e le versioni di Blender e dell'addon. Consulta [Supporto](support.md) per le informazioni da inviare; evita di condividere file riservati senza autorizzazione.
