# TextureFast for ArchViz Artists

TextureFast is a privacy-first AI texture generator for ArchViz artists. The architectural model stays in the browser, and the AI sees only the UV map. It turns UV-mapped models into Base Color textures and a full PBR texture set — Albedo, Normal, Height, Roughness, Metallic, and Ambient Occlusion — for common visualization workflows.

ArchViz projects depend on believable materials: wood, stone, marble, metal, fabric, concrete, and glass. Client models are often unreleased or under NDA, so sending the mesh to a cloud generator is not an option. TextureFast lets you explore finishes on a model that never leaves your browser.

## What TextureFast delivers

- Fast exploration of wood, stone, metal, fabric, and concrete finishes
- Several material directions for the same model, up to your token allowance, without re-sending the mesh
- The client model stays local. The AI sees the UV map and your prompt, not the geometry
- Consistent material direction across rooms, furniture, and architectural elements
- Full PBR exports for Blender, 3ds Max, V-Ray, Corona, Cycles, and other compatible workflows
- Prompt-driven revision cycles without searching a stock library for every change

TextureFast does not replace final art direction, UV preparation, renderer tuning, or client approval. It does not generate meshes. It reduces the time spent reaching a useful starting direction.

## Prepare the architectural model

Start with a model from Blender, 3ds Max, a CAD cleanup workflow, or another DCC. The model needs usable UVs so the generated texture can align to the surfaces.

Before you open it:

- UV unwrap counters, flooring, facade panels, and furniture pieces.
- Check for stretching on close-up surfaces.
- Keep important visible areas free from unwanted overlaps.
- Leave padding between UV islands.
- Use sensible texel density for the final camera distance.
- Export GLB, GLTF, OBJ, or FBX with UV data included.

GLB is a good choice when you want a single self-contained file. The current web workflow accepts files up to 100 MB. A free UV check that costs no tokens: https://texturefast.com/tools/uv-map-inspector

## ArchViz workflow

### 1. Open the model

Open the TextureFast texturing workflow and select the UV-unwrapped model. Review it in the browser before generating.

The file is read locally for the preview and UV extraction and is not uploaded. Generation uses the UV map, your prompt, an optional reference image, and later the generated Base Color. Geometry stays on your machine.

### 2. Prompt by design intent

Describe the finish and its architectural context. Include:

- Material type
- Color and undertone
- Finish and gloss level
- Grain, veining, weave, or surface pattern
- Wear level
- Interior or exterior context
- Camera distance or presentation role

Leave the client name and unreleased product name out of the prompt unless your agreement allows it.

Example prompts:

> Polished white Carrara marble countertop with subtle grey veining and a satin finish for a kitchen visualization hero shot.

> Wide-plank European oak flooring with a natural oil finish, warm honey-brown color, visible grain, and light foot-traffic wear for an interior walkthrough.

> Brushed bronze curtain-wall mullions with restrained oxidation and a refined satin finish for an exterior dusk render.

### 3. Compare material directions

Generate several Base Color directions and inspect each one on the model. Compare:

- Whether the material scale is believable
- Whether grain or veining follows the intended surface
- Whether roughness reads correctly in the renderer
- Whether the color matches the project palette
- Whether repeated areas look too uniform

If a client asks for "warmer wood" or "less gloss," revise the prompt and generate a new direction on the same UV layout. The model stays local for every revision.

### 4. Extract the full PBR map set

After selecting a Base Color, use the PBR Material workflow to generate:

- Albedo / Base Color
- Normal
- Height
- Roughness
- Metallic
- Ambient Occlusion

Base Color can reach up to 4K on supported quality tiers. Check the live product UI for current plan access, limits, and resolution options.

### 5. Import into the renderer

PNG maps can be imported into standard renderer workflows:

- Base Color / Albedo → diffuse or base-color input
- Normal → normal or bump input
- Roughness → roughness or glossiness workflow, with the required inversion
- Height → displacement or bump workflow where appropriate
- Metallic → metalness input
- AO → subtle occlusion treatment when the renderer supports it

Renderer conventions differ. For example, some workflows use Glossiness instead of Roughness. Confirm the expected channel direction before rendering.

## Resolution and scene budgets

TextureFast supports Base Color up to 4K on supported tiers, but every asset does not need 4K.

A practical starting point:

- Close-up hero interiors: 2K–4K
- Midground furniture and architectural elements: 1K–2K
- Background massing and distant surfaces: lower resolution where appropriate

Keep resolution consistent within a material group and test memory use in the final scene.

## Client revision workflow

TextureFast is built for cases where the geometry and UVs stay the same while the material direction changes:

1. Generate a baseline material.
2. Render a quick lighting test.
3. Collect client feedback.
4. Translate the feedback into prompt changes.
5. Generate a revised Base Color.
6. Extract maps for the approved direction.
7. Render a comparison still.

This can reduce the time spent hunting through asset libraries. You still own scale, realism, composition, and final approval.

## Reference images

On supported plans and workflows, a reference image can guide the material direction. This is useful for a client swatch, a product reference, or a specific finish.

The reference image is processed with the UV map and the prompt. Only use images you have the right to use, and follow the client's confidentiality requirements for that image.

## Privacy and NDA work

The full 3D model is opened locally in the browser and is not uploaded. The AI sees only the UV map, your prompt, and an optional reference image. TextureFast does not train on your models, prompts, or generated textures.

That is what makes the workflow usable for unreleased products and client models that cannot go to a cloud 3D generator. It does not replace reading the current Privacy Policy, Terms of Service, and your own NDA. Commercial-use rights depend on the active plan and current legal terms. Public plans are Starter, Pro, and Ultra, with a custom Enterprise option.

## When to use another tool

Use Substance 3D Painter or Blender when a hero asset needs detailed manual painting, exact decals, custom masks, or channel-by-channel control. Those tools also keep files on your computer.

Use Substance 3D Sampler when a specific photograph or physical sample is the source of truth.

Use a scanned-material library when an existing scan matches the project better than a generated direction. You download the scan. You do not send your model.

Do not use a cloud mesh generator for a client model that is not allowed to leave your machine.

TextureFast is the material-exploration and variation layer. It works alongside Painter, Blender, Sampler, and scan libraries when you still want manual control or a real-world source.

## Recommended starting workflow

1. Export one UV-mapped architectural element and check the UVs.
2. Open it in TextureFast. It stays in the browser.
3. Generate three material directions.
4. Test the strongest result under the project's HDRI or lighting.
5. Adjust color, roughness, scale, or wear in the prompt.
6. Generate the approved direction.
7. Extract the maps needed by the renderer.
8. Reuse the prompt structure across related surfaces.

Official workflow:
https://texturefast.com/for/archviz-artists
