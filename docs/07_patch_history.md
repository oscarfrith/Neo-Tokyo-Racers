# Patch History

This is a high-level summary, not a complete changelog of every script.

## Documentation

- 2026-05-28: Added dated current mechanics docs covering vehicle, lighting, LOD, traffic lights, mobile performance, customisation, UI, race events, and open-world city systems. These docs are a reference layer for future Codex/ChatGPT sessions and should not be treated as permission to rewrite unrelated systems.
- 2026-05-28: Added target architecture reorganisation plan and Studio inventory report script for planning a safe future hierarchy migration.
- 2026-05-28: Added a dedicated Studio inventory report paste document for long Roblox Explorer hierarchy reports.
- 2026-05-28: Added hierarchy migration plan based on the pasted Studio inventory, with `Test + WIP Assets` explicitly excluded from migration.
- 2026-05-28: Added `scripts/roblox_hierarchy_phase1_architecture_resolver.lua`, a non-destructive Studio command-bar script that creates future `NeoTokyoRacers` architecture roots, adds a compatibility `PathResolver`, and mirrors key config folders without moving live systems.
- 2026-05-28: Added `scripts/roblox_hierarchy_phase2_live_references_registry.lua`, a non-destructive Studio command-bar script that adds visual ObjectValue references to current live systems and a `LiveSystemRegistry` bridge module for future targeted migrations.
- 2026-05-28: Added `scripts/roblox_studio_active_script_audit_v1.lua`, a read-only Studio command-bar audit that reports active scripts outside approved live roots and flags generic, temporary, WIP/test, and excluded-area scripts.
- 2026-05-28: Added `scripts/roblox_studio_suspicious_script_inspector_v1.lua`, a read-only Studio command-bar inspector that captures source previews, line counts, fingerprints, and keyword hints for unexpected/generic active scripts before any cleanup decisions.
- 2026-05-28: User manually removed two generic active `LocalScript`s from `StarterPlayerScripts`; `TEMP_LightingPreview` is intentionally kept as a day/night lighting preview tool.
- 2026-05-28: Updated audit/inspector scripts so `TEMP_LightingPreview` is treated as an intentional temporary lighting tool rather than accidental clutter.
- 2026-05-28: Added `scripts/roblox_studio_archive_disabled_legacy_scripts_v1.lua`, a cleanup script that archives disabled legacy `HOVER_RACING*` scripts into `ServerStorage.NeoTokyoRacers_LegacyArchive.DisabledScripts` without deleting them or touching active systems.
- 2026-05-28: Added `scripts/roblox_hierarchy_phase3_config_registry_mirrors.lua`, a non-destructive config migration script that creates/refines `NeoTokyoRacers.Shared.Config`, adds live config references, refreshes generated config mirrors, and installs `ConfigRegistry` without changing live config values or switching live scripts.
- 2026-05-28: Added a lightweight Studio-to-GitHub script source mirror workflow: `scripts/roblox_studio_export_scripts_for_github_v1.lua`, `scripts/import_studio_script_export.py`, `docs/10_script_source_sync_workflow.md`, and `roblox/exported_scripts/`.
- 2026-05-28: Imported the current Studio script export into `roblox/exported_scripts` and added `docs/11_manual_script_copy_map.md` for manual source copy guidance.
- 2026-05-28: Reviewed the exported Studio script mirror and added `docs/script-architecture-review-2026-05-28.md`, documenting the current client/server modularity risks, mobile performance priorities, and staged migration order.
- 2026-05-28: Added `scripts/roblox_hierarchy_phase4_architecture_staging_scaffold.lua`, a non-destructive Studio command-bar script that creates future service/controller/config folders and ObjectValue references without moving or changing live scripts.
- 2026-05-28: Added `scripts/roblox_hierarchy_phase4b_prepare_traffic_service_shadow.lua`, a non-destructive Studio command-bar script that copies the live traffic controller into the new architecture as a disabled shadow script for future migration testing.
- 2026-05-28: Added `docs/phase5-ui-migration-plan-2026-05-28.md` and `scripts/roblox_hierarchy_phase5_ui_module_shadow_extract.lua` to stage UI helper modules and future UI folders without switching live UI behaviour.
- 2026-05-28: Added `docs/compressed-architecture-roadmap-2026-05-28.md` to reduce the remaining architecture work to six broader phases.
- 2026-05-28: Added `scripts/roblox_hierarchy_phase6_world_services_migration.lua`, which migrates traffic lights to the new world service location and stages disabled lighting/LOD shadow copies for later migration.
- 2026-05-28: Added `docs/phase7-shared-ui-helpers-2026-05-28.md` and `scripts/roblox_hierarchy_phase7_shared_ui_helpers_promote.lua`, promoting final shared UI helper modules and mirrored UI theme config without switching live UI behaviour.
- 2026-05-28: Added `docs/phase8-client-ui-controller-scaffold-2026-05-28.md` and `scripts/roblox_hierarchy_phase8_client_ui_controller_scaffold.lua`, creating the future client UI controller structure without switching live UI, driving, VFX, server actions, mobile controls, LOD, lighting, traffic, or assets.
- 2026-05-28: Added `docs/phase9-server-services-scaffold-2026-05-28.md` and `scripts/roblox_hierarchy_phase9_server_services_scaffold.lua`, creating the future garage/vehicle/profile/economy server service structure without switching the current live `GarageInvoke` action layer.
- 2026-05-28: Added `docs/phase10-runtime-controller-scaffold-2026-05-28.md` and `scripts/roblox_hierarchy_phase10_runtime_controller_scaffold.lua`, creating future runtime controller ownership targets for driving bootstrap, camera, HUD, mobile controls, VFX, and vehicle access without changing active runtime behaviour.
- 2026-05-28: Added `docs/phase11-architecture-readiness-audit-2026-05-28.md` and `scripts/roblox_hierarchy_phase11_architecture_readiness_audit.lua`, a non-destructive readiness audit for missing architecture paths, unexpected active scripts, accidental enabled future bootstraps, and remaining live legacy names.
- 2026-05-28: Added `docs/phase12-server-action-snapshot-2026-05-28.md` and `scripts/roblox_hierarchy_phase12_server_action_snapshot.lua`, capturing the live V56 server action layer as a non-live snapshot/parity reference before extracting server services.
- 2026-05-28: Added `docs/phase13-server-parity-harness-2026-05-28.md` and `scripts/roblox_hierarchy_phase13_server_parity_harness.lua`, a non-destructive parity gate that compares the live V56 hash against the Phase 12 snapshot and optionally checks the `GetInitial` response shape in Play mode.
- 2026-05-28: Corrected Phase 12 snapshot generation so `V56ActionLayerSnapshot` is valid Lua, updated Phase 13 to avoid unsupported server-side `OnServerInvoke` reads, and added `scripts/roblox_hierarchy_phase13b_client_getinitial_shape_check.lua` for the client-side `GetInitial` shape check.
- 2026-05-28: Added `docs/phase14-server-shadow-action-controller-2026-05-28.md` and `scripts/roblox_hierarchy_phase14_server_shadow_action_controller.lua`, creating a disabled shadow server action controller from the verified V56 block without switching live server ownership.
- 2026-05-28: Added `docs/phase15-server-action-owner-switch-2026-05-28.md` and `scripts/roblox_hierarchy_phase15_server_action_owner_switch.lua`, a controlled server action owner switch with `SWITCH` and `ROLLBACK` modes.
- 2026-05-28: Phase 15 `SWITCH` was run and tested successfully. Output confirmed the active V56 controller now runs from `GarageActionController_Shadow_Disabled`; Phase 13 hash parity and Phase 13B client `GetInitial` shape checks passed after the switch.
- 2026-05-28: Added `docs/phase16-runtime-helper-owner-switch-2026-05-28.md` and `scripts/roblox_hierarchy_phase16_runtime_helper_owner_switch.lua`, a controlled runtime helper owner switch for cached thrust VFX, mobile controls, and mobile HUD suppression.
- 2026-05-28: Phase 16 `SWITCH` was run and tested successfully. Runtime helper ownership moved into `NeoTokyoRacersClient.Controllers.Runtime` without reported gameplay regressions.
- 2026-05-28: Added `docs/phase17-driver-seat-owner-switch-2026-05-28.md` and `scripts/roblox_hierarchy_phase17_driver_seat_owner_switch.lua`, a controlled driver seat keeper owner switch into the new vehicle service architecture.
- 2026-05-28: Phase 17 `SWITCH` was run and tested successfully. Driver seat position keeper ownership moved into `NeoTokyoRacers.Services.Vehicle` without reported gameplay regressions.
- 2026-05-28: Added `docs/phase18-lod-client-owner-switch-2026-05-28.md` and `scripts/roblox_hierarchy_phase18_lod_client_owner_switch.lua`, a controlled LOD client owner switch into the new world controller architecture.
- 2026-05-28: Phase 18 `SWITCH` was run and tested successfully. LOD client ownership moved into `NeoTokyoRacersClient.Controllers.World` without reported gameplay regressions.
- 2026-05-28: Added `docs/phase19-lighting-service-owner-switch-2026-05-28.md` and `scripts/roblox_hierarchy_phase19_lighting_service_owner_switch.lua`, a controlled server lighting owner switch into the new world lighting service architecture.
- 2026-05-28: Phase 19 `SWITCH` was run and tested successfully. Server lighting ownership moved into `NeoTokyoRacers.Services.World.Lighting` without reported gameplay regressions.
- 2026-05-28: Added `docs/phase20-thrust-preview-owner-switch-2026-05-28.md` and `scripts/roblox_hierarchy_phase20_thrust_preview_owner_switch.lua`, a controlled thrust preview owner switch into the new preview controller architecture.
- 2026-05-28: Phase 20 `SWITCH` was run and tested successfully. Thrust preview ownership moved into `NeoTokyoRacersClient.Controllers.Preview` without reported gameplay regressions.
- 2026-05-28: Added `docs/phase21-post-switch-architecture-audit-2026-05-28.md` and `scripts/roblox_hierarchy_phase21_post_switch_audit.lua`, a read-only checkpoint audit for all owner switches completed in Phases 15-20.
- 2026-05-28: Phase 21 audit passed cleanly: 11/11 expected active owners enabled, no unexpected active scripts, no active scripts in `Test + WIP Assets`, and only the intentionally remaining `HOVER_RACING_V2_Client` legacy owner active.
- 2026-05-29: Added `docs/main-client-extraction-plan-2026-05-29.md`, a five-phase plan for extracting `HOVER_RACING_V2_Client` into state/API/catalog modules, preview/colour controllers, garage screen controllers, a final bootstrap, and cleanup.
- 2026-05-29: Added `docs/main-client-phaseA-core-boundary-2026-05-29.md` and `scripts/roblox_client_phaseA_core_boundary_modules.lua`, creating staged Core modules for client state, garage API calls, catalog lookups, theme reads, and paint utilities without changing live client behaviour.
- 2026-05-29: Phase A was run and play-tested successfully by the user; added `docs/main-client-phaseB-preview-colour-2026-05-29.md` and `scripts/roblox_client_phaseB_preview_colour_modules.lua`, staging preview vehicle, preview camera, and colour picker modules without switching live client behaviour.
- 2026-05-29: Phase B was run and play-tested successfully by the user; added `docs/main-client-phaseC-garage-screens-2026-05-29.md` and `scripts/roblox_client_phaseC_garage_screen_controllers.lua`, staging dealership, cockpit paint, module shop, customisation, navigation, and stats panel controllers without switching live client behaviour.
- 2026-05-29: Phase C was run and play-tested successfully by the user; added `docs/main-client-phaseD-owner-switch-2026-05-29.md` and `scripts/roblox_client_phaseD_main_client_owner_switch.lua`, a controlled `SHADOW` / `SWITCH` / `ROLLBACK` owner-location switch for the remaining live `HOVER_RACING_V2_Client`.
- 2026-05-29: Phase D was run and play-tested successfully by the user; added `docs/main-client-phaseE-post-switch-audit-2026-05-29.md` and `scripts/roblox_client_phaseE_post_switch_audit.lua`, a read-only audit for confirming the new architecture-owned main client is active and the legacy `HOVER_RACING_V2_Client` is disabled.
- 2026-05-29: Phase E audit passed cleanly after rerunning Phase D with `MODE = "SWITCH"`: 11/11 expected active owners enabled, no unexpected active scripts, no active scripts in `Test + WIP Assets`, no active legacy-named `HOVER_RACING` scripts, and all staged Phase A-C modules present.

## Early System

- Initial command-bar scripts created starter folders, template parts, module categories, UI, money, and a short checkpoint race.
- The system moved from cable-tied modular slots to fixed category-based module slots.

## Fixed-Slot Category System

- `V13` and later scripts introduced a fixed-slot category system.
- `BRUISER` became the active vehicle category.
- Modules became interchangeable within a vehicle category.

## UI and Mobile

- Multiple responsive/futuristic UI patches refined the dealership, module selection, colour picker, customisation menus, and mobile controls.
- The UI settled toward dark translucent panels, light green borders, and futuristic text.

## VFX

- V23-V31 introduced VFX templates for hover dust, engine jets, boost, stabilisers, and custom VFX hierarchies.
- V64-V66 added cached thrust visual runtime and fixed a weld leak.

## Server/Action Layer Recovery

- V52-V56 rebuilt or repaired server/action logic after earlier patch failures.
- Later guidance: avoid large brittle server/client rewrites unless necessary.

## Driving

- V62 restored V47-style driving and replaced fallback driving paths with `DrivingControllerV47`.
- V67-V71 restored and corrected mobile driving HUD visibility.
- V72/V73 experimented with a fully scriptable chase camera but caused jitter and did not feel right.
- V74 restored the pre-V72/default Roblox camera feel with a light camera assist. User confirmed this worked well.
- V75 added boost recharge delay, editable boost module attributes, and low-speed hover wobble. Needs play-test confirmation unless confirmed later.

## Current Important Scripts

- `scripts/roblox_hover_racing_v74_pre_v72_camera_assist.lua`
- `scripts/roblox_hover_racing_v75_boost_delay_hover_wobble.lua`
