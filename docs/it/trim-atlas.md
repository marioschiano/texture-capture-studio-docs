# Trim Sheet e Atlas

## Trim Sheet

La sezione Trim Sheet combina le texture estratte in una striscia verticale oppure orizzontale.

- **Vertical Trim Sheet** cambia l'orientamento.
- **Trim Padding** imposta lo spazio tra le regioni.
- Le mappe PBR usano lo stesso posizionamento della Base Color.

## Modalità Atlas

### Automatic — Preserve Resolution

La modalità automatica usa le mesh texturizzate selezionate e le loro UV attive. Misura ogni isola UV con la relativa immagine sorgente e ricrea il packing senza modificare l'ingombro in pixel.

Per esempio, se una regione della mesh usa esattamente 200 × 300 pixel sorgente, nell'Atlas la regione rimane di 200 × 300 pixel. Cambia la posizione UV, ma il dettaglio della texture non diventa più grande o più piccolo.

Opzioni:

- **Maximum Atlas Size**: dimensione massima consentita per l'Atlas.
- **Allow 90° Rotation**: ruota le isole complete quando migliora il packing.
- **Bake Base Color After Packing**: esegue il bake dei materiali copiati nella nuova texture condivisa.
- **Atlas Padding**: spazio intorno alle regioni impacchettate.

L'operazione crea una collection dedicata **Texture Capture Studio - Atlas**. Mesh e materiali sono copie indipendenti; gli oggetti originali mantengono UV, materiali e texture.

!!! important
    Il packing automatico conserva la densità dei pixel. Se le regioni non entrano nella dimensione massima senza ridimensionamento, occorre usare un Atlas più grande oppure meno regioni sorgente.

### Manual Grid

La modalità manuale usa celle di dimensione fissa e un numero prestabilito di colonne. È utile per slot volutamente uniformi, ma non calcola l'ingombro in pixel di ogni isola UV come la modalità automatica.

## Output Atlas PBR

Quando le mappe corrispondenti esistono, Texture Capture Studio può produrre output allineati come:

- `atlas_basecolor`
- `atlas_normal`
- `atlas_height`
- `atlas_roughness`
- `atlas_ao`

Tutte le mappe condividono lo stesso layout delle isole e le stesse coordinate UV.
