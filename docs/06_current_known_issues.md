# Current Known Issues

This file is intentionally conservative. Items are included only when they were mentioned in the chat or are reasonable verification steps after recent changes.

## Needs Play-Test Confirmation

- `V75` boost recharge delay and hover wobble were generated after `V74`, but no later user confirmation is present in this chat history.
- Confirm that `BoostRechargeDelay` is being read from installed Boost modules at runtime.
- Confirm that low-speed wobble is subtle enough and fades out by `20 MPH`.
- Mobile auto-sprint is prepared in `scripts/roblox_character_sprint_controller_install.lua`; verify on a mobile device/emulator that `MobileSprintMoveThreshold` feels right.

## Camera

Resolved direction:

- Avoid fully scriptable chase camera every frame. It caused jitter and did not feel like the desired pre-V72 camera.
- Keep Roblox default vehicle camera as the base.
- Use a light assist for FOV and soft recentering.

Watch for:

- Camera assist fighting any older camera script.
- On-foot sprint FOV fighting vehicle camera assist if the player enters a vehicle while sprinting.
- Mobile touch camera input overlapping driving controls.
- FOV not restoring after exit.

## Character Movement

Recently confirmed:

- Character sprint install worked after running `scripts/roblox_character_sprint_controller_install.lua`.
- The user moved/renamed the live runtime hierarchy to include `CharacterSprintController_Active`, `DriveHudController_Active`, `MobileDriveControlsController_Active`, and `RuntimeVFXController_Active` under `StarterPlayer.StarterPlayerScripts.NeoTokyoRacersClient.Controllers.Runtime`.
- A blocked third-party sprint animation asset warning was resolved by disabling/replacing the custom `AnimationId`; Roblox's normal character animation still looked fine.

Watch for:

- The previous placeholder animation attempt may have left `StarterPlayer.StarterCharacterScripts.NTR_CharacterSprintDefaults` in Studio. The sprint installer removes it automatically.
- A custom sprint animation must be an uploaded Roblox `Animation` asset usable by the place owner/group. KeyframeSequences, Animator object IDs, and unshared third-party assets will not work directly.
- If `AnimationId` fails to load, set it to `rbxassetid://0` or a permitted animation asset. Sprint speed should still work even without a custom sprint animation.
- Mobile auto-sprint uses Roblox's standard `PlayerModule` move vector first, then falls back to `Humanoid.MoveDirection`. Verify on an actual mobile device/emulator that the threshold feels like "full push" rather than triggering too early.
- After future edits, confirm the sprint controller does not leave the humanoid at sprint speed after death, respawn, sitting, or exiting a vehicle.

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
