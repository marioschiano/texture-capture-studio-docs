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

Controlla visibilità, dimensione, colore e opacità dei punti; riempimento dei poligoni; opacità del poligono selezionato; guide prospettiche; cursore 3D; snapping ai vertici e ai bordi.

### Precision Magnifier

Lo zoom di precisione aiuta a posizionare correttamente i punti di estrazione:

- attivazione dello zoom;
- quantità di ingrandimento e dimensione della finestra;
- mirino centrale;
- griglia dei pixel agli ingrandimenti elevati.

La finestra compare dopo l'attivazione di **New Points**, rimane centrata sul cursore senza offset fisso e rallenta temporaneamente il movimento. Dopo il posizionamento del punto, la sensibilità normale viene ripristinata.

### Reset e pulizia

- **Reset Advanced Defaults** ripristina i valori consigliati di overlay e zoom.
- **Purge Unused** elimina i data-block di Texture Capture Studio non più utilizzati.
