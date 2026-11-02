# Complete Workflow

The interface follows a numbered workflow. Optional sections can be skipped.

## 1. Source Photo

Load the original photograph, choose an output folder, and set the base texture name. **Lock Camera View** keeps the image workspace stable while points and guides are drawn.

Extraction dimensions are calculated from the selected pixels in the source image, with a maximum output dimension of 8192 pixels per side.

## 2. Match Perspective — Optional

Perspective Match reconstructs a virtual camera from two sets of parallel real-world lines.

1. Enable Perspective Match.
2. Draw two red X guides on edges parallel in the real scene.
3. Draw two green Y guides on a second perpendicular direction.
4. Optionally draw the blue Z guide. Its lower point becomes the 3D origin.
5. Click **Solve Perspective**.

After solving, new points can be placed on the 2D photo, ground plane, front wall, side wall, or chosen automatically from the polygon edges.

## 3. Extract Textures

Choose an extraction method:

| Method | Recommended use |
| --- | --- |
| Perspective Correct | Walls, brickwork, floors, signs, facades, and other rigid planes. |
| Tessellated Smooth | Reflections, water, glass, and irregular surfaces where one rigid homography creates visible distortion. |

**New Points** starts a new four-point polygon. **Edit Points** adjusts the current polygon. The precision magnifier appears while placing a point when enabled in Advanced.

Use **Extract Selected Polygon** or **Extract All Polygons** when several regions are stored.

## 3A. Polygons

Closed four-point regions are listed here. After Perspective Match is solved, **Create Perspective Box** can create a simple box aligned to the reconstructed camera and scene axes.

## 3B. Extracted Textures

Preview the extracted image, delete unwanted results, purge unused data, or create a Blender material for the selected texture.

## 4–8

- [PBR Maps and Displacement](pbr-maps.md)
- [Trim Sheet and Atlas](trim-atlas.md)
- [Export and Advanced](export-advanced.md)
