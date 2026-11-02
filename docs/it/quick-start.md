# Guida rapida

Questo esempio estrae una superficie rigida e piana, come un muro di mattoni.

1. Apri **1. Source Photo** e premi **Load Photo**.
2. Scegli la cartella di output e il nome della texture.
3. Per la prima estrazione manuale lascia disattivato **2. Match Perspective**.
4. In **3. Extract Textures** scegli **Perspective Correct**.
5. Premi **New Points** e posiziona quattro punti intorno al muro.
6. Se necessario correggi gli angoli con **Edit Points**.
7. Premi **Extract Perspective Texture**.
8. Apri **3B. Extracted Textures** per controllare il risultato ad alta risoluzione.
9. Usa **Create Material** per creare e assegnare un materiale Blender.

## Aggiungere le mappe PBR

1. Apri **4. Generate PBR — Optional**.
2. Attiva **PBR Generation**.
3. Seleziona Normal, Height, Roughness e Ambient Occlusion.
4. Regola intensità e contrasto.
5. Premi **Generate Selected**.

Le mappe vengono generate dai pixel della texture estratta, non dalla preview della viewport.

## Aggiungere profondità reale con la Height map

Seleziona la mesh texturizzata, scegli i livelli di suddivisione e la forza del displacement, quindi premi **Apply Height Displacement**. Texture Capture Studio configura la suddivisione e il displacement usando la Height map generata.

!!! warning
    Livelli di suddivisione alti possono creare geometrie molto pesanti. Parti da un livello basso e aumentalo solo quando la silhouette o i primi piani richiedono più dettaglio.
