# Adept Trackball Custom – QMK/VIA Firmware

![Adept Trackball Custom](images/adept_custom.JPG)

Adept Trackball Custom is a trackball based on the Adept Trackball (Ploopy), running a custom QMK/VIA firmware.  
This repository provides the source code for the firmware (keymap) used in Adept Trackball Custom,  
as well as usage information for the device.

## About the Keymap

Adept Trackball Custom uses QMK/VIA to define its own keymap.  
The default layer provides standard trackball operations, while the Fn layer offers additional features such as  
DPI switching and scroll‑mode toggling.

To view the current keymap, use [VIA](https://usevia.app/).  
When Adept Trackball Custom is connected to your PC, VIA should recognize it automatically.  
If it does not, try reconnecting the USB cable or restarting VIA.

Below is the keymap for the default layer (Layer 0).  
Due to VIA’s specifications, key assignments are shown on mouse‑over,  
so individual captures are provided for the main keys.  
Some keys appear as “CUSTOM(64)” in VIA,  
which simply means VIA does not have a name for that keycode.  
In practice, these keys are assigned to layer‑switching functions.

![Keymap Overview](images/keymap.png)

## About RGB Lighting

This firmware supports the two RGB LEDs mounted on the PCB.  
VIA cannot display or configure RGB settings for this device.

The RGB LEDs automatically change color depending on the device’s state:

- During drag‑scrolling: changes to a dedicated color  
- When switching layers: briefly changes color to indicate the new state  
- When switching DPI: cycles through colors and returns to the start after one full rotation  
  (Note: color intensity does not correspond to DPI values)

## About Bootloader Mode

This device uses the UF2 bootloader built into the RP2040.  
Bootloader mode is a special state used for rewriting the firmware and differs from normal operation.

### Behavior in Bootloader Mode

When the device starts in bootloader mode, it behaves as follows:

- It no longer functions as a mouse  
- A UF2 drive such as “RPI‑RP2” appears on your PC  

This is not a malfunction — it simply means the device is **waiting for firmware to be written**.

### How the Device Enters Bootloader Mode

If the USB cable is connected while holding the lower‑left button,  
the device will start in bootloader mode.  
Because of this, it is possible to enter this mode unintentionally.
