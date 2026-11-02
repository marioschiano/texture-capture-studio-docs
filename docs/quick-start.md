# Quick Start

This guide extracts a rigid planar surface such as a brick wall.

1. Open **1. Source Photo** and click **Load Photo**.
2. Choose the output folder and texture name.
3. Leave **2. Match Perspective** disabled for a first manual extraction.
4. In **3. Extract Textures**, choose **Perspective Correct**.
5. Click **New Points** and place four points around the wall.
6. Adjust the corners with **Edit Points** if necessary.
7. Click **Extract Perspective Texture**.
8. Open **3B. Extracted Textures** to preview the full-resolution result.
9. Use **Create Material** to create and assign a Blender material.

## Add PBR maps

1. Open **4. Generate PBR — Optional**.
2. Enable **PBR Generation**.
3. Select Normal, Height, Roughness, and Ambient Occlusion.
4. Adjust strength and contrast values.
5. Click **Generate Selected**.

The maps are generated from the extracted image pixels, not from the viewport preview.

## Add real depth with the height map

Select the textured mesh, choose subdivision levels and displacement strength, then click **Apply Height Displacement**. Texture Capture Studio creates the subdivision and displacement setup using the generated Height map.

!!! warning
    High subdivision levels can create very dense geometry. Start with a low level and increase it only when the silhouette or close-up detail requires it.
