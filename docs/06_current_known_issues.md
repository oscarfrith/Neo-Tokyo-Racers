# Current Known Issues

This file is intentionally conservative. Items are included only when they were mentioned in the chat or are reasonable verification steps after recent changes.

## Needs Play-Test Confirmation

- `V75` boost recharge delay and hover wobble were generated after `V74`, but no later user confirmation is present in this chat history.
- Confirm that `BoostRechargeDelay` is being read from installed Boost modules at runtime.
- Confirm that low-speed wobble is subtle enough and fades out by `20 MPH`.

## Camera

Resolved direction:

- Avoid fully scriptable chase camera every frame. It caused jitter and did not feel like the desired pre-V72 camera.
- Keep Roblox default vehicle camera as the base.
- Use a light assist for FOV and soft recentering.

Watch for:

- Camera assist fighting any older camera script.
- Mobile touch camera input overlapping driving controls.
- FOV not restoring after exit.

## UI

Recently confirmed:

- Dealership Intro Phases 1-7 were installed and reported working on 2026-06-03.
- The full dealership menu opens from `GarageDeskTrigger` instead of immediately on spawn.
- The first-menu Exit button closes the menu and the menu reopens after leaving and re-entering the desk zone.

Known sensitive areas:

- Phase Q appeared to restore garage/UI startup; confirm it still loads after a fresh Studio restart.
- The dealership intro markers are editable Studio placement controls; keep `Workspace.NeoTokyoRacersWorld.Dealership.Intro` and `Workspace.NeoTokyoRacersWorld.Dealership.Spawn.VehicleExitSpawnPoint` positioned after world/layout changes.
- Dealership Intro Phases 3-7 are guarded source-text patches; if the active bootstrap or intro client is regenerated, rerun audits before applying new dealership patches.
- In multiplayer/local server testing, confirm `Workspace._NTR_ClientOnly.VehiclePreview` is visible only on the owning client.
- Mobile dealership scaling.
- PC drive HUD hiding on mobile.
- Customisation colour sliders on mobile.
- Left customisation bar overlapping bottom UI on small screens.

## Lighting

- After running `scripts/roblox_lighting_phaseR_fogcolor_property_repair.lua`, confirm the `Lighting Fogcolor` warning no longer appears during Play startup.

## VFX

Known sensitive areas:

- Thrust colour should not flicker back to default after editing.
- Cosmetic neon and thrust-colour neon must remain separate.
- Front bumper optional neon previously did not update correctly.
- Stabiliser left/right VFX had breakage in earlier patches; verify directional drift VFX after any VFX runtime change.

## Vehicle Cockpit Lights

- Front/rear long-range car lights are intentionally deferred after the Phase S-AH experiments did not produce an acceptable result.
- Run `scripts/roblox_vehicle_phaseAI_remove_cockpit_light_systems.lua` in Studio if any cockpit-light helper output or objects remain.
- After Phase AI, Play output should not show any `[NTR Vehicle Phase U/Y/Z/AG/AH]` cockpit-light runtime messages.
- Do not rerun the removed cockpit light phases unless deliberately restoring an old experiment from Git history.

## Data/Folders

Known sensitive areas:

- Buyable modules need valid `Price` attributes.
- Boost modules should have `Boost`, `BoostDuration`, `BoostRecharge`, and `BoostRechargeDelay`.
- Module folder shape should stay simple and not reintroduce redundant colour-channel folders.
