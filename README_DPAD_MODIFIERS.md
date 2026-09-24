# GP2040-CE 0.7.12: DPAD, LS, and RS modifiers

This is a generic Raspberry Pi Pico / RP2040 build of GP2040-CE 0.7.12. It has been successfully flashed and re-enumerated in XInput mode; individual modifier inputs still require physical mapping and testing by the user.

## GPIO Mapping actions

- **DPAD Modifier**: while held, Up/Down/Left/Right report as D-pad.
- **LS Modifier**: while held, Up/Down/Left/Right report as the left analog stick.
- **RS Modifier**: while held, Up/Down/Left/Right report as the right analog stick.

Releasing the modifier immediately restores the currently selected default D-pad mode. The modifiers do not change or interrupt that saved default.

If more than one modifier is held simultaneously, the priority is DPAD, then LS, then RS.

## Installation

1. Export a GP2040-CE configuration backup.
2. Put the RP2040 into BOOTSEL mode.
3. Copy `GP2040-CE_0.7.12_DPAD-Modifier.uf2` to the `RPI-RP2` drive. Do not use a flash-nuke UF2 for this update.
4. Open the GP2040-CE web configurator and assign spare GPIO pins to the modifier actions.
5. Save and reboot into Controller mode.

The firmware was built from the official `v0.7.12` tag. It uses the generic `pico` board target and preserves the controller's stored GPIO configuration during a normal UF2 update.

## SHA-256

`62E1016834160730D6DF8AD532725F64EE6E8E0F5CD8E5026DC2620A0D871BDB`
