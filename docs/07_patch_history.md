# Patch History

This is a high-level summary, not a complete changelog of every script.

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

