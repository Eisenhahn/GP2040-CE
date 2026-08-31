# DDI analog overlay for GP2040-CE 0.7.12

This branch is based on the official GP2040-CE `v0.7.12` tag.

It changes Dual Directional Input behavior when the DDI target is an analog stick and **Combination Mode** is set to **None**.

## Behavior

- With no DDI input, the proportional thumbstick remains untouched.
- Left/Right DDI input replaces only the target stick's X axis with full-scale output.
- Up/Down DDI input replaces only the target stick's Y axis with full-scale output.
- A diagonal DDI input replaces both axes.
- Digital DDI behavior is unchanged.
- Mixed and override combination modes continue to use the stock override path.

This allows a digital lever and proportional thumbstick to coexist on the same logical analog stick.

## Files changed

- [`headers/addons/dualdirectional.h`](headers/addons/dualdirectional.h)
- [`src/addons/dualdirectional.cpp`](src/addons/dualdirectional.cpp)

## Configuration

In Web Config:

1. Enable **Dual Directional Input**.
2. Assign the lever's four DDI GPIO directions.
3. Set the DDI **D-pad Mode** to **Left Analog** (or **Right Analog** for the right stick).
4. Set **Combination Mode** to **None**.
5. Keep the physical thumbstick configured through the Analog add-on.

## Status

Tested on GP2040-CE 0.7.12 using an RP2040 Advanced Breakout Board v5.6E with USB Passthrough. This is an unofficial modification; build the firmware for your own board target.
