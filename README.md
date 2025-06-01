# SI60

[QMK](https://github.com/qmk/qmk_firmware) Compatible Open Hardware GH60-compatible USB-C PCBs designed for use with [Hi-Tek 725 "Space Invaders" Switches](https://wiki.vintkeys.ca/NMB/Switches) in a variety of layouts, including variants of NMB keyboards with and without stepped caps.



## Overview
The main features of this project are:
 - Support for nearly every possible 60% set of caps you could use, including all NMB RT101+ keyboards in ANSI and ISO, with stepped and unstepped caps, Erase-Eaze, and ADDS/Televideo ANSI layouts.
 - Future-proof STM32F072CBT6 MCU
 - Design optimized for hand-soldering, with no parts smaller than 0603, and an MCU that does not require an external crystal
 - Compatibility with the original GH60 footprint
 - Compatibility (theoretically) with the Bakeneko60 footprint
 
 **Important: The distance from the plate to PCB on Space Invaders switches is larger than that for MX switches. You must do your own research to confirm compatibility with whatever case you choose.
 Tray-mount cases are likely to work okay, but for top-mount keyboards, the pins may short out on the bottom of the case.
 I will update this page when compatibility with a certain case is confirmed, but other than that, I cannot answer questions like "is X keyboard with this PCB"**

Production files are included for production at [JLCPCB](https://jlcpcb.com/).

![Overview](https://github.com/nearestexit/SI60/blob/main/documentation/PCB.png)

## Supported layouts
 - Stepped and unstepped ISO, ANSI, BAE
 - Televideo ANSI bottom row
 - ADDS ANSI bottom row

**Please note: compatibility for the more obscure layouts is untested.**

![KLE](https://github.com/nearestexit/SI60/blob/main/documentation/KLE.png)

## Configuration options
 - To fit in a GH60 case, the JST ought to be depopulated.
 - To fit in a Bakeneko60 case, the USB-C ought to be depopulated.

## JLCPCB Ordering Information
1. On jlcpcb.com, click "order now" and "add gerber file"
2. Navigate to the directory with the gerber.zip - for example, SI60\jlcpcb\production_files
3. Wait for the gerber to upload.
4. Select the number of PCBs you wish to build.
5. Make sure PCB thickness is set to 1.6mm.
6. Make sure Via covering is set to "tented".
7. Make sure Min via hole size/diameter is set to "0.3mm"
8. Turn the "PCB Assembly" option on
9. Make sure PCBA type is set to "Economic"
10. For "Assembly side", if you are ordering the daughterboard select "top side", otherwise select "bottom side"
11. Click "next", and then "next" again
12. Click "Add BOM File" and select the BOM csv - for example, BOM-SI60.csv
13. Click "Add CPL File" and select the CPL csv - for example, CPL-SI60.csv
14. Click "Process BOM and CPL"
15. Make sure all parts are in stock - if any are not in stock, you will need to find replacements
16. Decide whether you want the USB-C soldered or the JST soldered, and uncheck the box next to the one you don't want
17. **IMPORTANT:** Click "Bottom" to view the bottom side of the PCB, and begin inspecting the component placements. You **WILL** need to correct some component rotations. If you are not sure at this step, do not continue!
18. Click "next" and finish checking out.

## Firmware
- [Vial-QMK](https://get.vial.today/) .uf2 files are provided in the firmware folder.
- To put the keyboard into bootloader mode to flash the firmware:
1. Open QMK toolbox, select the firmware file, and check the box for "auto flash"
2. Unplug the USB cable
3. Short the 3v3 and BOOT0 pins with a pair of tweezers
4. Plug the USB cable in
5. Stop shorting the BOOT pins.
- The STM32 will then be recognized by QMK toolbox, and it will load the firmware.
- You may need to reconnect the keyboard after flashing.
- Once you have flashed the firmware, you can change the keymap from [vial.rocks](https://vial.rocks)
  
