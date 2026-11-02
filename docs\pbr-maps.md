# PBR Maps and Displacement

Texture Capture Studio can derive four supporting maps from an extracted Base Color texture.

## Available maps

| Map | Purpose |
| --- | --- |
| Normal | Simulates small surface direction changes without adding geometry. |
| Height | Stores relative surface height as grayscale data. |
| Roughness | Controls how broad or sharp reflections appear. |
| Ambient Occlusion | Estimates darkening in small cavities and contact-like details. |

## Controls

- **Normal Strength** controls the intensity of the generated normal gradients.
- **Height Strength** and **Height Contrast** shape the grayscale height range.
- **Roughness Strength** and **Roughness Contrast** control the reflective variation.
- **AO Strength** and **AO Contrast** control cavity darkening.
- **Detail Radius** changes the scale of local detail used for surface analysis.

Use **Generate Selected** for the active extracted texture or **Generate All** for every extracted texture.

## Height displacement

The generated Height map can drive real geometry:

1. Create and assign the texture material to a mesh.
2. Select that mesh.
3. Set **Subdivision Levels**.
4. Set **Displacement Strength** in Blender units.
5. Set **Midlevel**; 0.5 means mid-gray produces no displacement.
6. Click **Apply Height Displacement**.

For a brick wall, mortar and brick variation can gain visible depth. The quality depends on mesh density and on how clearly the source photo separates material relief from lighting.

!!! note
    Height inferred from one photograph cannot reliably distinguish geometry from painted color, shadows, or highlights. Use the controls to tune the result before applying heavy subdivision.

## Trim and atlas consistency

When PBR maps exist, new trim sheets and atlases reuse the same layout for Base Color, Normal, Height, Roughness, and AO, so every map remains aligned to the same UV coordinates.
