# Exploratory 3D

Human-directed, AI-assisted Blender studies by Spenser Dickerson. The emphasis is reference-led form, believable assemblies, staged visual review and inspectable delivery, not a one-prompt production claim.

## Studies

| Study | Focus |
| --- | --- |
| VANTA / 07 | Orbital helmet, profile control, fitted hose connections, mechanical detailing and blue reflective optics. |
| BRUTE / Intermediate | Organic mask shell, component-first development, leather harness routing, UVs and asymmetric surface wear. |
| BRUTE / EMBER | The same geometry remixed with yellow paint, red scars, a carbonized side, raw hide and gold/ruby optics. |

## Downloads

Download the asset bundles from [Releases](https://github.com/sdimaging/exploratory-3d/releases). Large binaries live there rather than inside git history. Extract the bundles into the same parent directory; their internal paths share the layout below.

| Bundle | Contents |
| --- | --- |
| `blender-masters.zip` | Three packed native Blender masters and BRUTE's earlier editable construction checkpoint. |
| `optimized-glb.zip` | Three standalone GLBs, with export verification reports. |
| `camera-rigs.zip` | Three 200-pose spherical Blender rigs and two BRUTE presentation setups; green includes the final-surface wire scene. |
| `presentation-case-studies.zip` | Standalone six-page BRUTE Case Study 02, original eight-page VANTA PDF, design board, both colorway hero/details, texture sheets, separate 360 movies and a synchronized BRUTE three-up comparison. |
| `texture-plates.zip` | 16 green and 20 EMBER high-resolution maps, plus VANTA's export-only PBR atlas maps. |
| `brute-green-colmap-200.zip` | 200 green BRUTE images, masks, COLMAP cameras/poses/tracked seed and verification. |
| `brute-ember-colmap-200.zip` | 200 EMBER images with matching camera sampling and complete COLMAP data. |
| `vanta-colmap-200.zip` | 200 VANTA images, masks and complete COLMAP data. |

### Trained Splats

Added 7 September 2026 as individual PLY attachments to [release v0.1.0](https://github.com/sdimaging/exploratory-3d/releases/tag/v0.1.0):

| File | Splats | Size |
| --- | ---: | ---: |
| `vanta_.ply` | 323,744 | 76,405,190 bytes |
| `brute_green_.ply` | 273,683 | 64,590,794 bytes |
| `brute_ember_.ply` | 311,336 | 73,476,902 bytes |

These are Spenser's original trained splat exports, not the untrained `seed.ply` files inside the capture datasets. The PLY headers identify Postshot v1.1.69. Binary structure and payload sizes were checked; the trained results were not visually reviewed during this upload. GitHub displays a SHA-256 digest for each attachment. The original ZIP manifest and checksums still describe the earlier Blender delivery, and the PDFs document the pre-training stage.

## Local Layout

```text
case-study/     PDFs
media/          Hero/detail images, design board, texture sheets and movies
models/         Native .blend and portable .glb assets
rigs/           Blender camera and presentation scenes
textures/       Baked PBR plates from the optional texture bundle
captures/       brute-green/, brute-ember/, vanta/
qa/             Machine-readable verification reports
```

Blender 5.2.1 LTS was used. The native files retain packed textures and Cycles materials. Choose your available render device in Blender preferences. Camera rigs contain absolute authoring output paths; choose a local render output directory when rendering on another machine. The image/pose pairs in each supplied dataset are authoritative.

## COLMAP And Splat Training

The verified delivery contains **600 images: 200 per asset, 1200 x 1200, 70 mm**, rendered in Cycles with OpenImageDenoise. Each dataset root contains `images/`, matching `masks/`, and text plus binary `sparse/0/` data. `seed.ply` contains the same untrained surface seed. All three `CAPTURE-VERIFICATION.json` reports state `complete`.

The cameras sample a full Fibonacci sphere, with per-pose distance fitted to the actual product geometry and a checked border. The asset and lighting remain fixed. This is not a smooth turntable path; separate BRUTE presentation movies use a 192-frame, 24 fps camera loop. The 3240 x 1080 three-up comparison synchronizes green, EMBER and wireframe across the same 8-second orbit.

Camera poses are known Blender ground truth exported in [COLMAP's coordinate conventions](https://colmap.github.io/format.html). Surface points are synthetic mesh samples with ray-tested observations and render-sampled colors. They are **not** recovered SfM features, nor are they trained Gaussian splats. Binary track indices and reprojections are verified independently after writing.

Open each dataset root in [LichtFeld Studio](https://github.com/MrNeRF/LichtFeld-Studio). Reflective/transmissive optics are deliberately retained, so view-dependent appearance may need trainer tuning. Alpha-derived masks include partially transparent pixels. Training results have not been validated as part of the Blender delivery.

Spenser's trained PLY exports are now available separately under Trained Splats above. The repository remains private until an explicit public-release decision.

## Native Versus Portable

Native Cycles files are the look-development authority. GLBs use batched atlas meshes, reduced texture dimensions, packed metal/rough channels and Draco compression. BRUTE's foil thickness, transmission and emissive channels are retained using supported glTF extensions; appearance still depends on the viewer and lighting.

Optimization here does not mean game-ready retopology: each BRUTE GLB retains approximately 658k triangles, and VANTA about 1.05 million. The BRUTE working asset has 305 meshes and four texture sets. Tiny sampled UV overlaps, sliver islands and inefficient packing remain documented limits. VANTA's UVs were created on an export-only copy, leaving the native helmet unchanged.

Wireframe footage is labelled by scope. BRUTE shows the dense final UV-ready polygon surface. VANTA's existing wire presentation shows editable mesh cages and evaluated curve tessellation. The separate BRUTE construction checkpoint predates final leather adjustments and UV conversion; it is not a pixel-identical lower-resolution final asset.

## Provenance And Limits

The original concepts and design sheets were generated with GPT imaging. The EMBER remix reference was supplied by the user from Gemini / Nano Banana. The dragon stencil was generated as original artwork with GPT imaging. Actual Blender renders are labelled separately from those visual references.

VANTA uses [Machine Shop 03 by Oliksiy Yakovlyev / Poly Haven](https://polyhaven.com/a/machine_shop_03), a CC0 lighting environment. Generated maps and procedural/baked derivatives are recorded in the original study notes and packed source files.

These are static concept assets, not validated protective equipment, manufacturing models, complete LOD sets or rigged functional mechanisms. No open-source license is granted by this private handoff; choose licensing deliberately before any public release.
