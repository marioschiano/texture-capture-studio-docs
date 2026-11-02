# Trim Sheet and Atlas

## Trim Sheet

The Trim Sheet section combines extracted textures into a vertical or horizontal strip.

- **Vertical Trim Sheet** changes orientation.
- **Trim Padding** sets spacing between regions.
- PBR maps use the same region placement as Base Color.

## Atlas modes

### Automatic — Preserve Resolution

Automatic mode uses selected textured meshes and their active UV maps. It measures each connected UV island against its source image and repacks the islands without changing their pixel footprint.

For example, if a mesh region uses exactly 200 × 300 source pixels, the packed atlas region remains 200 × 300 pixels. Its UV position changes, but its texture detail does not become larger or smaller.

Options:

- **Maximum Atlas Size**: largest allowed atlas dimension.
- **Allow 90° Rotation**: rotates complete islands when this improves packing.
- **Bake Base Color After Packing**: bakes copied source materials into the new shared atlas.
- **Atlas Padding**: spacing around packed regions.

The operation creates a dedicated **Texture Capture Studio - Atlas** collection. Meshes and materials are independent copies; the original objects keep their UVs, materials, and textures.

!!! important
    Automatic packing preserves texel density. If the regions cannot fit within the maximum atlas size without scaling, the operation must use a larger atlas or fewer source regions.

### Manual Grid

Manual mode uses a fixed cell size and number of columns. It is useful for intentionally uniform slots, but it does not calculate each UV island's source-pixel footprint like Automatic mode.

## PBR atlas outputs

When corresponding maps exist, Texture Capture Studio can produce matching outputs such as:

- `atlas_basecolor`
- `atlas_normal`
- `atlas_height`
- `atlas_roughness`
- `atlas_ao`

All maps share the same island layout and UV coordinates.
