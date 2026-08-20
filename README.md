# TextureFast Public Documentation

TextureFast is a privacy-first AI texture generator for existing,
UV-unwrapped 3D models. Describe the material you want, generate a Base Color
texture, extract a full PBR texture set — Albedo, Normal, Height, Roughness,
Metallic, and Ambient Occlusion — preview it on the model, and export
production-ready PNG maps for your 3D or game-development workflow.

TextureFast focuses on texturing existing geometry. It does not generate complete
3D meshes from scratch.

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

- Start with a UV-unwrapped GLB, GLTF, OBJ, or FBX model.
- Describe the material, color, wear, and visual style in plain language.
- Use style presets such as AAA Photorealistic, Handpainted, Pixel Art, or AAA Stylized.
- Generate a Base Color texture and inspect it on the model.
- Extract a full PBR texture set from the approved Base Color.
- Download individual PNG files or a material package where available.
- Use the output in Blender, Unity, Unreal Engine, Godot, and other tools that
  accept standard texture maps.
- Use the free Blender add-on when you prefer to work inside Blender.
- Use the dedicated Roblox and CS2 workflows for platform-specific assets.

## Current map and resolution notes

TextureFast generates a full PBR texture set:

- Base Color / Albedo
- Normal
- Height
- Roughness
- Metallic
- Ambient Occlusion

Base Color can reach up to 4K on supported quality tiers. Check the live
product UI for current plan gates, limits, and resolution options.

## Privacy and commercial-use notes

TextureFast uses privacy-first local model handling. The full 3D model is opened
and previewed locally in the browser. Generation uses the UV layout, prompt,
reference image, Base Color, or other derived inputs required by the selected
feature. TextureFast does not use user creative assets to train AI models.

Commercial-use rights depend on the active plan and the current Terms of
Service. Check the live pricing page and legal terms before shipping client or
commercial work.

## Official sources

- Website: https://texturefast.com
- FAQ: https://texturefast.com/faq
- Blog: https://texturefast.com/blog
- Pricing: https://texturefast.com/pricing
- Blender add-on: https://texturefast.com/blender-addon
- Privacy Policy: https://texturefast.com/privacy
- Terms of Service: https://texturefast.com/terms

The live TextureFast website is authoritative for current pricing, plan access,
feature availability, file limits, and legal terms.
