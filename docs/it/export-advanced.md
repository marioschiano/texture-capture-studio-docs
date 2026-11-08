# Export e Advanced

## Export

Texture Capture Studio offre un preset per mesh statiche con **FBX** selezionato di default.

| Formato | Opzioni principali |
| --- | --- |
| FBX | Oggetti selezionati, applica modificatori, triangola, Apply Transform, Apply Unit. Usa -Z Forward e Y Up. |
| OBJ | Oggetti selezionati, applica modificatori, triangola, esporta materiali. |
| GLB | Oggetti selezionati, applica modificatori, esporta materiali. La triangolazione è gestita dall'export glTF. |

Animazioni, camere, luci e armature sono escluse da questo workflow per mesh statiche.

## Advanced

Le impostazioni avanzate sono separate dal workflow principale per non confondere l'utente medio.

### Selection Overlay

Controlla visibilità, dimensione, colore e opacità dei punti; riempimento dei poligoni; opacità del poligono selezionato; opacità delle guide; cursore 3D. La sezione **Snapping** permette di configurare l'aggancio a vertici, bordi e guide e le relative distanze.

### Perspective Guides e Box Visibility

Qui trovi **Perspective Mode**, **Sensor Width**, spessore e dimensione delle etichette delle guide. **Automatic Guides** controlla la sensibilità del rilevamento automatico. Per i box dell'addon compatibili sono disponibili **Mask Rear Faces** e **Hide Back Faces**.

**Sensor Width** influisce sull'interpretazione in millimetri della lente stimata: non è un controllo di velocità o di sensibilità del mouse.

### Precision Magnifier

Lo zoom di precisione aiuta a posizionare correttamente i punti di estrazione:

- attivazione dello zoom;
- quantità di ingrandimento e dimensione della finestra;
- mirino centrale;
- griglia dei pixel agli ingrandimenti elevati.

Lo zoom aiuta durante il posizionamento e la modifica; puoi regolare anche il rallentamento del cursore con **Cursor Slowdown**.

### Reset e pulizia

- **Reset Defaults** ripristina le impostazioni predefinite dell'addon.
- **Purge Unused** elimina i data-block inutilizzati generati da Texture Capture Studio, preservando le texture presenti nella lista e i file salvati.
