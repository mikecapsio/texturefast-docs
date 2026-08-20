# TextureFast FAQ

## Product basics

### What is TextureFast?

TextureFast is an AI texture generator for existing UV-unwrapped 3D models.
Upload a model, describe the desired material, generate a Base Color texture,
preview it on the model, and download texture maps for use in common 3D tools
and game engines.

TextureFast focuses on texturing existing geometry. It does not generate
complete 3D meshes from scratch.

### How does TextureFast work?

TextureFast uses a two-stage workflow:

1. Load a UV-unwrapped model locally in the browser.
2. Describe the material with a prompt or supported reference input.
3. Choose a style preset and quality or resolution option.
4. Generate a Base Color texture.
5. Review the result on the 3D model.
6. Extract available PBR maps from the approved Base Color.
7. Download individual PNG maps or a material package where available.

### Who uses TextureFast?

TextureFast is designed for game developers, 3D artists, environment artists,
ArchViz and product-visualization artists, Blender users, Unity, Unreal, Godot
and Roblox creators, asset publishers, educators, students, modders, and
robot-vision or synthetic-data teams.

## Models, UVs, and formats

### Do I need a UV-unwrapped model?

Yes. UV unwrapping flattens a 3D surface into a 2D layout so the generated
texture knows where each pixel belongs. Without usable UV coordinates,
TextureFast cannot reliably align a texture to the model.

Prepare UVs in Blender, Maya, 3ds Max, or another DCC before uploading. Check
for stretching, unwanted overlaps, and insufficient island spacing.

### Which file formats are supported?

The main texturing workflow supports:

- GLB
- GLTF
- OBJ
- FBX

GLB is recommended when you want one self-contained file containing the model
and its related data. Check the live UI for current file-size limits and
tool-specific support.

### Does TextureFast generate 3D models?

No. TextureFast textures an existing model. Use a modeling or full 3D asset
generation tool first if you do not have geometry yet.

### Can AI-generated textures contain imperfections?

Yes. Results can vary with UV quality, geometry, material complexity, and prompt
clarity. Clean UVs and specific material prompts usually produce more useful
results. Always inspect the texture on the model and test it in the target
renderer or game engine.

## Generation and maps

### What is Base Color?

Base Color, also called Albedo or Diffuse in some workflows, contains the
surface color without lighting or shine baked into it. It is the foundation for
the PBR extraction workflow.

### What PBR maps are currently available?

The current live PBR extraction workflow provides:

- **Albedo / Base Color:** surface color without lighting
- **Normal:** small surface-direction detail without extra geometry
- **Height:** elevation information for parallax or displacement workflows
- **Roughness:** how matte or glossy the surface appears
- **Ambient Occlusion:** soft contact shadowing in creases and corners

Metallic extraction is currently marked as coming soon in the product UI.
Workflows that need a Metallic map should create or refine that channel in
Blender, Substance, Photoshop, or the target engine.

### How do I get Normal or Roughness maps?

Generate a Base Color first. Then open the PBR Material workflow, choose the
available maps and target resolution, and generate them individually or through
one-click full material generation on eligible plans.

### What resolution can I use?

Base Color can reach up to 4K on supported quality tiers. Current PBR
extraction uses 1K or 2K output. Resolution availability depends on the active
plan and selected workflow, so check the live dashboard before planning a
batch.

### What are style presets?

Style presets guide the overall visual direction. Available examples include
AAA Photorealistic, Handpainted, Pixel Art, and AAA Stylized. Presets help
creators keep a consistent look across props, characters, environments, or
other asset groups.

### What is prompt expansion?

Prompt expansion is an optional feature that enriches a short material
description before generation. It can help when you know the general idea but
want to provide more surface detail and material guidance.

### Can I use a reference image?

On supported plans and workflows, you can provide a reference image to guide
material, color, and surface direction. Only upload reference images you have
the right to use.

### Can I adjust Ambient Occlusion?

TextureFast provides an AO adjustment workflow with levels controls. Use it to
change the contrast and intensity of the generated ambient-occlusion result
before export.

## Privacy and data handling

### Is my 3D model uploaded?

TextureFast public product copy states that the full 3D model file is opened
and processed locally in the browser during the core texturing workflow. The
service may process derived or user-provided inputs needed by the selected
feature, such as the UV layout, prompt, reference image, Base Color, or
generated map data.

Read the current Privacy Policy for the authoritative details.

### Are prompts or assets used to train AI models?

TextureFast public product copy states that user creative assets are not used
to train AI models. Do not put passwords or other secrets in prompts, and
review your studio or client policy before using confidential material.

## Blender and game engines

### Can I use TextureFast with Blender?

Yes. You can export a UV-unwrapped model to the web app, generate maps, and
import the PNG files back into Blender. You can also use the free TextureFast
Blender add-on to generate and apply textures from inside the 3D Viewport.

### How do I install the Blender add-on?

1. Download the add-on ZIP from https://texturefast.com/blender-addon.
2. Do not extract the ZIP.
3. In Blender, open **Edit → Preferences → Add-ons → Install from Disk**.
4. Select the ZIP and enable the TextureFast add-on.
5. Press **N** in the 3D Viewport and open the TextureFast tab.
6. Sign in through the browser device-code flow.
7. Select a UV-unwrapped mesh, enter a prompt, choose settings, and generate.

The current add-on page lists Blender 4.0 or newer and support for Windows,
macOS, and Linux. Check that page for the current version and requirements.

### Can I use the output in Unity or Unreal Engine?

Yes. TextureFast exports standard PNG maps for common PBR workflows. Import the
maps into Unity URP/HDRP or Unreal Engine and assign them to the corresponding
material inputs.

Unity usually requires the Normal texture to be marked as a Normal Map. Unity
uses Smoothness where many workflows use Roughness, so invert or remap the
channel according to your shader setup.

In Unreal, connect Base Color, Normal, Roughness, and other available channels
through your master material or Material Instance. Height and AO depend on the
shader features enabled in your project.

### Can I use TextureFast with Godot?

Yes. Standard PNG PBR maps can be imported into Godot workflows such as
StandardMaterial3D. Check the current Godot version and project shader setup
for the exact channel mapping.

## Pricing, tokens, and rights

### How does the token system work?

TextureFast uses token-based usage on subscription plans. Base Color generation
and PBR map extraction consume tokens according to the selected workflow,
quality, and resolution. The dashboard shows the current balance and plan
limits.

### Can I use generated textures commercially?

Commercial-use rights depend on the active plan and the current Terms of
Service. Check the live pricing page and legal terms before using generated
assets in client work, games, films, advertisements, marketplaces, or other
revenue-generating projects.

### Is there a free Blender add-on?

Yes. The Blender add-on itself is free. Texture generation uses the tokens and
plan access associated with your TextureFast account.

### How do I cancel or change a subscription?

Use the account billing or subscription-management options shown in the
TextureFast dashboard. Current cancellation, renewal, and plan-change terms are
defined by the live pricing and account pages.

## Specialized workflows

### Can I create Roblox clothing?

Yes. The Roblox clothes workflow generates shirt and pants textures, previews
them on R6 or R15 block avatars, and exports a 585×559 PNG for the classic
clothing workflow.

TextureFast does not upload clothing to Roblox for you. You remain responsible
for Roblox rules, account permissions, moderation, originality, and rights to
any logos or other graphics.

### Can I create CS2 weapon skins?

Yes. The CS2 workflow lets you choose a weapon preset, describe the finish,
preview the result on a weapon model, and export texture maps for the CS2
Workshop preparation workflow.

TextureFast does not submit skins to the Workshop. Final polishing,
packaging, screenshots, submission, and compliance with current Valve
requirements remain your responsibility.

## Support

For product questions, review the official website, FAQ, pricing page, Privacy
Policy, and Terms of Service. Public support contact information is listed at
https://texturefast.com and may change over time.
