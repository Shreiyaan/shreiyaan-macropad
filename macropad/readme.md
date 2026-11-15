Shreiyaan’s Macropad

This is my three-key macropad with a rotary encoder for media controls and everyday shortcuts. I designed the PCB in KiCad, made the enclosure in Autodesk Fusion, and configured the firmware using QMK.

Hardware

The design uses a Seeed Studio XIAO RP2040, three MX-style mechanical switches with keycaps, and an EC11 rotary encoder with a push button. The PCB and enclosure were designed for this project.

Controls

The current firmware assigns speaker and mute option to the first key, play/pause to the second key, and Print Screen (to take a screenshot) to the third key. Turning the rotary encoder adjusts the volume, and pressing it toggles speaker mute. Speaker mute does not mute the microphone.

Firmware files

The keyboard configuration and GPIO assignments are in keyboard.json. The button assignments and encoder actions are in keymaps/default/keymap.c. Encoder mapping is enabled in rules.mk.

Building and uploading

I compiled the firmware into a UF2 file for the XIAO RP2040. Once I receive the hardware, I will put the board into bootloader mode and copy this file onto it. I will then test the buttons and rotary encoder to check that they work as intended.

qmk compile -kb shreiyaan/macropad -km default

Flashing

With the XIAO RP2040 disconnected, hold its BOOT button while connecting it to the computer using a USB data cable. Release the button once connected, then copy the compiled UF2 file onto the bootloader drive that appears.

Project status

The PCB, enclosure design, and firmware source have been created. The hardware has not yet been assembled or tested. The firmware pin assignments, enclosure fit, and manufacturing files still need final verification. Physical button operation and encoder direction will be tested after assembly.

Author

Shreiyaan P Shah