# Mappe PBR e displacement

Texture Capture Studio può ricavare quattro mappe di supporto dalla texture Base Color estratta.

<div class="te-ui-row" markdown="1">
<div class="te-ui-text" markdown="1">

Nella schermata i controlli sono disattivati perché la generazione non è ancora stata abilitata.

- **Enable PBR Generation**: abilita o disabilita i controlli di generazione.
- **Normal, Height, Roughness, Ambient Occlusion**: selezionano le mappe da produrre.
- **Normal Strength**: regola l'intensità della Normal map.
- **Height Strength / Height Contrast**: regolano intensità e contrasto della mappa di altezza.
- **Roughness Strength / Roughness Contrast**: regolano intensità e contrasto delle variazioni di rugosità.
- **AO Strength / AO Contrast**: regolano intensità e contrasto dell'occlusione stimata.
- **Detail Radius**: imposta la scala del dettaglio locale analizzato.
- **Generate Selected**: genera le mappe abilitate per la texture selezionata.
- **Generate All**: le genera per tutte le texture estratte.
- **Subdivision Levels**: imposta i livelli di suddivisione per il displacement; valori alti aumentano molto la geometria.
- **Displacement Strength**: imposta l'intensità dello spostamento della superficie.
- **Midlevel**: indica il valore della Height map che non produce spostamento; normalmente 0,5.
- **Apply Height Displacement**: applica la configurazione alla mesh texturizzata selezionata.

Le righe informative spiegano che il materiale e le mappe vengono generati dai pixel della texture e che bisogna selezionare la mesh prima del displacement.

</div>
<div class="te-ui-image" markdown="1">

![Pannello Generate PBR con le impostazioni disattivate](images/generate-pbr.png)

</div>
</div>

## Mappe disponibili

| Mappa | Funzione |
| --- | --- |
| Normal | Simula piccole variazioni di direzione della superficie senza aggiungere geometria. |
| Height | Memorizza l'altezza relativa della superficie in scala di grigi. |
| Roughness | Controlla quanto i riflessi appaiono larghi oppure nitidi. |
| Ambient Occlusion | Stima l'oscuramento nelle piccole cavità e nei dettagli di contatto. |

## Controlli

- **Normal Strength** controlla l'intensità dei gradienti della Normal map.
- **Height Strength** e **Height Contrast** regolano l'intervallo della mappa in scala di grigi.
- **Roughness Strength** e **Roughness Contrast** regolano le variazioni di riflessione.
- **AO Strength** e **AO Contrast** controllano l'oscuramento delle cavità.
- **Detail Radius** cambia la scala del dettaglio locale analizzato.

Usa **Generate Selected** per la texture estratta attiva oppure **Generate All** per tutte le texture estratte.

## Height displacement

La Height map generata può deformare realmente la geometria:

1. Crea e assegna il materiale a una mesh.
2. Seleziona la mesh.
3. Imposta **Subdivision Levels**.
4. Imposta **Displacement Strength** in unità Blender.
5. Imposta **Midlevel**; con 0.5 il grigio medio non produce spostamento.
6. Premi **Apply Height Displacement**.

Su un muro di mattoni, mattoni e fughe possono acquistare una profondità visibile. La qualità dipende dalla densità della mesh e da quanto la foto permette di distinguere il rilievo reale dall'illuminazione.

!!! note
    Da una sola fotografia non è sempre possibile distinguere geometria, colore dipinto, ombre e riflessi. Regola i valori prima di applicare una suddivisione pesante.

## Coerenza di Trim e Atlas

Quando le mappe PBR esistono, i nuovi Trim Sheet e Atlas riutilizzano lo stesso layout per Base Color, Normal, Height, Roughness e AO. Tutte le mappe restano così allineate alle stesse coordinate UV.

!!! info "Immagine da aggiungere — mappe PBR"
    Inserire un esempio reale della stessa texture con Base Color, Normal, Height, Roughness e AO generate dall'addon, etichettate e affiancate.
