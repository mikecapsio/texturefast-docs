# TextureFast for ArchViz Artists

ArchViz projects depend on believable materials: wood, stone, marble, metal,
fabric, concrete, and glass. Client revisions can make material sourcing
expensive when every change requires a new scan, a new asset purchase, or
another manual texturing pass.

TextureFast helps ArchViz artists explore material directions on their own
UV-mapped models and export standard PNG maps for common visualization
workflows.

## What TextureFast helps with

- Fast exploration of wood, stone, metal, fabric, and concrete finishes
- Material variations for client presentations
- Consistent material direction across rooms, furniture, and architectural
  elements
- PBR-oriented exports for Blender, 3ds Max, V-Ray, Corona, Cycles, and other
  compatible workflows
- Prompt-driven revision cycles without searching a stock library for every
  change
- Local model handling during the core browser workflow

TextureFast does not replace final art direction, UV preparation, renderer
tuning, or client approval. It reduces the cost of reaching a useful starting
direction.

## Prepare the architectural model

Start with an existing model from Blender, 3ds Max, a CAD cleanup workflow, or
another DCC. The model needs usable UVs so the generated texture can align to
the surfaces.

Before uploading:

- UV unwrap counters, flooring, facade panels, and furniture pieces.
- Check for stretching on close-up surfaces.
- Keep important visible areas free from unwanted overlaps.
- Use sensible texel density for the final camera distance.
- Export GLB, GLTF, OBJ, or FBX with UV data included.

GLB is recommended when you want a single self-contained file.

## ArchViz workflow

### 1. Upload the model

Open the TextureFast texturing workflow and upload the UV-unwrapped model.
Review the model in the browser before generating.

The core workflow opens the full model locally for preview and UV handling.
The selected generation feature may process derived inputs such as the UV
layout, prompt, reference image, Base Color, or generated map data.

### 2. Prompt by design intent

Describe the finish and its architectural context. Include:

- Material type
- Color and undertone
- Finish and gloss level
- Grain, veining, weave, or surface pattern
- Wear level
- Interior or exterior context
- Camera distance or presentation role

Example prompts:

> Polished white Carrara marble countertop with subtle grey veining and a satin
> finish for a kitchen visualization hero shot.

> Wide-plank European oak flooring with a natural oil finish, warm honey-brown
> color, visible grain, and light foot-traffic wear for an interior walkthrough.

> Brushed bronze curtain-wall mullions with restrained oxidation and a refined
> satin finish for an exterior dusk render.

### 3. Compare material directions

Generate several Base Color directions and inspect each one on the model.
Compare:

- Whether the material scale is believable
- Whether grain or veining follows the intended surface
- Whether roughness reads correctly in the renderer
- Whether the color matches the project palette
- Whether repeated areas look too uniform

If a client asks for “warmer wood” or “less gloss,” revise the prompt and
generate a new direction on the same UV layout.

### 4. Extract the available PBR maps

After selecting a Base Color, use the PBR Material workflow to generate:

- Albedo / Base Color
- Normal
- Height
- Roughness
- Ambient Occlusion

Current PBR extraction uses 1K or 2K output. Base Color can reach up to 4K on
supported quality tiers.

Metallic extraction is currently marked as coming soon. For bronze, steel,
aluminum, or other metal surfaces, set or refine the Metallic value in the
target renderer or DCC.

### 5. Import into the renderer

PNG maps can be imported into standard renderer workflows:

- Base Color / Albedo → diffuse or base-color input
- Normal → normal or bump input
- Roughness → roughness or glossiness workflow, with the required inversion
- Height → displacement or bump workflow where appropriate
- AO → subtle occlusion treatment when the renderer supports it

Renderer conventions differ. For example, some workflows use Glossiness
instead of Roughness. Confirm the expected channel direction before rendering.

## Resolution and scene budgets

TextureFast supports Base Color up to 4K on supported tiers, but every asset
does not need 4K.

A practical starting point:

- Close-up hero interiors: 2K–4K
- Midground furniture and architectural elements: 1K–2K
- Background massing and distant surfaces: lower resolution where appropriate

Keep resolution consistent within a material group and test memory use in the
final scene.

## Client revision workflow

TextureFast is useful when the geometry and UVs stay the same while the material
direction changes:

1. Generate a baseline material.
2. Render a quick lighting test.
3. Collect client feedback.
4. Translate the feedback into prompt changes.
5. Generate a revised Base Color.
6. Extract maps for the approved direction.
7. Render a comparison still.

This can reduce the time spent hunting through asset libraries, while keeping
the artist responsible for scale, realism, composition, and final approval.

## Reference images

On supported plans and workflows, a reference image can guide the material
direction. This is useful for a client swatch, a product reference, or a
specific finish.

Only upload images you have the right to use. Treat reference images as
production assets and follow the client's confidentiality requirements.

## Privacy and NDA work

TextureFast public product copy states that the full 3D model is opened and
handled locally in the browser during the core texturing workflow. It also
states that creative assets are not used to train AI models.

This is useful for projects involving unreleased products or client work, but
it is not a replacement for reviewing the current Privacy Policy, Terms of
Service, and your own NDA obligations. Commercial-use rights depend on the
active plan and current legal terms.

## When to use another tool

Use Substance 3D Painter or Blender when a hero asset needs detailed manual
painting, exact decals, custom masks, or channel-by-channel control.

Use Substance 3D Sampler when a specific photograph or physical sample is the
source of truth.

Use a scanned-material library when an existing scan matches the project
better than a generated direction.

TextureFast fits the material exploration and variation stage, and can work
alongside each of these tools.

## Recommended starting workflow

1. Export one UV-mapped architectural element.
2. Generate three material directions.
3. Test the strongest result under the project's HDRI or lighting.
4. Adjust color, roughness, scale, or wear in the prompt.
5. Generate the approved direction.
6. Extract the maps needed by the renderer.
7. Reuse the prompt structure across related surfaces.

Official workflow:
https://texturefast.com/for/archviz-artists
