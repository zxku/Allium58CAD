# Allium58CAD

![Allium58CAD prototype2](https://github.com/zxku/Allium58CAD/assets/167131775/ff9a7fd3-d8ad-49f6-a4e2-4372c999faab)


&nbsp;  
___________________________________________________
___________________________________________________
THIS IS A WORK IN PROGRESS...
___________________________________________________
___________________________________________________

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

&nbsp;  
The Allium58CAD is a wireless open source 6*4+4keys column-staggered split keyboard that integrates an ortholinear QWERTY layout, SpaceMouse, macro pad, and a left number pad into a single system to optimize productivity and ergonomics in 3D design, CAD, Engineering, and 3D CNC programming. 
It is a fork of the [Allium58 by beekeeb](https://github.com/beekeeb/Allium58) which is in turn based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro). 

&nbsp; 
  >[!note]
  >The SpaceMouse itself is a seperate product sold by [3DConnection](https://3dconnexion.com/dk/product/spacemouse-wireless/) The Allium58CAD is designed to
integrate with the SpaceMouse by snapping tight to the SpaceMouse base with magnets.

  >_If you have never used a SpaceMouse, I highly recommend them. There is definitely a learning curve, but once you figure it out the SpaceMouse is a lifechanging improvement for navigating in a 3D space.It alows you to manipulate the 3D space simultanious and independent of what your mouse is doing. This lets your mouse be dedicated to selcting, drawing, etc._

>_One beginner tip: Turn off perspective view to make navigation more predictable._



  >[!tip]
  > _This design is configured for right handed mouse use, but could be easily mirrored to work in a left hand dominant setup._


&nbsp;  
# Purpose of the Project


The biggest downside of a spacemouse is that you must remove your hand, reaching up and over it to hit any of the keyboard keys. While most 3D software can be navigated almost completely with a mouse and the menus, shortcuts are much more efficient, and it is often still nessessary to use some of the modifier keys in conjunction with the mouse. 
The Allium58CAD was developed after scouring the internet for both commercial options and custom implementations to address this issue, and not finding a satisfactory solution. The Allium58CAD integrates a keyboard, SpaceMouse, number pad, and macro pad into a single system and I am convinced that “this is the way”.  

Most of the availible solutions add additional buttons/keys around the SpaceMouse Joystick, basically adding a macro pad to go with the SpaceMouse. I, along with others, have discovered the utility of a left hand number pad, so that I can quickly enter in values without taking my hand off the mouse.  When you put all of this together, it leaves you with a left number pad, a macro-pad, a spacemouse, and a traditional keyboard all taking up room on your desktop.  Furthermore, since they are all seperate, they are unintentionally getting shifted around the desktop, which interferes with the muscle memory of what is where.


&nbsp;  
###### **Solution:**


- Allium58CAD utilizes ZMK programming and a custom case to integrate all of these items into a single system, decreasing desktop clutter instead of adding to it.
  
- The split keyboard functionality has the added benifit of leaving desk space directly in front of you for hardcopy reference documents (such as the Machinery's Handbook).
  
- The magnetic snap function allows the board to be used as two seperate keyboards, or snapped together to function like a unibody split keyboard

- Most SpaceMouse users start off with the basic spacemouse model, getting a feel for using it before commiting further investment for added utility. The Allium58CAD allows users to utilize their existing equipment instead of reinvesting in a whole new module.

- ZMK allows users to customize the key layout for their paticular preference or software. The starting keymap is designed to work with solidworks, but it can be adapted for other software packages.


    >I'm hoping it will be easier to tweak and modify my [existing keymap](https://github.com/zxku/zmk-config/blob/main/config/lily58.keymap) instead of building one from scratch like I did. Same thing goes for the FK custom keymap legend included in this documentation.  It ended up taking quite a bit of time to compile both of them, and I wish I had had someone elses map as a base to modify, instead of building the whole thing from scratch. 


I chose to use low profile choc switches because of the angle at which you hold the SpaceMouse. The low, flat profile puts the mod keys in the right position to be easily reached while manupulating the SpaceMouse joystick. 
Tenting of the keyboard case was tested, but it got in the way of using the SpaceMouse. Raising the spacemouse up to compensate for the tenting height was tested as well but made the spacemouse akward to use. 


&nbsp;  
# Keymap 

The included keymap is designed to combine all the basic funcitons of a standard QWERTY layout with a left handed number pad, a macro pad, and a navigation pad. This is accomplished using a combination of varrious ZMK behaviors. An in depth explination is beyond the scope of this document, I recommend reading up on the official [ZMK Behavior documentation](https://zmk.dev/docs/behaviors/)


### Keymap Ideology and Theory
- One of my goals was to make sure that all of the standard availible QWERTY symbols be accessible in the default layer.
- The second priority was a left hand key layout that would provide both quick access to needed shortcut and macro keys while also providing an efficient 4x3 number pad within easy reach.  
- Though the top number row has fallen out of favor with many ergonomic keymap enthusiasts, one of the main reasons for choosing the Allium58 layout was that extra row. Though, not for a *top* number row. That additional top row of keys is nesessary for a proper 4x3 number pad layout, an important addition for anyone working with lots of numbers.
- Instead of numbers on the top row of the default layer, it has just the symbols as the base fuction of the key. The number pad is availible via the momentary navigation key for quick access any time I need to imput numbers. I find the number pad much faster than the number row. And I find myself using that top row for the symbols far more often than I use the numbers.
- instead of splitting into many layers of working commands, I thought it made more sense to use 2 layers, and utilize modifier keys on the second layer to fit the extra commands. The benifit of this, is if you work in multiple 3D modeling programs you can seperate all of its related commands in a new layer. At that point I would probably alter the programming to utilize the layer key in conjunction with the number pad keys to select the active 3D program layer.
I would program new layers to be conditional over top of the default `tools` layer such that you can still easily swap back to the alphabetical keys. This also saves you from duplicating any functions on the right keypad that are not getting changed (use `&trans`). It could be implimented in a simmilar way to the activation layers for the `Wire` layer and `Num Lock` layer
- Realistically, the only reason for choosing a 4 row keyboard was to fit the number pad. It would actually be possible to use a corn style pcb on the right hand. I decided to utilize those extra unused keys on the right keypad of the `tools` layer for math and engineering symbols that I normally have to enter an Alt code for. There is plenty of room for customization in this area if you have differnt needs.



### Layers Explained
#### Default Layer `Layer 0`
  - Instead of number keys across the top row of the default layer, it has just the corrisponding symbols as the base fuction of the key. The number pad is availible via the momentary navigation key for quick access to enter numbers. The number pad much faster than the number row for numerical entry. The symbols attached to those keys are used more often than I use the numbers. The parentheses in particular come to mind...
  - The layout tries to maintain as much standard QWERTY layout as possible, but not everything would fit perfectly. Several of the less used keys, : , ; , [ , ] , { , } , and DELETE, are implimented as side by side combos. Just hit two keys at the same time and it will output the corrisponding character.
  - Caps Lock is activiated using a double tap on the shift key.  It is a smart caps lock, so it will dissengage when any non alphabetical key is pressed. Traditional Caps Lock is activated with a tripple tap.
     
#### Tools Layer `Layer 1`
  - The "Tools" layer contains the number pad and the shortcut keys on the left half, with the navigation arrow keys and additional math and engineering related symbols on the right half
  - The left hand of this layer is intended to be the primary imput while 3D modeling, while your other hand remains on the mouse. This is why the left side is crammed full of programing to hold all of the macros in addition to the all important number pad for dimention and data entry. It should be noted that for solidworks, these keys do not cover all of my most frequently used commands. I have a lot of frequently used commands mapped to mouse gestures in the custom configurator.
  - In general, the Ergo Keyboard Community encorages no legend keycaps, touchtyping from memory only. However, the infrequency of using some of these shortcuts makes memorizing them difficult, Thus why I thought it would be important to have labeled legends. The touchtype memory is also effected by the shifting of the hand durring use. Although a much shorter distance that the standard SpaceMouse setup, the hand will still be required to shift back and forth between the number pad and the spacemouse position. (Additional Homing Keys are being considered to help this).
  - There are two other very frequently used commands that I have left out of the keymap because I have mapped them to the two keys on the spacemouse base.
    1) _Fit Normal To (a custom macro)_ - Executes "normal to" and then zooms to fit on the selected item, if one is selected. Great for working with non orthogonal working planes. Macro is set to execute "Normal To" and then "Zoom to Selection" in that order. If nothing selected, the zoom does nothing and it just re-orient to the closest orthogonal view. 
    2) _Lock Rotation_ - This command is specific to the SpaceMouse and is used to lock it into a pan only mode. Excellent for moving around a sketch on a werid plane. 
          >I've included a copy of my solidworks workspace settings in the firmware section for reference to how I have the other commands set up)
  
  
  ###### Tools Layer Modifier Keys
  -  Workhorse and Control Mod Key Placement: All of the most used keys are grouped close to the spacemouse such that they should be able to be pressed with pinky or ring finger while holding the SpaceMouse Joystick. <sup>[1](#1)</sup>
  - Sketch Commands:  All of the sketch related shortcuts are activated using the Shift key as the modifier and then the legends top left listed command will be the action.
  - Model Commands:   All of the Model and Assembly related commands are activated using the Alt key as the modifier. The action is listed as the second line in the top left corner of the legend, underneath the sketch command mentioned above.
    

     <a name="myfootnote1">1</a>: _Some of the keymap code references an A, S, and D keys mapped to the G, F, and R key locations. These keys are referencing default shortcuts key chosen by solidworks, I only kept the names for continuity. This is also why the icons incorperate the A and S, to help solidworks users familiar with those commands._


  - In general, the Ergo Keyboard Community seems to recommend legendless or blank keycaps, encoraging touchtype from memory. However, the infrequency of using some of these shortcuts makes memorizing them difficult, Thus why I thought it would be important to have labeled legends. The touchtype memory is also effected by the shifting of the hand durring use. Although a much shorter distance that the standard SpaceMouse setup, the hand will still be required to shift back and forth between the number pad and the spacemouse position. (Additional Homing Keys are being considered to help this).     
  - The "Tools" layer is accessed in two ways:
    1) A layer toggle on/off on the lower left pinky on the left keypad.
    2) A "sticky momentary layer" toggle on the thumb of the right pad. This momentary switch is positioned such that it is easily reached while pressing the arrow keys.
         >("sticky momentary layer" is the term I use for urobs capsword [PR 1451](https://github.com/zmkfirmware/zmk/pull/1451#) that I use. In fact I use his entire [fork](https://github.com/urob/zmk). This PR allows you to impliment smart layers which is a modified capsword type of behavior for layers and things that are not alphanumerics. So after you tap the arrow nav toggle button, the layer will stay active untill you type anything that isnt a nav key, number key, or the layer toggle key)

   >[!warning]
   >There are a couple of non-model related commands on the tools layer, such as the Check-In and Check-Out commands that are specific to PDM use that my not apply to everyone. If creating your own build, assess the provided list of default commands to make sure that they meet your needs before ordering a set of custom keycaps.

#### Utility Layer `Layer 2`
  - This contains needed utility keys such as boot mode and bluetooth connectivity buttons.
  - Layer can be accessed from the Default or Tools layers by holding the left layer key. This layer is designed with a sticky layer. you must hold the layer key to activate it and then press the desired action. The layer is automatically deactivated after that keypress to prevent accidental keypressing. To subsequently hit a different key in the utility layer, you would have to hold the layer key again. 
  - Programming is implimented to require a hold to activate boot, reset, and BT clear keys. This is to prevent accidental activation.
  - Blue Tooth Clear only clears the pairing for the currently selected connection, each pariring must be cleared individuallly. 
  - The key for bluetooth disconnect of each blutooth pairing is not labeled in the legend but are located in the row below their corrisponding selector key.
  - The Num Lock key is used to toggle the number layout in the tools layer to output keypad numbers presses instead of number row presses. This is occassionally needed for some programs where they are mapped for a different use, or for entering in alt code characters.
    _See Num Lock Layer below for implimentation._

#### Wire Layer `Layer 3` and Wire Activate Layer `Layer 5`
  - This layer is used only to impliment a toggle key function. This allows a key to output one macro with the first press, and a different macro on the second before switching back to the first macro if pressed a third time. 
  - Wireframe to shaded with lines requires two differnent commands in solidworks, but I wanted a key that would toggle back and forth between them.
  - The first keypress in the tools layer sends the first macro and then activates this layer that is completely transparent exept for this key.
  - The Wire Activate layer is completely transparent and is used to activate the wire layer on the conditional basis that the Tools layer is active. This way the wire layer function will only be active when the tools layer is also active.  
 
#### Num Lock Layer `Layer 4` and Num Activate Layer `layer 6`
  - When active, the Num Lock layer overlays the number keys on the tools layer, and will output the equivelant number pad keypress. Most of the time this will not be needed. However, the bindings of the number row and the number pad numbers are treated slightly different by the system and in some programs they are mapped to different things. Alt code symbols are an excellent example of this.
  - The Num Lock layer is completely transparent except for the numbers. 
  - The Num Activate layer is completely transparent and is only used to activate the Num layer on the conditional basis that the Tools layer is also active. This way the Num Lock layer will turn itself on and off in tandom with the tools layer. This way it wont interfere with the functions on any other layers.
  
#### Combos and Macros
  - Combos and other behaviors are utilized to fit some things that didn't otherwise have a spot. Combo keys are indicated by little icons on the touching edges of both keys.
  - All Combos are side by side keys making it easier to remember them. 
  - Macros are heavily utilized to output the alt codes for the symbol keys on the right side of the tools layout.
    
#### Layer Switching Keys
  - The outermost lower left key (![image](https://github.com/zxku/Allium58CAD/assets/167131775/769b777b-341b-4cc9-90ec-40f4285b0699)) on the left keypad switches between the default and the tools layer, holding it will toggle the utility layer.
  - The utility layer is a momentary sticky layer. The left layer key must be held to activate the layer, and then it is only good for one keypress before deactivating.
    - While the Layer Key ![image](https://github.com/zxku/Allium58CAD/assets/167131775/769b777b-341b-4cc9-90ec-40f4285b0699)
 on the left keypad toggles the layers on and off, the Navigation layer key ![image](https://github.com/zxku/Allium58CAD/assets/167131775/1077704a-1e81-4a24-a88b-078da37be6c5) on the right keypad is used for temporary layer activation utilizing the smart layer function of [urobs PR #1415](https://github.com/zmkfirmware/zmk/pull/1451#) 
    - Pressing the Navigation layer key ![image](https://github.com/zxku/Allium58CAD/assets/167131775/d38142fe-e0d3-477d-851a-7db4f9beb0b4) from the Default layer temporarily activates the Tools layer, allowing you to enter numbers and navigate with the arrow keys until spacebar, enter, return or a letter is pressed, when it will automatically return to the default layer.
    - Simmilarily, pressing the Navigation layer key ![image](https://github.com/zxku/Allium58CAD/assets/167131775/d38142fe-e0d3-477d-851a-7db4f9beb0b4) from the Tools layer temporarily activates the default layer, allowing you to enter letters and words with the arrow keys untill a break key is press, when it will automatically return to the default layer. Break keys for the Temporary alpha layer access are spacebar, enter, return or other break keys such as the parentheses and brackets

&nbsp;        
# Legend Layout Guide

### Keycap Legend Location Layout:
![Legend layout guide](https://github.com/zxku/Allium58CAD/assets/167131775/5a431003-e01b-44c2-8be6-0a0949a80c74)



### [Full Legend:](#fk)
![Full FK Custom Allium58CAD Keycap Legend](https://github.com/zxku/Allium58CAD/assets/167131775/301a595e-6371-44ca-bf71-c4f385eb0e90)


[Link to FK custom layout](https://fkcaps.com/custom/N1EN6S){#fk} If you create a login, you should be able to modify this for your own customizations.  *If you go back to the keycap selection you can choose to change to precolored keycaps instead of blank PBT.*
- You can also piece together a [custom remix](https://fkcaps.com/custom/U5X2FC) to add a little personality and flair. 


&nbsp;  


### Keymap Legend Definitions and Icons Keybindings
###### Most Used
  
  
|Key(s) | Legend Symbol| Command | 
|-----|:----:|------------------------------------------------------------------------------------------| 
G | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/e9f5ec32-9b74-4e83-a9e3-07bf1ad12107) | Opens a Shortcut Bar Menu at your cursor for quick selection. (This may get less use as I learn the shortcut keys)
R | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/f2d4ac75-305a-49ac-b0d9-a5fd7ad74c7d) | Toggles command option type. Toggles through availible command options such as tangent arc vs. 3 point arc. 
F | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/96e68555-f19a-46d3-a23c-b0344689cf55) | Brings confimation or cancellation box right to your mouse.
Ctrl | | Multi Item Select
Space | |  Shortcut for the orthogonal view selector cube. 
Tab | | Used to Hide or Show a part in an assembly
Delete, Alt, Shift, Esc, Enter |  | Need for these should be somewhat obvious
Ctrl + G | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/0f770d24-6b35-4175-a9a7-7f9e12531ad7) | Redo
Ctrl + F | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/7e7e16a3-b0ec-4297-a5a9-cad5a4fa2781) | Undo
Ctrl + R | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/2828d102-53e8-4ee7-a732-5c4d31db29b8) | Expand Quick Access Feature Tree
V & Ctrl V | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/b1df7fdb-35c6-42ca-b534-1e2eb57c0165) | The combination of these two commands will toggle the view between wireframe and shaded with edges. Gives you X-ray vision...
Ctrl + Esc | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/40c1eb96-3cf1-4cae-a795-c31c9173f367) | Save Shortcut

###### Additional Command Keybindings
  |Key(s) | Legend Symbol| Command|
  |----|:----:|:------------------------------------------------------------------------------------------|
  Shift + 9 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/0b328cb1-4846-4b27-badc-13d96a7e5f34) | Override dimentions on Drag/Move
  Shift + 8 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/ae43ea01-5e15-4b0d-857f-3ce816e3b133) | Close Sketch to Model
  Shift + 7 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/e209138b-2930-4cf3-9b09-91801f26b6a2) | Silhouette Entities
  Shift + 4 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/edabc6e0-9526-4d85-a424-9d162292e928) | Derived Sketch
  Alt + 4 |![image](https://github.com/zxku/Allium58CAD/assets/167131775/8fb53452-710e-44d0-8e2a-51a3161f31a0) | Magnified Selection
  Shift + 5 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/3ad5990d-cc3d-40c1-8871-4f415776df43) | Convert Entities
  Shift + / | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/613d2405-0af0-42da-903a-2274b379ea01) | Fully Define Sketch
  Alt + / | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/a0a4c3cd-9318-4a29-8765-0536acf56466) | Select Other
  Shift + V | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/fce707dc-465f-4ad5-a968-b94b68bc9c22) | Toggle "For Construction"
  Alt + V | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/166128db-c771-4421-a623-358d46988dc3) | *\*Reserved for future Transparancy toggle coding*
  Utility + # | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/9c222693-71a1-42ce-a168-894ba67bac09) | Toggle External Power Mode
  Shift [Double Tap] | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/453aa30d-4242-405f-ac7e-170e14d1593a) | CapsWord with auto deactivation
Shift [Tripple Tap] | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/453aa30d-4242-405f-ac7e-170e14d1593a) | Traditional CapsLock function
Shift + 1 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/d46717c0-d6e3-417f-bcf9-1d857f3994f5) | Show Spline Handles
Alt + 1 | ![image](https://github.com/zxku/Allium58CAD/assets/167131775/32b725a5-5d40-4b3a-9bf7-aa73a8de67cb) | Spell Check


&nbsp;  
## Status

Initial build underway...     As of 4/30/2023 this is still a work in progress 

&nbsp;  
## Photos


&nbsp;  
### This picture is of the 3D printed moc up:
![Prototype Picture](https://github.com/zxku/Allium58CAD/assets/167131775/380984bc-6e11-4af9-8e7e-8524cc75f92c)


&nbsp;  
### Renderings:
![Allium58CAD prototype](https://github.com/zxku/Allium58CAD/assets/167131775/7d8de403-b1e2-47ef-907f-3594b26161f7)
![Allium58CAD prototype split](https://github.com/zxku/Allium58CAD/assets/167131775/04d745f9-60a9-4afb-99b2-9d7a1d351202)




&nbsp;  
## Case

- Top Plate & Low Profile Bottom Case:     ...To Be Added...


&nbsp;  
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

&nbsp;  
## Firmware

- [ZMK](https://github.com/zmkfirmware/zmk "ZMK") - supported
- [ZMK config files](https://github.com/zxku/zmk-config)
- Keymap file (WIP)
- [Custom labeled MBK Keycap set](https://fkcaps.com/custom/9WTR81) - In PBT white, allows for a custom color dye job!
- Optional Customization: [Custom color mod keys MBK keycaps](https://fkcaps.com/custom/U5X2FC)
- Solidworks Shortcuts to Program (WIP)
- [My personal Solidworks Workspace Settings Profile](https://github.com/zxku/Allium58CAD/blob/main/swSettingsReg%20Zac%20Alli58cad.sldreg)

&nbsp;  
# Solidworks Shortcuts Sketching and Modeling 

In this list, I have only included the shortcuts relevant to the Tools layer of the Allium58CAD key layout. The full List, including defalut shortcuts, is availible as a PDF in the firmware section.


&nbsp;  
#### Main Commands


|	|	 ****Quick Access Comands****			|	|
|-----------:|:-----------------------------:|:-----------------------|
|**Catagory**|**Command**|**Shortcut Keys**|
View	|		Orientation..		|	SpaceBar
Others	|		View Selector		|	Ctrl + SpaceBar
Others	|		Hide the Hovered-over Component/Bodies		|	TAB
Others	|		Show the Hovered-over Component/Bodies		|	Shift + TAB
Others	|		Show all the hidden Components/Bodies		|	Ctrl + Shift + TAB
Edit	|		Repeat Last Command..		|	Enter
Others	|		Expand/Collapse Tree		|	C
Others	|		Normal To		|	Alt + SpaceBar
Others	|		Zoom to Selection		|	Shift + SpaceBar
Others	|		Shortcut Bar		|	S
Others	|		Command option toggle		|	A
Others	|		Move Selection Breadcrumbs, Confirmation Corner		|	D
View	|		Wireframe..		|	Q
View	|		Shaded With Edges..		|	Alt + Q
Others	|		Spell Checker		|	Alt + Num 1
| |				|	 |
| |	**Sketch Commands**			|	|
Tools	|		Construction Geometry..		|	Shift + Q
Tools	|		Line..		|	Shift + Num -
Tools	|		Spline..		|	Shift + Period
Tools	|		Circle..		|	Shift + Num +
Tools	|		3 Point Arc..		|	Shift + Num *
Insert	|		Hole Wizard..		|	Alt + Num +
Tools	|		Fully Define Sketch..		|	Shift + Num /
Tools	|		Override Dims on Drag/Move..		|	Shift + 9
Tools	|		Close Sketch to Model..		|	Shift + 8
Tools	|		Silhouette Entities..		|	Shift + 7
Tools	|		Corner Rectangle..		|	Shift + 6
Tools	|		Convert Entities..		|	Shift + 5
Insert	|		Derived Sketch..		|	Shift + 4
Tools	|		Straight Slot..		|	Shift + 3
Tools	|		Offset Entities..		|	Shift + 2
Tools	|		Display/Delete..		|	Shift + 0
Tools	|		Show Spline Handles..		|	Shift + 1
|	|				|	 |
|	|	**Standard Commands**			|	|
Edit	|		Delete..		|	Delete
Edit	|		Undo..		|	Ctrl + Z
Edit	|		Redo..		|	Ctrl + Y
Edit	|		Cut..		|	Ctrl + X
Edit	|		Copy..		|	Ctrl + C
Edit	|		Paste..		|	Ctrl + V
File	|		Save..		|	Ctrl + S
View	|		Previous View..		|	Shift + Ctrl + Z (Shift + Undo Combo)
Edit	|		Copy Appearance..		|	Shift + Ctrl + C (Shift + Copy Combo)
Edit	|		Paste Appearance..		|	Shift + Ctrl + V (Shift + Paste Combo)
|	|				|	|
|	|	**Model and Assembly Commands**			|	|
Others	|		Select Other		|	Alt + Num /
Insert	|		Plane..		|	Alt + Period
Insert	|		Extruded Cut		|	Alt + Num *
Insert	|		Extrude..		|	Alt + Num -
Insert	|		Sweep..		|	Alt + 2
Insert	|		Revolve..		|	Alt + 3,
Tools	|		Magnified Selection..		|	Alt + 4
Insert	|		Sweep Cut		|	Alt + 5
Insert	|		Revolved Cut		|	Alt + 6
|	|				|	 |
|	|	**PDM Commands**			|	|
Tools	|		Get Latest Version..		|	Alt + 7
Tools	|		Check Out..		|	Alt + 8
Tools	|		Check In..		|	Alt + 9
|	|				|	|
|	|	**Quick View  Commands**			|	|
Others	|		Isometric		|	Ctrl + 7
Others	|		Bottom		|	Ctrl + 6
Others	|		Top		|	Ctrl + 5
Others	|		Right		|	Ctrl + 4
Others	|		Left		|	Ctrl + 3
Others	|		Back		|	Ctrl + 2
Others	|		Front		|	Ctrl + 1


&nbsp;  
## Bill of Materials (BOM)

### Required

| Name | Count | Remarks |
|:-|:-|:-|
| PCB | 1 set | |
| Top plate | 2 sheets | 1.2mm thick |
| Bottom plate / 3D printed case | 1 set | |
| OLED cover | 2 | |
| nice!nano or equivalent | 2 |  |
| Reset switch | 2 | |
| Diodes | 58 | SMD Only (SOD-123 Package) |
| Hotswap Sockets | 58 | Choc Recommended, [Gateron is slightly taller alternative)(https://showcase.beekeeb.com/the-keycaps-of-gateron-low-profile-key-switches-and-kailh-choc-v1-key-switch/) |
| Key switches | 58 | Sunset Orange Choc switches are recommended|
| Keycaps | 58 pieces |1u: 48 pcs, 1u convex: 6, 1u homing: 2,  1.5u: 2 pcs [(Link)](#FK)
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


&nbsp;  
## Ordering Parts

- Pre built Wireless: (https://shop.beekeeb.com/product/wireless-allium58-choc/)

 
_\*Although Beekeeb does not currently offer an unsoldered DIY kit for the Choc version of the Allium58 on his website, he is very responsive, and if asked nicely he could probably send you one._


&nbsp;  
## More Information

* {Official ZMK Documentation](https://zmk.dev/docs)

* [Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) by Nick Coutsos is a very handy GUI for creating keymaps. 
  * It wont code everything, especially the details of the custom PR patches by [urob](https://github.com/urob) but it sure helps for building and visualizing the layout code. 

* For understanding the nuances of the different hold-tap flavors and options, I found the animations of this beta [ZMK Hold-Tap Documentation](https://deploy-preview-1657--zmk.netlify.app/docs/behaviors/hold-tap) to be quite helpful. I dont know why it never got implimented, but be aware that some of the other sections in that ZMK document version contains out of date information and may be missleading. 

* [beekeeb's store](https://shop.beekeeb.com/). 
  - beekeeb also has an [etsy store]. I've noticed that sometimes there are things listed on etsy that are not listed on the offical store website, and vice-versa  

* [FK Custom Keycaps] has a very intuitive web based builder for custom keycap legends. There is quite a selection provided and there is also provisions for uploading your own custom font and or vector image.

* Rough guidelines for creating a [Custom Gradient Dye Job](https://www.reddit.com/r/MechanicalKeyboards/comments/1atzinr/gradient_handdyed_choc_keycap_set/). *\*Keycaps must be PBT for this to work!*

* [Interesting guide](https://imgur.com/a/LB65p) for implimenting ball bearing home key bumps. *\*Be sure to use stainless steel ball bearings, long term users reported back that standard carbon steel BB's were causing some staining from the formation of slight surface rust.    - For anyone with a perfectionism streak, the machinists version can be found [here](https://www.reddit.com/r/MechanicalKeyboards/comments/6r3n1t/ball_bearing_homing_keys/).


&nbsp;  
## Credits

This fork by zxku is an open source hardware project originally created by [beekeeb](https://beekeeb.shop) and other contributors. It is based on [Lily58 Pro created by kata0510](https://github.com/kata0510/Lily58/tree/master/Pro).


[<img src="docs/beekeeb.png" height="80" />](https://beekeeb.shop)


zxku is a pseudonym for Zac Morhous. A senior product design and development engineer who knows what he wants, and will over-engineer the shit out of it as a personal side project if it doesnt exist. 
