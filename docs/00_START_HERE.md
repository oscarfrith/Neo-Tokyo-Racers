# Neo Tokyo Racers Project Context

Last updated: 2026-05-28

This folder is the handoff pack for new Codex or ChatGPT sessions. Read this file first, then use the other docs only as needed.

## Current Project

Neo Tokyo Racers is a Roblox open-world hover racing game with modular hovercars. The main vehicle category currently being built is `BRUISER`.

The vehicle system is category-based: cockpits and modules inside the same category share fixed slot locations, so modules can be swapped between similar cockpits.

## Current Script State

Known from chat:

- Phase 15 successfully moved live server action ownership to `ServerScriptService.NeoTokyoRacers.Services.Garage.GarageActionController_Shadow_Disabled`. The old `HOVER_RACING_V2_Server` remains available for rollback but is no longer the live server action owner.
- `V74` restored the pre-V72/default Roblox driving camera feel and added a light camera assist. The user confirmed this worked well.
- `V75` was generated next to add boost recharge delay and low-speed hover wobble. At the time of writing, no later user confirmation is present in this chat history.

Recommended baseline:

- Server action owner baseline: `GarageActionController_Shadow_Disabled` is currently the tested live owner after Phase 15.
- Use `scripts/roblox_hover_racing_v74_pre_v72_camera_assist.lua` if camera stability is the priority.
- Use `scripts/roblox_hover_racing_v75_boost_delay_hover_wobble.lua` as the latest generated patch, then play-test fresh in Roblox Studio.

## Important Working Style

- Prefer small command-bar scripts that modify one system at a time.
- Do not create in-game backup copies unless explicitly asked. Roblox version history is the preferred backup.
- Avoid large fragile patches against the main client script when a ModuleScript replacement or config folder can solve it.
- If a patch depends on a specific older script shape and may fail, say that before writing the script.

## Quick Links

- Current mechanics index: `docs/current-mechanics.md`
- Architecture reorganisation plan: `docs/architecture-reorganisation-plan.md`
- Game overview: `docs/01_game_overview.md`
- Vehicle folders/assets: `docs/02_vehicle_folder_system.md`
- Driving mechanics: `docs/03_driving_mechanics.md`
- Customisation UI: `docs/04_customisation_ui.md`
- VFX system: `docs/05_vfx_system.md`
- Known issues: `docs/06_current_known_issues.md`
- Patch history: `docs/07_patch_history.md`
- Script source sync workflow: `docs/10_script_source_sync_workflow.md`
- Manual script copy map: `docs/11_manual_script_copy_map.md`
- Script architecture review: `docs/script-architecture-review-2026-05-28.md`
- Phase 5 UI migration plan: `docs/phase5-ui-migration-plan-2026-05-28.md`
- Phase 7 shared UI helpers: `docs/phase7-shared-ui-helpers-2026-05-28.md`
- Phase 8 client UI controller scaffold: `docs/phase8-client-ui-controller-scaffold-2026-05-28.md`
- Phase 9 server services scaffold: `docs/phase9-server-services-scaffold-2026-05-28.md`
- Phase 10 runtime controller scaffold: `docs/phase10-runtime-controller-scaffold-2026-05-28.md`
- Phase 11 architecture readiness audit: `docs/phase11-architecture-readiness-audit-2026-05-28.md`
- Phase 12 server action snapshot: `docs/phase12-server-action-snapshot-2026-05-28.md`
- Phase 13 server parity harness: `docs/phase13-server-parity-harness-2026-05-28.md`
- Phase 14 server shadow action controller: `docs/phase14-server-shadow-action-controller-2026-05-28.md`
- Phase 15 server action owner switch: `docs/phase15-server-action-owner-switch-2026-05-28.md`
- Compressed architecture roadmap: `docs/compressed-architecture-roadmap-2026-05-28.md`

## Diagrams

- `diagrams/vehicle_asset_system.svg`
- `diagrams/driving_runtime_system.svg`
