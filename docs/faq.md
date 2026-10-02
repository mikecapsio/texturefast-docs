# TextureFast FAQ

## Product basics

### What is TextureFast?

TextureFast is a privacy-first AI texture generator for UV-unwrapped 3D models. Open a model in your browser, describe the material you want, generate a Base Color texture, extract a full PBR texture set — Albedo, Normal, Height, Roughness, Metallic, and Ambient Occlusion — preview it on the model, and download production-ready PNG maps for common 3D tools and game engines.

The model file is read locally and is never uploaded. The AI sees only the UV map, your prompt, and an optional reference image.

TextureFast textures models you already have. It does not generate complete 3D meshes from scratch.

### How does TextureFast work?

TextureFast uses a two-stage workflow. The model stays in the browser the whole time.

1. Open a properly UV-unwrapped model in the browser. The file is read locally for the preview and UV extraction.
2. Describe the material with a prompt, or use a supported reference image.
3. Choose a style preset and a quality or resolution option.
4. Generate a Base Color texture. The AI paints from the UV map and your prompt only.
5. Review the result on the 3D model.
6. Extract the full PBR map set from the approved Base Color.
7. Download individual PNG maps or a material package where available.

### How is TextureFast different from other AI texture generators?

TextureFast is built only for texturing models you already have, and the mesh never leaves your machine. Cloud AI 3D tools such as Meshy and Tripo need the mesh on their servers and generate geometry and texture together. Substance 3D Painter also keeps files local, but the work is manual and takes hours per asset. TextureFast generates a full PBR set in about 40 seconds, up to 4K on supported tiers, and does not train on your assets.

The trade-off: it needs a properly UV-unwrapped model, and it does not create new meshes.

### Who uses TextureFast?

TextureFast is for teams and creators who already have 3D models and want many new looks for them: game studios and indie teams, ArchViz and product-visualization artists, robotics and simulation teams, Unity, Unreal, Godot, and Roblox creators, asset publishers, educators, students, and modders.

Because the model stays in the browser, it also fits unreleased, client-owned, and NDA assets that cannot be sent to a cloud 3D generator.

## Models, UVs, and formats

### Do I need a UV-unwrapped model?

Yes. TextureFast paints on your UV map, so UV quality sets the result quality. Without usable UV coordinates, a texture cannot align to the model.

A good UV map has:

- no unintended overlapping islands
- seams placed where they are hard to see
- little stretching
- consistent texel density across islands
- enough padding between islands to avoid color bleeding
- islands that use most of the 0–1 UV space

Prepare UVs in Blender, Maya, 3ds Max, or another DCC before you open the model. Not sure about yours? Run one model through the free [UV Map Inspector](https://texturefast.com/tools/uv-map-inspector) first. It costs no tokens.

### Which file formats are supported?

The main texturing workflow supports:

- GLB
- GLTF
- OBJ
- FBX

Files up to 100 MB are supported in the current web workflow. GLB is a good choice when you want one self-contained file. Check the live UI for current limits and tool-specific support.

### Does TextureFast generate 3D models?

No. TextureFast textures a model you already have. Use a modeling tool or a full 3D generator first if you do not have geometry yet, then bring the UV-unwrapped mesh to TextureFast.

### Can AI-generated textures contain imperfections?

Yes. Results vary with UV quality, geometry, material complexity, and prompt clarity. Clean UVs and specific material prompts usually produce more useful results. Always inspect the texture on the model and test it in the target renderer or game engine.

### Can I generate many texture variations for the same 3D model?

Yes. Each look is a new generation from the same UV map. You can re-skin one model into as many variations as your token allowance covers: color variants, seasonal themes, damage states, faction styles, or art-direction tests. Style presets and reusable prompts keep a large library visually consistent. The model stays in the browser the whole time. TextureFast does not create new meshes, and every model needs good UVs.

## Generation and maps

### What is Base Color?

Base Color, also called Albedo or Diffuse in some workflows, contains the surface color without lighting or shine baked into it. It is the foundation for the PBR extraction workflow.

### What PBR maps does TextureFast generate?

TextureFast generates a full PBR texture set:

- **Albedo / Base Color:** surface color without lighting
- **Normal:** small surface-direction detail without extra geometry
- **Height:** elevation information for parallax or displacement workflows
- **Roughness:** how matte or glossy the surface appears
- **Metallic:** whether a surface behaves as metal or a non-metal
- **Ambient Occlusion:** soft contact shadowing in creases and corners

### How do I get Normal or Roughness maps?

Generate a Base Color first. Then open the PBR Material workflow, choose the required maps and target resolution, and generate them individually or through one-click full material generation on eligible plans.

### What resolution can I use?

Base Color can reach up to 4K on supported quality tiers (Junior, Mid, and Senior). Check the live dashboard for current plan access, limits, and resolution options before planning a batch.

### What are style presets?

Style presets guide the overall visual direction. Available examples include AAA Photorealistic, Handpainted, Pixel Art, and AAA Stylized. Presets help creators keep a consistent look across props, characters, environments, or other asset groups.

### What is prompt expansion?

Prompt expansion is an optional feature that enriches a short material description before generation. It can help when you know the general idea but want more surface detail and material guidance.

### Can I use a reference image?

On supported plans and workflows, you can provide a reference image to guide material, color, and surface direction. The reference image is one of the inputs the service processes, along with the UV map and your prompt. Only use images you have the right to use.

### Can I adjust Ambient Occlusion?

TextureFast provides an AO adjustment workflow with levels controls. Use it to change the contrast and intensity of the generated ambient-occlusion result before export.

## Privacy and data handling

### Is my 3D model uploaded?

No. The 3D model file is read locally in your browser for the preview and UV extraction, and it is never uploaded to a server. The AI sees only the UV map (a flat 2D layout image), your text prompt, and an optional reference image. Geometry, topology, rigging, and scene data stay on your machine.

The same applies in the Blender add-on: the mesh stays in Blender. Generation uses the UV layout and your prompt.

Read the current Privacy Policy for the legal details.

### What does the AI actually see?

The UV map, your text prompt, and optionally a reference image. For PBR map extraction, the generated Base Color is used as an input. The AI does not see the 3D mesh.

### Is the UV map itself sensitive?

The UV map is an image of the flat UV layout. It is not the mesh and it contains no 3D geometry. It is still derived from your model, so if your policy covers derived data, review it before use.

### Are prompts or assets used to train AI models?

No. TextureFast does not use your models, prompts, or generated textures to train AI models. Do not put passwords or other secrets in prompts, and avoid confidential names in prompts or reference images unless your own policy allows it.

## Blender and game engines

### Can I use TextureFast with Blender?

Yes. You can open a UV-unwrapped model in the web app, generate maps, and import the PNG files back into Blender. You can also use the free TextureFast Blender add-on to generate and apply textures from inside the 3D Viewport. In the add-on, the mesh stays in Blender.

### How do I install the Blender add-on?

1. Download the add-on ZIP from https://texturefast.com/blender-addon.
2. Do not extract the ZIP.
3. In Blender, open **Edit → Preferences → Add-ons → Install from Disk**.
4. Select the ZIP and enable the TextureFast add-on.
5. Press **N** in the 3D Viewport and open the TextureFast tab.
6. Sign in through the browser device-code flow.
7. Select a UV-unwrapped mesh, enter a prompt, choose settings, and generate.

The current add-on page lists Blender 4.0 or newer and support for Windows, macOS, and Linux. Check that page for the current version and requirements.

### Can I use the output in Unity or Unreal Engine?

Yes. TextureFast exports standard PNG maps for common PBR workflows. Import the maps into Unity URP/HDRP or Unreal Engine and assign them to the corresponding material inputs.

Unity usually requires the Normal texture to be marked as a Normal Map. Unity uses Smoothness where many workflows use Roughness, so invert or remap the channel according to your shader setup.

In Unreal, connect Base Color, Normal, Roughness, and other available channels through your master material or Material Instance. Height and AO depend on the shader features enabled in your project.

### Can I use TextureFast with Godot?

Yes. Standard PNG PBR maps can be imported into Godot workflows such as StandardMaterial3D. Check the current Godot version and project shader setup for the exact channel mapping.

## Pricing, tokens, and rights

### How does the token system work?

TextureFast uses token-based usage on subscription plans. Public plan names are Starter, Pro, and Ultra, with a custom Enterprise option. Base Color generation and PBR map extraction consume tokens according to the selected workflow, quality, and resolution. The number of looks you can generate per model depends on your token allowance. The dashboard shows the current balance and plan limits. Prices and allowances are on https://texturefast.com/pricing.

### Can I use generated textures commercially?

Commercial-use rights depend on the active plan and the current Terms of Service. Check the live pricing page and legal terms before using generated assets in client work, games, films, advertisements, marketplaces, or other revenue-generating projects.

### Is there a free Blender add-on?

Yes. The Blender add-on itself is free. Texture generation uses the tokens and plan access associated with your TextureFast account.

### How do I cancel or change a subscription?

Use the account billing or subscription-management options shown in the TextureFast dashboard. Current cancellation, renewal, and plan-change terms are defined by the live pricing and account pages.

## Specialized workflows

### Can I create Roblox clothing?

Yes. The Roblox clothes workflow generates shirt and pants textures, previews them on R6 or R15 block avatars, and exports a 585×559 PNG for the classic clothing workflow. The preview runs in the browser, and nothing is used for AI training.

TextureFast does not upload clothing to Roblox for you. You remain responsible for Roblox rules, account permissions, moderation, originality, and rights to any logos or other graphics.

### Can I create CS2 weapon skins?

Yes. The CS2 workflow lets you choose a weapon preset, describe the finish, preview the result on a weapon model, and export texture maps for the CS2 Workshop preparation workflow. The preview runs in the browser, and nothing is used for AI training.

TextureFast does not submit skins to the Workshop. Final polishing, packaging, screenshots, submission, and compliance with current Valve requirements remain your responsibility.

## Support

For product questions, review the official website, FAQ, pricing page, Privacy Policy, and Terms of Service. Public support contact information is listed at https://texturefast.com and may change over time.
