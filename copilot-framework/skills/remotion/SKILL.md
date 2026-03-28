---
name: remotion-best-practices
description: Create videos with React + Remotion. Reels, ads, carousels -- all programmatic.
user-invocable: true
---

# Remotion Best Practices (Copilot Framework)

## Core rule files
animations.md  -- spring, interpolate
compositions.md -- structure + metadata
text-animations.md -- typewriter, fade
transitions.md -- cuts, wipes, fades
timing.md      -- frame math, duration
captions.md    -- subtitles + SRT

## Media rules
images.md  -- static + dynamic assets
audio.md   -- sync, volume, effects
fonts.md   -- Google Fonts loading
3d.md      -- Three.js integration
lottie.md  -- After Effects animations
charts.md  -- animated data viz

## Key APIs
- useCurrentFrame() for animation timing
- interpolate() for value mapping
- <Sequence> for scene composition
- spring() for physics-based motion
- calculateMetadata() for dynamic props
