# Texture Capture Studio

<span class="te-draft">Documentation draft</span>

Extract high-resolution textures directly from source photos, correct perspective, generate PBR maps, and create aligned trim sheets or atlases in Blender.

<div class="te-flow">Source Photo → Perspective Match → Extract → PBR → Trim / Atlas → Export</div>

## What Texture Capture Studio does

Texture Capture Studio uses the real pixels of the loaded source image. It does **not** capture the Blender viewport and is therefore independent of monitor resolution.

If a wall occupies 2200 × 1600 pixels in an 8000 × 6000 photo, the extracted texture can preserve approximately that source detail even when the viewport is displayed on a 1080p monitor.

## Main features

- Optional two-point perspective reconstruction for architectural photos.
- Four-point texture extraction with perspective-correct or tessellated-smooth warping.
- Multiple stored polygons and extracted textures.
- PBR map generation: Normal, Height, Roughness, and Ambient Occlusion.
- Height-map displacement with automatic subdivision and Displace modifier setup.
- Vertical or horizontal trim sheets.
- Automatic pixel-perfect atlas packing that preserves the original texel density.
- Static-mesh export to FBX, OBJ, or GLB.
- Precision magnifier, snapping, overlays, and other advanced drawing controls.

!!! note "PBR maps are estimates"
    PBR maps generated from one color photograph are useful production starting points, but they are not physically measured surface data. Lighting, shadows, and reflections in the source photo can influence the result.

## Compatibility

Texture Capture Studio requires **Blender 4.2 or later** and is installed as a Blender Extension ZIP.

## Start here

- [Installation](installation.md)
- [Quick Start](quick-start.md)
- [Complete Workflow](workflow.md)
- [PBR Maps and Displacement](pbr-maps.md)
- [Trim Sheet and Atlas](trim-atlas.md)
