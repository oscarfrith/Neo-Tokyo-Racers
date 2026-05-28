# Customisation UI

## Visual Style

The UI direction is futuristic, compact, and readable. It uses:

- Michroma-style futuristic text where possible.
- Dark translucent panels.
- Light green borders/accent colour.
- Consistent button sizing.
- Responsive scaling for mobile and desktop.

Avoid oversized landing-page style UI. The garage/customisation UI should be functional and scan-friendly.

## Dealership Flow

Known dealership structure:

- Category menu on the left.
- Cockpit grid in the centre.
- Vehicle stats panel on the right.
- Available cash panel near the lower left.

For mobile:

- Cockpit cards should scale to fit a `3x3` style grid where possible.
- Left/category UI should not overlap the cash UI.
- Right stats panel should remain readable and aligned with the rest of the layout.

## Paint Cockpit

Known cockpit paint channels:

- Primary
- Secondary
- Detail

Cockpit front/rear light defaults were requested:

- Front: `252, 250, 255`
- Rear: `255, 116, 116`

Front/rear cockpit lights should not be editable during initial cockpit paint, but should be editable later in module/customisation menus.

## Build Modules

Known module selection slots:

- Front engine
- Rear engine
- Stabilisers
- Boost
- Front bumper
- Rear bumper
- Rear spoiler
- Side pods

Earlier labels `Engine 1` and `Engine 2` were renamed conceptually to:

- Front engine
- Rear engine

When selecting modules:

- Selecting a slot should show options for that slot.
- Engine A/B assets should not be interchangeable between front/rear unless the folder/slot rules explicitly allow it.
- Buy/equip should install the module and return to the slot menu.

## Customise Modules

Known customisation options:

- Customise all colours.
- Cockpit.
- Bought/installed modules.
- Brakes.
- Converter.
- Fuel system.
- Thrust colour.

Colour channels should be detected from the actual module contents where possible:

- Primary
- Secondary
- Detail
- Neon/optional neon
- Thrust colour for engine/boost/stabiliser systems

Upgrade buttons should preview stat changes first, then commit on buy.

## Mobile Driving UI

Known mobile driving UI:

- Accelerator button bottom right.
- Smaller brake pedal nearby.
- Left-side steering/drift controls.
- Boost button also acts as boost meter.
- MPH text shown above boost button.
- PC bottom-left drive HUD should be hidden on mobile.

