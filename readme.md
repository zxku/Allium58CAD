# Allium58CAD

![Allium58 GLP Keyboard](docs/banner.jpg)

[WORK IN PROGRESS...]

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

The Allium58CAD is a wireless open source 6*4+4keys column-staggered split keyboard that integrates an ortholinear QWERTY layout, SpaceMouse, macro pad, and left number pad into a single system to optimize productivity and ergonomics in 3D design, CAD, and Engineering, and 3D CNC programming. It is A fork of the Allium58 by beekeeb which is in turn based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro). 

_This is configured for right handed mouse use, but could be easily mirrored to work in a left hand dominant setup. _

The SpaceMouse is a seperate product sold by [3DConnection](https://3dconnexion.com/dk/product/spacemouse-wireless/) 
This keyboard is designed to integrate with the SpaceMouse by snapping tight to the SpaceMouse base with magnets.
_If you have never used a SpaceMouse, I highly recommend them. There is definitely a learning curve, but once you figure it out the SpaceMouse is a lifechanging improvement for navigating in a 3D space.  It alows you to manipulate the 3D space simultaniously and independent of what your mouse is doing. This lets your mouse be dedicated to selcting, drawing, etc._ 

The biggest downside of a spacemouse is that you must remove your hand, reaching up and over it to hit any of the keyboard keys. While most 3D software can be navigated almost completely with a mouse and the menus, shortcuts are much more efficient, and it is often still nessessary to use some of the modifier keys in conjunction with the mouse. The Allium58CAD was developed after scouring the internet for both commercial options and custom implementations to address this issue, and not finding a satisfactory solution. The Allium58CAD integrates a keyboard, SpaceMouse, number pad, and macro pad into a single system and I am convinced that “this is the way”.  
Most of the availible solutions add additional buttons/keys around the SpaceMouse Joystick, basically adding a macro pad to go with the space mouse. I, along with others, have also discovered the utility of a left hand number pad, so that I can quickly enter in values without taking my hand off the mouse.  Now you have a left number pad, a macro-pad, a spacemouse, and a traditional keyboard all taking up room on your desktop.  Allium58CAD utilizes layers in ZMK to integrate all of these into a single system decreasing desktop clutter instead of adding to it. The split keyboard functionality has the added benifit of leaving space directly in front of you for hardcopy reference documents (such as the Machinery's Handbook).



## Status

Initial build underway...     As of 4/30/2023 this is still a work in progress 

## Photos

![Allium58 GLP Keyboard](docs/photo-1.jpg)
![Allium58 GLP Keyboard](docs/photo-2.jpg)
![Allium58 GLP Keyboard](docs/photo-3.jpg)

## Bill of Materials (BOM)

### Required

| Name | Count | Remarks |
|:-|:-|:-|
| PCB | 1 set | |
| Top plate | 2 sheets | 1.2mm thick |
| Bottom plate / 3D printed case | 1 set | |
| OLED cover | 2 | |
| Pro Micro (compatible with Sea Picro RP2040) / nice!nano or equivalent | 2 |  |
| Reset switch | 2 | |
| Diodes | 58 | SMD Only (SOD-123 Package) |
| Hotswap Sockets | 58 | [GLP variant] Gateron Low Profile Hotswap Sockets |
| Key switches | 58 | [GLP variant] Gateron KS-33 / KS-27 |
| Keycaps | 58 pieces | 1u 56 pcs, 1.5u 2 pcs [GLP Keycaps Comparison](https://showcase.beekeeb.com/the-keycaps-of-gateron-low-profile-key-switches-and-kailh-choc-v1-key-switch/) |
| Female Threaded Brass Spacer M2 5mm | 10 pieces | For Case assembly |
| Female Threaded Brass Spacer M2 9mm (or 14mm with MCU sockets) | 4 pieces | For OLED cover |
| GP823 Screw M2 4mm | 28 screws | |
| [Wired build] TRRS (4 poles) cable | 1 |  |
| [Wired build] TRRS jack | 2 |  |
| [Wired build] Micro USB or USB-C cable | 1 | Avoid charge-only cables |
| [Wireless build] JST battery socket | 2 | |
| [Wireless build] Battery with JST connector | 2 | |  |

### Optional

| Name | Count | Remarks |
|:-|:-|:-|
| OLED module / nice!view display | 2 | |
| Microcontroller/OLED Sockets & Pins | 1 set |  | |

## Case
- Top Plate & Low Profile Bottom Case:     ...
-** PCB Trimming Instructions**: ...work in progres...
    PCB will require slight trimming on the lower right of the left hand PCB, this puts the spacemouse in a comfortable position for       the Control, S, D, A, and Escape buttons.
    I recommend throughly taping off the rest of the exposed PCB with removable painters tape etc. to protect it from dust and debris.
    A dremel tool with a cut off wheel works well. A fine tooth coping saw could probably also be used.  Follow the template below to      make sure you dont overcut. 
          NOTE: At some point, it would be nice to get a custom PCB, but for now the modification will have to do. 

  ------  CAUTION!!! overcutting could render the bottom row of keys unuseable, be cautious and precise! -------

## Firmware

- [ZMK](https://github.com/zmkfirmware/zmk "ZMK") - supported
- [ZMK config files](https://github.com/zxku/zmk-config)
- Keymap file (WIP)
- Solidworks Shortcuts to Program (WIP)
- [Custom labeled MBK Keycap set](https://fkcaps.com/custom/9WTR81) - In PBT white, allows for a custom color dye job!
- [Custom color mod keys MBK keycaps](https://fkcaps.com/custom/U5X2FC)


## Ordering Parts

- Wireless: https://shop.beekeeb.com/product/allium58-glp-wireless-kit/

## External Libraries

* [https://github.com/siderakb/key-switches.pretty](https://github.com/siderakb/key-switches.pretty)
* [https://github.com/foostan/kbd](https://github.com/foostan/kbd)

## More Information



## Credits

This fork by zxku is an open source hardware project originally created by [beekeeb](https://beekeeb.shop) and other contributors. It is based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro).

[<img src="docs/beekeeb.png" height="80" />](https://beekeeb.shop)
