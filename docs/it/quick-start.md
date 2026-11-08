# Guida rapida

Questo esempio estrae una superficie rigida e piana, come un muro di mattoni.

1. Apri **1. Source Photo** e premi **Load Photo**.
2. Per la prima estrazione lascia disattivato **2. Match Perspective**: non è obbligatorio per catturare una texture.
3. Apri **3. Capture**, scegli **Texture** e imposta **Extraction Method** su **Perspective Correct**.
4. Premi **New Points** e posiziona quattro punti lungo il contorno del muro, seguendone il perimetro.
5. Se necessario correggi gli angoli con **Edit Points**.
6. In **3. Capture**, scegli **Output Folder** e **Texture Name**, quindi premi **Extract Perspective Texture**.
7. Apri **Extracted Textures** e controlla la texture risultante. Se vuoi creare un materiale, seleziona la texture e usa **Create Material From Selected**.

La cattura usa i pixel della fotografia originale, non uno screenshot della viewport. La correzione prospettica può ricampionare l'immagine: la proporzione reale della superficie non è sempre ricavabile con precisione dalla sola foto. Per controllarla usa **Target UV Ratio**, descritto nel [workflow completo](workflow.md).

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
