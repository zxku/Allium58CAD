# Allium58CAD


![Prototype Picture](https://github.com/zxku/Allium58CAD/assets/167131775/380984bc-6e11-4af9-8e7e-8524cc75f92c)

<

_This picture is of the 3D printed moc up._

--------------------------------------------------
THIS IS A WORK IN PROGRESS...
___________________________________________________


[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)


The Allium58CAD is a wireless open source 6*4+4keys column-staggered split keyboard that integrates an ortholinear QWERTY layout, SpaceMouse, macro pad, and a left number pad into a single system to optimize productivity and ergonomics in 3D design, CAD, Engineering, and 3D CNC programming. 
It is a fork of the [Allium58 by beekeeb](https://github.com/beekeeb/Allium58) which is in turn based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro). 

>[!note]
>Although split keyboards with a number row have fallen out of favor, that additional top row is neesary to fit a number pad layout. That is why the Allium58 was chosen as the base design. 

```
The SpaceMouse itself is a seperate product sold by [3DConnection](https://3dconnexion.com/dk/product/spacemouse-wireless/) 
The Allium58CAD is designed to integrate with the SpaceMouse by snapping tight to the SpaceMouse base with magnets.

_If you have never used a SpaceMouse, I highly recommend them. There is definitely a learning curve, but once you figure it out the SpaceMouse is a lifechanging improvement for navigating in a 3D space.  It alows you to manipulate the 3D space simultanious and independent of what your mouse is doing. This lets your mouse be dedicated to selcting, drawing, etc._ 
```
>[!tip]
> _This design is configured for right handed mouse use, but could be easily mirrored to work in a left hand dominant setup._



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


>I'm hoping it will be easier to tweak and modify my [existing keymap](https://github.com/zxku/zmk-config/blob/main/config/lily58.keymap) instead of building one from scratch like I did. Same thing goes for the FK custom keymap legend included in this documentation.  It ended up taking quite a bit of time to compile both of them, and I wish I had had someone elses map as a base to modify, instead of building the whole thing from scratch. 


I chose to use low profile choc switches because of the angle at which you hold the SpaceMouse. The low, flat profile puts the mod keys in the right position to be easily reached while manupulating the SpaceMouse joystick. 
Tenting of the keyboard case was tested, but it got in the way of using the SpaceMouse. Raising the spacemouse up to compensate for the tenting height was tested as well but made the spacemouse akward to use. 


# Keymap 

The included keymap is designed to combine all the basic funcitons of a standard QWERTY layout with a left handed number pad, a macro pad, and a navigation pad. Quite a few ZMK behaviors were utilized to make this happen. 


### Keymap Ideology and Theory
- One of my goals was to make sure that all of the standard availible QWERTY symbols be accessible in the default layer.
- Instead of numbers on the top row of the default layer, it has just the symbols as the base fuction of the key. The number pad is availible via the momentary navigation key for quick access any time I need to imput numbers. I find the number pad much faster than the number row. And I find myself using that top row for the symbols far more often than I use the numbers.


### Layers Explained

- Default Layer `Layer 0`
  - Instead of number keys across the top row of the default layer, it has just the corrisponding symbols as the base fuction of the key. The number pad is availible via the momentary navigation key for quick access to enter numbers. The number pad much faster than the number row for numerical entry. The symbols attached to those keys are used more often than I use the numbers. The parentheses in particular come to mind...
  - The layout tries to maintain as much standard QWERTY layout as possible, but not everything would fit perfectly. Several of the less used keys, : , ; , [ , ] , { , } , and DELETE, are implimented as side by side combos. Just hit two keys at the same time and it will output the corrisponding character.
  - Caps Lock is activiated using a double tap on the shift key.  It is a smart caps lock, so it will dissengage when any non alphabetical key is pressed. Traditional Caps Lock is activated with a tripple tap.
     
- Tools Layer `Layer 1`
  - The "Tools" layer contains the number pad and the shortcut keys on the left half, with the navigation arrow keys and additional math and engineering related symbols on the right half
  - point of this layer...
  - ...sketch mods...
  - ...model mods...
  - ...solidworks keys...
  - 
  - The "Tools" layer is accessed in two ways:
     1) A layer toggle on/off on the lower left pinky on the left keypad.
     2) A "sticky momentary layer" toggle on the thumb of the right pad. This momentary switch is positioned such that it is easily reached while pressing the arrow keys.
  >("sticky momentary layer" is the term I use for urobs capsword [PR 1451](https://github.com/zmkfirmware/zmk/pull/1451#) that I use. In fact I use his entire [fork](https://github.com/urob/zmk). This PR allows you to impliment smart layers which is a modified capsword type of behavior for layers and things that are not alphanumerics. So after you tap the arrow nav toggle button, the layer will stay active untill you type anything that isnt a nav key, number key, or the layer toggle key)
  -

- Utility Layer `Layer 2`
  - This contains needed utility keys such as boot mode and bluetooth connectivity buttons.
  - Layer can be accessed from the Default or Tools layers by holding the left layer key. This layer is designed with a sticky layer. you must hold the layer key to activate it and then press the desired action. The layer is automatically deactivated after that keypress to prevent accidental keypressing. To subsequently hit a different key in the utility layer, you would have to hold the layer key again. 
  - Programming is implimented to require a hold to activate boot, reset, and BT clear keys. This is to prevent accidental activation.
  - Blue Tooth Clear only clears the pairing for the currently selected connection, each pariring must be cleared individuallly. 
  - The key for bluetooth disconnect of each blutooth pairing is not labeled in the legend but are located in the row below their corrisponding selector key.
  - The Num Lock key is used to toggle the number layout in the tools layer to output keypad numbers presses instead of number row presses. This is occassionally needed for some programs where they are mapped for a different use, or for entering in alt code characters.
    _See Num Lock Layer below for implimentation._

- Wire Layer `Layer 3` and Wire Activate Layer `Layer 5`
  - This layer is used only to impliment a toggle key function. This allows a key to output one macro with the first press, and a different macro on the second before switching back to the first macro if pressed a third time. 
  - Wireframe to shaded with lines requires two differnent commands in solidworks, but I wanted a key that would toggle back and forth between them.
  - The first keypress in the tools layer sends the first macro and then activates this layer that is completely transparent exept for this key.
  - The Wire Activate layer is completely transparent and is used to activate the wire layer on the conditional basis that the Tools layer is active. This way the wire layer function will only be active when the tools layer is also active.  
 
- Num Lock Layer `Layer 4` and Num Activate Layer `layer 6`
  - When active, the Num Lock layer overlays the number keys on the tools layer, and will output the equivelant number pad keypress. Most of the time this will not be needed. However, the bindings of the number row and the number pad numbers are treated slightly different by the system and in some programs they are mapped to different things. Alt code symbols are an excellent example of this.
  - The Num Lock layer is completely transparent except for the numbers. 
  - The Num Activate layer is completely transparent and is only used to activate the Num layer on the conditional basis that the Tools layer is also active. This way the Num Lock layer will turn itself on and off in tandom with the tools layer. This way it wont interfere with the functions on any other layers.
  
- Combos and Macros
  - Combos and other behaviors are utilized to fit some things that didn't otherwise have a spot. Combo keys are indicated by little icons on the touching edges of both keys. (all combos are side by side)
  - Macros are heavily utilized to output the alt codes for manny of the symbol keys on the right side of the tools layout.
  - 
- Layer Switching Keys
  - The outermost lower left key on the left keypad switches between the default and the tools layer, holding it will toggle the utility layer.
  - The utility layer is a momentary sticky layer. The left layer key must be held to activate the layer, and then it is only good for one keypress before deactivating.
    - While the Layer Key (![image](https://github.com/zxku/Allium58CAD/assets/167131775/769b777b-341b-4cc9-90ec-40f4285b0699)
) on the left keypad toggles the layers on and off, the Navigation layer key (![image](https://github.com/zxku/Allium58CAD/assets/167131775/1077704a-1e81-4a24-a88b-078da37be6c5)) on the right keypad is used for temporary layer activation utilizing the smart layer function of [urobs PR #1415](https://github.com/zmkfirmware/zmk/pull/1451#) 
    - Pressing the Navigation layer key (![image](https://github.com/zxku/Allium58CAD/assets/167131775/d38142fe-e0d3-477d-851a-7db4f9beb0b4) from the Default layer temporarily activates the Tools layer, allowing you to enter numbers and navigate with the arrow keys until spacebar, enter, return or a letter is pressed, when it will automatically return to the default layer.
    - Simmilarily, pressing the Navigation layer key (![image](https://github.com/zxku/Allium58CAD/assets/167131775/d38142fe-e0d3-477d-851a-7db4f9beb0b4) from the Tools layer temporarily activates the default layer, allowing you to enter letters and words with the arrow keys untill a break key is press, when it will automatically return to the default layer. Break keys for the Temporary alpha layer access are spacebar, enter, return or other break keys such as the parentheses and brackets

      
# Legend Layout Guide
![Legend Guide](https://github.com/zxku/Allium58CAD/assets/167131775/0453577a-7bf1-47eb-ae9f-0f5b584b51cd)
![LEGEND](https://github.com/zxku/Allium58CAD/assets/167131775/621a4df4-9f2f-48d7-ad08-32f0730ce9aa)
[Link to FK custom layout](https://fkcaps.com/custom/9WTR81) If you create a login, you should be able to modify this for your own purposes.


## Status

Initial build underway...     As of 4/30/2023 this is still a work in progress 


## Photos

![Allium58CAD Keyboard](docs/photo-2.jpg)


## Case

- Top Plate & Low Profile Bottom Case:     ...To Be Added...



# PCB Trimming Instructions: ...work in progres...
>[!warning]
>This section should be attempted with caution to make sure you dont render your keyboard unusable. Hoping to find an alternative solution for this in the future, but for now the modification will have to do.

    a) The Allium58 PCB will require slight trimming on the lower right corner of the left hand PCB. This puts the spacemouse in a comfortable position to allow your ring and pinky fingers to reach the Control, S, D, A, and Escape buttons without repositioning your hand from the spacemouse. (S, D, and A are solidworks specific shortcut examples. These can be programmed differently for a different software)
    b) I recommend throughly taping off the rest of the exposed PCB with removable painters tape etc. to protect it from dust and debris.
    c) A dremel tool with a cut off wheel works well. A fine tooth coping saw could probably also be used.  Follow the template below to make sure you dont overcut. 

     > [!important]
     > ...Add Template Here...

>[!Caution]
>------ Overcutting the PCB could render the bottom row of keys unuseable! Be cautious and precise to make sure you aren't cutting through any of the circut traces in that corner of the board!------


## Firmware

- [ZMK](https://github.com/zmkfirmware/zmk "ZMK") - supported
- [ZMK config files](https://github.com/zxku/zmk-config)
- Keymap file (WIP)
- [Custom labeled MBK Keycap set](https://fkcaps.com/custom/9WTR81) - In PBT white, allows for a custom color dye job!
- Optional Customization: [Custom color mod keys MBK keycaps](https://fkcaps.com/custom/U5X2FC)
- Solidworks Shortcuts to Program (WIP)[Solidworks Shortcut List  -  Allium58CAD.pdf](https://github.com/zxku/Allium58CAD/files/15178827/Solidworks.Shortcut.List.-.Allium58CAD.pdf)


# Solidworks Shortcuts Sketching and Modeling 

>[!Note]
>In this list, I have only included the shortcuts relevant to the Tools layer of the Allium58CAD key layout. The full List, including defalut shortcuts, is availible as a PDF in the firmware section.

|Catagory|Command|Shortcut Keys|
|-----------:|:-----------------------------:|:-----------------------|
|Tools|Select over Geometry..|T|	
|View	|		Orientation..		|	SpaceBar			
|Others	|		Show the Hovered-over Component/Bodies		|	Shift+TAB			
|Tools|			Construction Geometry..		|	Shift+Q			
|Tools	|		Spline..		|	Shift+Period			
|Tools	|		Circle..		|	Shift+Num +			
|Tools	|		3 Point Arc..		|	Shift+Num *			
|View		|	MotionManager..		|	Shift+M			
|Others	|		Collapse all Items.	|		Shift+C			|
Tools		|	Override Dims on Drag/Move..	|		Shift+9			
Tools		|	Close Sketch to Model..	|		Shift+8			
Tools		|	Corner Rectangle..	|		Shift+6			
Tools		|	Convert Entities..	|		Shift+5			
Insert	|		Derived Sketch..		|	Shift+4			
Tools		|	Straight Slot..		|	Shift+3			
Tools		|	Offset Entities..		|	Shift+2			
Tools		|	Display/Delete..		|	Shift+0			
Others		|	Shortcut Bar		|	S			
View		|	Wireframe..		|	Q			

Tools		|	Line..	|		L,Shift+Num -			
Others			Scroll to FeatureManager tree top			Home			
Tools			Show Spline Handles..			H,Shift+1			
Tools			Magnified Selection..			G,Alt+4			
Others			Scroll to FeatureManager tree bottom			End			
Edit			Delete..			Delete			
Others			Move Selection Breadcrumbs, Confirmation Corner			D			
Edit			Undo..			Ctrl+Z				
Edit			Paste..			Ctrl+V			
Others			View Selector			Ctrl+SpaceBar			
View			Previous View..			Shift+Ctrl+Z	(Shift + Undo combo)		
Edit			Paste Appearance..			Shift+Ctrl+V	(Shift + Paste combo)	

File			Save..			Ctrl+S

Tools			Unlock..			Ctrl+Alt+Shift+Num /

Others			Isometric			Ctrl+7			
Others			Bottom			Ctrl+6			
Others			Back			Ctrl+2			

Tools			Lock..			Alt+Shift+Num /			
Tools			Check Out..			Alt+Num 8,Alt+8			
Insert			Sweep..			Alt+Num 5,Alt+5			
Tools			Silhouette Entities..			Alt+Num 4,Shift+7			
Insert			Plane..			Alt+Num .,Alt+Period			
Insert			Extrude..			Alt+Num *			
Insert			Revolve..			Alt+3,Alt+Num 3			

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

## Ordering Parts

- Pre built Wireless: (https://shop.beekeeb.com/product/wireless-allium58-choc/)
  >[!note]
  >Although Beekeeb does not currently offer an unsoldered DIY kit for the Choc version of the Allium58 on his website, he is very responsive, and if asked nicely he could probably send you one.
  
## External Libraries


## More Information



## Credits

This fork by zxku is an open source hardware project originally created by [beekeeb](https://beekeeb.shop) and other contributors. It is based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro).

[<img src="docs/beekeeb.png" height="80" />](https://beekeeb.shop)
