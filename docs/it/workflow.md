# Workflow completo

L'interfaccia segue un workflow numerato. Le sezioni opzionali possono essere saltate.

## 1. Source Photo

Carica la fotografia originale, scegli la cartella di output e imposta il nome base della texture. **Lock Camera View** mantiene stabile lo spazio di lavoro mentre disegni punti e guide.

Le dimensioni di estrazione vengono calcolate dai pixel selezionati nell'immagine sorgente, con un limite massimo di 8192 pixel per lato.

## 2. Match Perspective — Opzionale

Match Perspective ricostruisce una camera virtuale usando due gruppi di linee parallele nel mondo reale.

1. Attiva Perspective Match.
2. Disegna due guide X rosse su bordi paralleli nella scena reale.
3. Disegna due guide Y verdi su una seconda direzione perpendicolare.
4. Facoltativamente disegna la guida Z blu. Il punto più basso diventa l'origine 3D.
5. Premi **Solve Perspective**.

Dopo il calcolo, i nuovi punti possono essere posizionati sulla foto 2D, sul piano del terreno, sulla parete frontale, sulla parete laterale oppure con riconoscimento automatico dai bordi del poligono.

## 3. Extract Textures

Scegli il metodo di estrazione:

| Metodo | Uso consigliato |
| --- | --- |
| Perspective Correct | Pareti, mattoni, pavimenti, insegne, facciate e altri piani rigidi. |
| Tessellated Smooth | Riflessi, acqua, vetro e superfici irregolari dove una singola trasformazione crea deformazioni visibili. |

**New Points** avvia un nuovo poligono di quattro punti. **Edit Points** modifica il poligono corrente. Lo zoom di precisione compare durante il posizionamento quando è attivo in Advanced.

Usa **Extract Selected Polygon** oppure **Extract All Polygons** quando hai memorizzato più aree.

## 3A. Polygons

Qui vengono elencate le aree chiuse con quattro punti. Dopo aver risolto Match Perspective, **Create Perspective Box** può creare un box semplice allineato alla camera ricostruita e agli assi della scena.

## 3B. Extracted Textures

Puoi vedere l'anteprima dell'immagine estratta, eliminare risultati non desiderati, pulire i dati inutilizzati o creare un materiale Blender per la texture selezionata.

## Step 4–8

- [Mappe PBR e displacement](pbr-maps.md)
- [Trim Sheet e Atlas](trim-atlas.md)
- [Export e Advanced](export-advanced.md)
