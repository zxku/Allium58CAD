# Allium58CAD


![Prototype Picture](https://github.com/zxku/Allium58CAD/assets/167131775/380984bc-6e11-4af9-8e7e-8524cc75f92c)



_This picture is of the 3D printed moc up._

--------------------------------------------------
[WORK IN PROGRESS...]
___________________________________________________


[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)


The Allium58CAD is a wireless open source 6*4+4keys column-staggered split keyboard that integrates an ortholinear QWERTY layout, SpaceMouse, macro pad, and left number pad into a single system to optimize productivity and ergonomics in 3D design, CAD, and Engineering, and 3D CNC programming. 
It is a fork of the [Allium58 by beekeeb](https://github.com/beekeeb/Allium58) which is in turn based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro). 


The SpaceMouse itself is a seperate product sold by [3DConnection](https://3dconnexion.com/dk/product/spacemouse-wireless/) 
The Allium58CAD is designed to integrate with the SpaceMouse by snapping tight to the SpaceMouse base with magnets.

_If you have never used a SpaceMouse, I highly recommend them. There is definitely a learning curve, but once you figure it out the SpaceMouse is a lifechanging improvement for navigating in a 3D space.  It alows you to manipulate the 3D space simultanious and independent of what your mouse is doing. This lets your mouse be dedicated to selcting, drawing, etc._ 

_NOTE: This design is configured for right handed mouse use, but could be easily mirrored to work in a left hand dominant setup._



# Purpose of the Project

The biggest downside of a spacemouse is that you must remove your hand, reaching up and over it to hit any of the keyboard keys. While most 3D software can be navigated almost completely with a mouse and the menus, shortcuts are much more efficient, and it is often still nessessary to use some of the modifier keys in conjunction with the mouse. 
The Allium58CAD was developed after scouring the internet for both commercial options and custom implementations to address this issue, and not finding a satisfactory solution. The Allium58CAD integrates a keyboard, SpaceMouse, number pad, and macro pad into a single system and I am convinced that “this is the way”.  

Most of the availible solutions add additional buttons/keys around the SpaceMouse Joystick, basically adding a macro pad to go with the SpaceMouse. I, along with others, have discovered the utility of a left hand number pad, so that I can quickly enter in values without taking my hand off the mouse.  When you put all of this together, it leaves you with a left number pad, a macro-pad, a spacemouse, and a traditional keyboard all taking up room on your desktop.  Furthermore, since they are all seperate, they are unintentionally getting shifted around the desktop, which interferes with the muscle memory of what is where.

**Solution:**
- Allium58CAD utilizes ZMK programming and a custom case to integrate all of these items into a single system, decreasing desktop clutter instead of adding to it.
- The split keyboard functionality has the added benifit of leaving desk space directly in front of you for hardcopy reference documents (such as the Machinery's Handbook).
- The magnetic snap function allows the board to be used as two seperate keyboards, or snapped together to function like a unibody split keyboard
- Most SpaceMouse users start off with the basic spacemouse model, getting a feel for using it before commiting further investment for added utility. The Allium58CAD allows users to utilize their existing equipment instead of reinvesting in a whole new module.
- ZMK allows users to customize the key layout for their paticular preference or software. The starting keymap is designed to work with solidworks, but it can be adapted for other software packages.
  
I'm hoping it will be easier to tweak and modify my [existing keymap](https://github.com/zxku/zmk-config/blob/main/config/lily58.keymap) instead of building one from scratch like I did. Same thing goes for the FK custom keymap legend included in this documentation.  It ended up taking quite a bit of time to compile both of them, and I wish I had had someone elses map to edit from instead of building the whole thing from scratch. 


I chose to use low profile choc switches because of the angle at which you hold the SpaceMouse. The low, flat profile puts the macro keys in the right position to be easily reached while manupulating the SpaceMouse joystick. 
I attempted to impliment some tenting in the Keyboard case, but found that it got in the way of using the SpaceMouse. Raising the spacemouse up to compensate for the tenting height was tested but made the spacemouse akward to use. 

# Keymap 
The included keymap is designed to combine all the basic funcitons of a standard QWERTY layout with a left handed number pad, a macro pad, and a navigation pad. Quite a few ZMK behaviors were utilized to make this happen. 

- One of my goals was to make sure that all of the standard availible QWERTY symbols be accessible in the default layer.
- Instead of numbers on the top row of the default layer, it has their corrisponding symbols. The number pad is availible via the momentary navigation key for quick access any time I need to imput numbers. I find the number pad much faster than the number row.
- The second "Tools" layer contains the number pad and the shortcut keys on the left half, with the navigation arrow keys and additional math and engineering related symbols on the right half
- The second "Tools" layer is accessed in two ways: 1)A layer toggle on/off on the left pinky. 2) A "sticky momentary layer" toggle on the thumb of the right pad. This momentary switch is positioned such that it is easily reached while pressing the arrow keys.
  ("sticky momentary layer" is the term I use for urobs capsword PR that I use. In fact I use his entire fork. This PR allows you to impliment a capsword type of behavior on layers and things that are not alphanumerics. So after you tap the arrow nav toggle button, the layer will stay active untill you type anything that isnt a nav key, number key, or the right layer toggle key)
- The third layer is the utility layer containing boot mode and bluetooth connecting buttons. programming is implimented to require hold to activate boot, reset, and BT clear, not labeled in the legend are the bluetooth disconnect keys that are below their corrisponding selector key.
- The last layer is only used for a quirky toggle functionality I require for solidworks (wireframe to shaded with lines requires two differnent commands, to make it toggle function. It activates a layer that is transparent except for that key.)

- Combos are utilized to fit some things that didn't otherwise have a spot. Combo keys are indicated by little icons on the touching edges of both keys. (all combos are side by side)
- Caps Lock is implimented as a double tap behavior on the left shift key.
- The outermost lower left key on the left keypad switches between the default and the tools layer, holding it will toggle the utility layer.

# Legend Layout Guide
![Legend Guide](https://github.com/zxku/Allium58CAD/assets/167131775/0453577a-7bf1-47eb-ae9f-0f5b584b51cd)



## Status

Initial build underway...     As of 4/30/2023 this is still a work in progress 

## Photos

![Allium58CAD Keyboard](docs/photo-2.jpg)

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

- Top Plate & Low Profile Bottom Case:     ...To Be Added...
- 
-**PCB Trimming Instructions:** ...work in progres...
    a) The Allium58 PCB will require slight trimming on the lower right corner of the left hand PCB. This puts the spacemouse in a comfortable position to allow your ring and pinky fingers to reach the Control, S, D, A, and Escape buttons without repositioning your hand from the spacemouse. (S, D, and A are solidworks specific shortcut examples. These can be programmed differently for a different software)
    b) I recommend throughly taping off the rest of the exposed PCB with removable painters tape etc. to protect it from dust and debris.
    c) A dremel tool with a cut off wheel works well. A fine tooth coping saw could probably also be used.  Follow the template below to      make sure you dont overcut. 
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

- Wireless: (https://shop.beekeeb.com/product/wireless-allium58-choc/)

## External Libraries


## More Information



## Credits

This fork by zxku is an open source hardware project originally created by [beekeeb](https://beekeeb.shop) and other contributors. It is based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro).

[<img src="docs/beekeeb.png" height="80" />](https://beekeeb.shop)
