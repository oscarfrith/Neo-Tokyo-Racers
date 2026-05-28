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

Known sensitive areas:

- Mobile dealership scaling.
- PC drive HUD hiding on mobile.
- Customisation colour sliders on mobile.
- Left customisation bar overlapping bottom UI on small screens.

## VFX

Known sensitive areas:

- Thrust colour should not flicker back to default after editing.
- Cosmetic neon and thrust-colour neon must remain separate.
- Front bumper optional neon previously did not update correctly.
- Stabiliser left/right VFX had breakage in earlier patches; verify directional drift VFX after any VFX runtime change.

## Data/Folders

Known sensitive areas:

- Buyable modules need valid `Price` attributes.
- Boost modules should have `Boost`, `BoostDuration`, `BoostRecharge`, and `BoostRechargeDelay`.
- Module folder shape should stay simple and not reintroduce redundant colour-channel folders.

