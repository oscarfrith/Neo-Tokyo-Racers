# Customisation System

**Created / first designed:** Before 2026-05-26  
**Last updated:** 2026-05-26  
**Current status:** Exists in current build / exact implementation TBC  
**Relevant docs file:** `docs/customisation-system.md`  
**Relevant files to edit:** Customisation UI, customisation configs, vehicle cosmetic scripts only.

## What The System Does

The project already has some form of vehicle customisation, intended to support modular futuristic hover vehicles that players can personalise.

This is part of the core fantasy of Neo Tokyo Racers:

- Build / own a futuristic hover racer.
- Race through a neon city.
- Upgrade or customise the vehicle over time.

## Current Folder / Script Names

Exact folder/script names TBC.

Known current-build note:

- Customisation already exists in the project in some form.

Likely systems needing documentation:

```text
ReplicatedStorage
- Shared / Config / VehicleParts TBC

StarterGui
- Customisation UI TBC

ServerScriptService
- Customisation server validation TBC
```

## Important Attributes / Settings

Current exact attributes TBC.

Design rules:

- Keep customisation prototype-friendly.
- Avoid overbuilding economy/progression too early.
- Avoid real brands or copyrighted references.
- Use fictional brands and original visual identity.
- Separate visual customisation from vehicle physics until the base game is stable.
- Ensure customisation choices are replicated safely.

## Current Known Issues

- Exact implementation needs documenting.
- Need to identify which customisation features are currently functional.
- Need to confirm whether customisation is saved, temporary, or UI-only.
- Need to confirm whether customisation affects performance or physics.

## Confirmed Working

- Customisation exists in the current build.
- Fictional companies/images are already part of the project direction.
- The feature is considered part of the current prototype identity.

## Still Needs Testing

- Multiplayer replication.
- Save/load behaviour.
- Reset/respawn behaviour.
- Performance with customised vehicles.
- Mobile UI usability.
- Whether custom parts affect collisions or vehicle handling.
- Whether all cosmetics are original and IP-safe.

## Codex Safety Notes

- Do not edit driving physics when changing cosmetic customisation unless explicitly requested.
- Do not assume save/load behaviour exists until it is verified in Studio.
- Avoid real brands, real car names, or copyrighted references.
