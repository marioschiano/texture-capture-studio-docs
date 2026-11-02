# Export and Advanced

## Export

Texture Capture Studio provides a static-mesh preset with **FBX** selected by default.

| Format | Main options |
| --- | --- |
| FBX | Selected objects, apply modifiers, triangulate, apply transform, apply unit. Uses -Z Forward and Y Up. |
| OBJ | Selected objects, apply modifiers, triangulate, export materials. |
| GLB | Selected objects, apply modifiers, export materials. Triangulation is handled by glTF export. |

Animations, cameras, lights, and armatures are excluded by this static-mesh workflow.

## Advanced

Advanced settings are intentionally separated from the main workflow.

### Selection Overlay

Controls point visibility, point size, point color and opacity, polygon fill, selected-polygon opacity, guide opacity, the 3D cursor, and vertex/edge snapping.

### Precision Magnifier

The magnifier helps place extraction points accurately:

- enable or disable the magnifier;
- choose zoom amount and window size;
- show a crosshair;
- show a pixel grid at high zoom.

The magnifier appears after **New Points** is activated, follows the cursor without a fixed offset, and temporarily slows point movement. Normal cursor sensitivity returns after the point is placed.

### Reset and cleanup

- **Reset Advanced Defaults** restores the recommended overlay and magnifier settings.
- **Purge Unused** removes unused Texture Capture Studio data blocks.
