# TextureFast Getting Started Guide

TextureFast is a privacy-first AI texturing workflow for existing 3D models.
Start with a clean UV unwrap, describe the material, and generate a Base Color
texture plus a full PBR texture set — Albedo, Normal, Height, Roughness,
Metallic, and Ambient Occlusion — for your DCC or engine.

The basic workflow is:

1. Prepare the model and UVs.
2. Open the texturing workflow.
3. Describe the material.
4. Generate and review Base Color.
5. Extract the full PBR map set.
6. Download and import them into your DCC or engine.

## Before you start

Prepare:

- A TextureFast account with available plan usage or tokens
- A UV-unwrapped 3D model
- A clear material direction
- A target application such as Blender, Unity, Unreal Engine, or Godot

The main workflow accepts GLB, GLTF, OBJ, and FBX. GLB is recommended when
you want a single self-contained file.

## Step 1: Prepare the model

UV unwrapping flattens the surface of a 3D model into a 2D layout. TextureFast
uses that layout to place the generated image correctly.

Before exporting:

- Check that every visible surface has UV coordinates.
- Reduce stretching where detail matters.
- Avoid unwanted overlaps on areas that need unique texture detail.
- Leave sensible spacing between UV islands.
- Keep texel density reasonably consistent across the asset.
- Preview the model in your DCC before uploading.

TextureFast does not repair bad topology or create missing UVs. Fix those
issues in Blender, Maya, 3ds Max, or another DCC first.

## Step 2: Upload the model

Open the TextureFast texturing workflow and select your model file. The browser
loads the model for local preview and UV handling.

After upload:

1. Confirm that the model appears correctly in the viewport.
2. Check the UV readiness information if shown.
3. Give the asset a useful name.
4. Choose a style and quality option appropriate for the asset.

The core workflow is designed around local model handling. The generation
request may use the UV layout and other derived inputs required by the selected
feature.

## Step 3: Write a useful material prompt

Describe the surface, not only the object name. Include:

- Material
- Color or palette
- Finish
- Age and wear
- Pattern or grain
- Important secondary materials
- Art direction or target style

Weak prompt:

> Metal object

More useful prompt:

> Brushed stainless steel with fine horizontal grain, soft satin reflections,
> light edge wear, and darker grime in recessed areas.

For a game asset, include the visual direction:

> Stylized hand-painted stone with warm grey blocks, teal mortar, simplified
> cracks, and readable shapes for a mobile fantasy game.

For ArchViz:

> Wide-plank European oak flooring with a natural oil finish, subtle grain,
> warm honey-brown color, and light foot-traffic wear.

Keep prompt language consistent across a group of assets when you want a
cohesive art direction.

## Step 4: Choose a style and quality

Style presets can guide the visual direction across generations. Examples
include:

- AAA Photorealistic
- Handpainted
- Pixel Art
- AAA Stylized

Choose quality and resolution based on where the asset will appear. A background
prop may not need the same setting as a first-person weapon or a close-up
ArchViz hero asset.

Base Color supports up to 4K on supported quality tiers. Junior Base Color
generation is limited to 1K according to the current product configuration.
Check the live UI for the current plan matrix.

## Step 5: Generate Base Color

Generate the Base Color texture first. Then inspect it on the model, not only
as a flat image.

Check:

- Whether the material reads correctly from different angles
- Whether important details land on the intended surfaces
- Whether seams or UV boundaries are distracting
- Whether the scale of the pattern feels right
- Whether the colors work under the target lighting

If the direction is wrong, revise the prompt and generate again before spending
tokens on secondary map extraction.

## Step 6: Extract PBR maps

After approving Base Color, open the PBR Material workflow. TextureFast
generates:

- Albedo / Base Color
- Normal
- Height
- Roughness
- Metallic
- Ambient Occlusion

You can generate maps individually or use one-click full material generation on
eligible plans. Check the live product UI for current plan access, limits, and
resolution options.

## Step 7: Download the maps

Download individual PNG maps or a material package where the current workflow
supports it. PNG output is intended to work with common DCC and game-engine
pipelines.

Keep map names organized by asset and material. For batch work, use a consistent
folder and naming convention before importing into your project.

## Step 8: Import into Blender

In Blender, assign the maps to the Principled BSDF:

- Base Color / Albedo → Base Color
- Normal → Normal Map node, then Normal
- Roughness → Roughness or Smoothness, according to the shader
- Metallic → Metallic
- Height → Bump or displacement workflow if needed
- AO → optional occlusion treatment depending on the shader

The free TextureFast Blender add-on can generate and wire maps inside Blender
without a browser round trip:

1. Download the ZIP from https://texturefast.com/blender-addon.
2. Install it through Blender Preferences.
3. Enable the add-on.
4. Open the N-panel and TextureFast tab.
5. Sign in with the browser device-code flow.
6. Select a UV-unwrapped object and generate.

## Step 9: Import into Unity

For a Unity URP or HDRP workflow:

1. Drop the PNG files into the Unity `Assets` folder.
2. Mark the Normal texture as a Normal Map in its import settings.
3. Create a Lit material.
4. Assign Base Color to Base Map.
5. Assign Normal to the Normal Map slot.
6. Map Roughness according to your shader setup. Unity commonly uses
   Smoothness, so invert or remap Roughness when required.
7. Use Height and AO only when your shader and performance budget support them.

Use lower resolutions for distant or mobile assets and reserve higher
resolutions for hero objects.

## Step 10: Import into Unreal Engine

For Unreal Engine:

1. Import the mesh and PNG textures into the project.
2. Create or reuse a master Material.
3. Expose texture parameters.
4. Create a Material Instance for the asset.
5. Connect Base Color, Normal, and Roughness to the appropriate inputs.
6. Add Height or AO according to the features in your material.

Material Instances make it easier to apply the same structure across many
props. Test Roughness under the lighting used in the level rather than judging
it only from a thumbnail.

## Step 11: Iterate and refine

TextureFast is built for exploring directions quickly. Final validation still
belongs in the target application.

Use a loop:

1. Generate at a practical preview resolution.
2. Inspect on the model.
3. Test under representative lighting.
4. Adjust the prompt or UVs.
5. Generate the approved direction at the required resolution.
6. Extract only the maps needed by the final shader.

Hero assets may still benefit from hand-painted refinement in Blender,
Substance, Photoshop, or another texture editor.

## Common problems

### The model has no texture or generation fails

Check that the model has valid UV coordinates and that the exported file
actually includes them.

### The texture is stretched

Improve the UV unwrap and texel-density distribution. TextureFast follows the
UV layout you provide.

### The material looks noisy

Simplify the prompt, describe larger readable forms, and inspect the model at
the distance where it will be used.

### The result looks good flat but bad in 3D

Rotate the model and check seams, scale, and detail placement. Always judge a
texture on the model and in the target renderer.

### A required map is missing

Check current plan access and the live PBR Material tab if a map or resolution
option is unavailable.

## Next steps

- [TextureFast FAQ](faq.md)
- [TextureFast for game developers](for/game-developers.md)
- [TextureFast for ArchViz artists](for/archviz-artists.md)
- Official Blender add-on page: https://texturefast.com/blender-addon
- Official pricing page: https://texturefast.com/pricing
