# BD Replay

BD Replay is a V1 phone-based spatial memory replay platform.

The concept is simple: a user records a place, room, street, object, or moment with their phone, uploads the media, and receives an interactive 3D replay they can explore from different perspectives in the browser.

This project does not claim neural capture, emotion replay, or brain scanning. It is a visual spatial replay MVP built with current web technology.

## Product Vision

BD Replay turns ordinary phone footage into an explorable memory scene.

The first version focuses on:

- Phone capture
- Photo/video upload
- A guided reconstruction workflow
- Interactive replay in the browser
- Original camera-path playback
- Free-camera exploration
- First-person and orbit viewing modes
- A futuristic but usable interface

The long-term direction is a consumer-friendly spatial memory product: capture a place once, then revisit it from angles you did not originally film.

## V1 Scope

This repository starts with a frontend-only MVP. It uses mocked processing and a placeholder 3D viewport so the full user flow can be tested before integrating the real reconstruction backend.

Included pages:

- `/` landing page
- `/capture` phone capture guide
- `/upload` upload flow
- `/processing/[id]` mocked reconstruction progress
- `/replay/[id]` interactive replay viewer shell
- `/library` saved replay list
- `/settings` placeholder settings page

Included components:

- `BDLayout`
- `NeonPanel`
- `ReplayViewport`
- `TimelineScrubber`
- `TelemetryPanel`
- `CaptureGuide`
- `UploadDropzone`
- `ProcessingPipeline`
- `ReplayLibrary`
- `CameraModeToggle`
- `ShareReplayDialog`

## Current Tech Stack

- Next.js 14+
- TypeScript
- Tailwind CSS
- React
- LocalStorage mock persistence

Planned backend stack:

- Supabase/Postgres for database and auth
- S3 or Cloudflare R2 for object storage
- Python/FastAPI or Node workers for processing
- FFmpeg for frame extraction
- COLMAP for camera pose estimation
- 3D Gaussian Splatting pipeline for reconstruction
- Three.js or React Three Fiber for rendering
- WebXR-ready viewer architecture

## UX Principles

The main UI avoids technical reconstruction terms. Users should see plain language such as:

- Building your replay
- Mapping camera movement
- Reconstructing the scene
- Optimizing replay
- Ready to explore

The visual style is futuristic noir and 2077-adjacent without copying protected game assets, logos, typography, layouts, or exact interface elements. The intended feel is a high-end memory forensics tool: dark panels, amber/red/cyan accents, thin borders, scanline texture, subtle glitch transitions, telemetry, and cinematic HUD overlays.

## Reconstruction Pipeline Plan

The real pipeline should look like this:

```text
Phone video/photos
  -> upload to object storage
  -> extract frames with FFmpeg
  -> estimate camera poses with COLMAP
  -> train Gaussian Splat scene
  -> export viewer asset
  -> render in browser
  -> replay original camera path or detach into free camera
```

## Development

Install dependencies:

```bash
npm install
```

Run locally:

```bash
npm run dev
```

Open:

```text
http://localhost:3000
```

## Important Notes

This V1 is visual spatial replay only.

No fake brain scanning.
No emotion capture.
No neural interface claims.

The product should feel like the first real consumer version of braindance-style spatial replay using tools that can actually be built today.
