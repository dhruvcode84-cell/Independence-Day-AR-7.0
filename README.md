# UPICON Production WebAR

A static, GitHub Pages-ready Independence Day WebAR experience built with MindAR and Three.js.

## Included

- Enterprise landing page
- QR entry flow
- Image-target WebAR
- Bundled GLB models: India Gate, Ashoka Chakra and stage
- Animated shader-based Indian flag
- Floating MD video screen
- Greeting panel, tricolour trails and particles
- Responsive mobile interface
- Demo video and UPICON branding

## Required before AR tracking

Compile `assets/card.png` using the MindAR Image Target Compiler. Download the generated target file, rename it to `card.mind`, and put it inside `assets/`.

Final structure:

```text
assets/
  card.png
  card.mind
  md-demo.mp4
  upicon-logo.png
  qr-code.png
  models/
    india-gate.glb
    ashoka-chakra.glb
    stage.glb
```

## Local test

```bash
npx serve .
```

Open the localhost address. Camera access works on localhost or HTTPS.

## GitHub Pages

1. Create a public repository named `upicon-webar-production`.
2. Upload the contents of this folder directly to the repository root.
3. Go to Settings → Pages.
4. Select Deploy from a branch → `main` → `/ (root)`.
5. Open the generated Pages URL.

The included QR currently points to:

```text
https://dhruvcode84-cell.github.io/upicon-webar-production/?source=qr
```

Regenerate `assets/qr-code.png` if your repository URL is different.

## Replace demo video

Replace `assets/md-demo.mp4` with the actual MD video while keeping the same filename. Recommended: H.264 MP4, 16:9, 720p/1080p, under 15 MB.


## V2 model-axis and material corrections

- Stage remains flat in the target XY plane; the previous 90-degree X rotation was removed.
- India Gate is rotated from Z-up export coordinates to Three.js Y-up coordinates.
- Stage, India Gate and Ashoka Chakra materials are overridden at runtime for consistent mobile rendering.
- Tricolour stage accents and a contact shadow were added.
