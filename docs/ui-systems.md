# UI Systems

**Created / first designed:** Before 2026-05-26  
**Last updated:** 2026-05-26  
**Current status:** Exists in current build / exact implementation TBC  
**Relevant docs file:** `docs/ui-systems.md`  
**Relevant files to edit:** UI screens and UI client controllers only.

## What The System Does

The game already has UI work in progress. This likely supports racing, vehicle feedback, customisation, and prototype presentation.

## Current Folder / Script Names

Exact UI folder/script names TBC.

Likely location:

```text
StarterGui
- UI screens TBC

StarterPlayer
- StarterPlayerScripts
  - UI client controllers TBC
```

## Important Attributes / Settings

Design rules:

- UI should be mobile-first.
- UI should support racing readability.
- Avoid clutter during high-speed driving.
- Use clean futuristic styling.
- Keep UI scripts client-side where appropriate.
- Keep data/config separate from UI presentation.

## Current Known Issues

- Exact UI systems are not yet documented.
- Need to confirm what UI is functional versus placeholder.
- Need to test on mobile aspect ratios.

## Confirmed Working

- UI exists in the current build.

## Still Needs Testing

- Mobile screen sizes.
- Touch controls.
- Controller support if planned.
- Race HUD clarity at speed.
- Customisation menu usability.
- Performance impact from UI effects.

## Codex Safety Notes

- Do not modify vehicle, LOD, lighting, or economy logic when working on UI unless explicitly requested.
- Keep mobile layouts readable and touch-friendly.
- Preserve working UI behaviour when only styling is requested.
