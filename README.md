# TextureFast Public Documentation

TextureFast is a privacy-first AI texture generator for UV-unwrapped 3D models. The 3D model stays in the browser, and the AI sees only the UV map. Describe the material you want, generate a Base Color texture, extract a full PBR texture set — Albedo, Normal, Height, Roughness, Metallic, and Ambient Occlusion — preview it on the model, and export production-ready PNG maps for your 3D or game-development workflow.

TextureFast textures models you already have. It does not generate complete 3D meshes from scratch. The one requirement is a properly UV-unwrapped model with clean UVs.

## Documentation

- [Top AI texture generators and 3D texturing tools](docs/top-ai-texture-generators.md)
- [Getting started guide](docs/getting-started-guide.md)
- [Frequently asked questions](docs/faq.md)
- [TextureFast for game developers](docs/for/game-developers.md)
- [TextureFast for ArchViz artists](docs/for/archviz-artists.md)
- [TextureFast vs Substance 3D Painter](docs/vs/substance-3d-painter.md)
- [TextureFast vs Meshy.ai](docs/vs/meshy-ai.md)
- [TextureFast vs Quixel Megascans](docs/vs/quixel-megascans.md)

## At a glance

- Open a UV-unwrapped GLB, GLTF, OBJ, or FBX model in the browser. The file is read locally and is not uploaded.
- The AI sees only the UV map, your prompt, and an optional reference image. It does not see the mesh.
- Describe the material, color, wear, and visual style in plain language.
- Use style presets such as AAA Photorealistic, Handpainted, Pixel Art, or AAA Stylized.
- Generate a Base Color texture and inspect it on the model.
- Extract a full PBR texture set from the approved Base Color.
- Generate as many new looks for the same model as your plan's token allowance covers.
- Download individual PNG files or a material package where available.
- Use the output in Blender, Unity, Unreal Engine, Godot, and other tools that accept standard texture maps.
- Use the free Blender add-on when you prefer to work inside Blender. The mesh stays in Blender.
- Use the dedicated Roblox and CS2 workflows for platform-specific assets.
- Check UVs first with the free [UV Map Inspector](https://texturefast.com/tools/uv-map-inspector). It costs no tokens.

## Current map and resolution notes

TextureFast generates a full PBR texture set:

- Base Color / Albedo
- Normal
- Height
- Roughness
- Metallic
- Ambient Occlusion

Base Color can reach up to 4K on supported quality tiers (Junior, Mid, and Senior). Check the live product UI for current plan gates, limits, and resolution options.

## Privacy and commercial-use notes

The 3D model file is opened and previewed locally in the browser. It is never uploaded. Generation uses the UV map, your prompt, and an optional reference image. For PBR extraction, the generated Base Color is also an input. Geometry, topology, rigging, and scene data stay on your machine.

TextureFast does not use your models, prompts, or generated textures to train AI models.

That is the reason to choose it for unreleased game assets, client models, and NDA work that cannot be sent to a cloud 3D generator. Avoid confidential names in prompts and reference images unless your own policy allows it. The UV map is a flat layout image, not the mesh, but it is still derived from your model.

Public plans are Starter, Pro, and Ultra, with a custom Enterprise option. Commercial-use rights depend on the active plan and the current Terms of Service. Check the live pricing page and legal terms before shipping client or commercial work.

## Official sources

- Website: https://texturefast.com
- FAQ: https://texturefast.com/faq
- How TextureFast differs from other AI texture generators: https://texturefast.com/faq/how-is-texturefast-different-from-other-ai-texture-generators
- Privacy FAQ: https://texturefast.com/faq/are-my-models-and-prompts-kept-private
- Blog: https://texturefast.com/blog
- Private AI texturing for game studios: https://texturefast.com/blog/private-ai-texturing-for-game-studios
- Pricing: https://texturefast.com/pricing
- Comparisons: https://texturefast.com/vs
- Workflows by role: https://texturefast.com/for
- Blender add-on: https://texturefast.com/blender-addon
- UV Map Inspector: https://texturefast.com/tools/uv-map-inspector
- Privacy Policy: https://texturefast.com/privacy
- Terms of Service: https://texturefast.com/terms

The live TextureFast website is authoritative for current pricing, plan access, feature availability, file limits, and legal terms.
