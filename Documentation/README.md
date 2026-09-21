Assembly
======


# Materials & tools

Tools you need:
* Soldering Iron + Solder + Flux
* Wire Stripper
* T2 Screwdriver
* Flathead Screwdriver
* 4,2mm and 2mm Drill + means of holding it, a battery powered drill works but a Pin Vice would be more controlled
* Hotglue gun
* FDM 3D printer
* SLA 3D printer
* CSR USB SPI Programmer

Parts:
* Assembled PCB including QCC3008
* Lithium battery (see below what to choose)
* 6mm Microphone capsule
* DT 770 headphones
* 26AWG / 0,15mm^2 Wire


# Process steps:
+ Print all the parts
+ Program the PCB
+ disassemble the Headphones
+ attach the Lightpipe
+ solder the microphone and glue it into the Headphone casing
+ glue the PCB in
+ solder the battery
+ assemble everything


# Programming
Solder a 1,27mm Pin header to some wires. To program the PCB just plug the pin header into the PCB and hold it on an angle to make contact. 
Pin out is self explanatory, check the PCB files and labelling on the programmer.
"+BATT" doesn't need to be connected if you already have a battery connected. Without a battery, this pin can be connected to the 3,3V output of the CSR USB to supply power to be PCB while programming.
Upload the Config file with the "ADK Configuration Tool". 
+ Open the program
+ connect programmer to PCB
+ select the right device
+ click "go configurable"
+ hold play/pause button to enable PCB
+ under File click "Open Config Set Dump"
+ click "Write Device"
+ click "Go Normal"
done

Set the Bluetooth name by opening PSTool.
Select the right device click "ok" and use the filter to search for "Name".  Add your desired name and click "Set" followed by "Reset & Close" -> done.


# Battery

Many different battery will work. You trade off battery runtime with internal volume and added weight. 
I used a 7,6mm x 18mm x 55mm cell with 600mAh. This cell is relatively big and needs modifications to the internal "cage". Three posts need to be cut out.
The maximum size that fits in the internal cage without modification is 8x10x50mm. so a 801050 cell. This cell fits in the internal slot of the cup.
Even a 100mAh cell will give good batter runtime of ~ 5h depending on listening volume.
A protected cell isn't necessary here as the circuit already includes short circuit, over charge and over discharge protection. 
The current PCB doesn't feature a battery NTC to halt charging at extreme temperatures. So make sure to only charge in room temp environments. (or change the PCB and software to include it)

# Disassembly

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/dissassembly.jpg "Disassembly")

Use the T2 screwdriver to remove the headband holders from the left ear cup. Remove the ear cushions by carefully sliding them from the rim.
A flathead screwdriver can now be inserted in slots around the ring that hold the driver inside. Use a prying motion to unclip the ring. 
Desolder all wires from the driver - including the wire for the right side driver as well as the audio input cable. 
Remove both cables from the cup by pulling the metal clips from the strain relive. 
The left Earcup should now be completely free.
Keep all the parts safe except for the Audio input wire. It can be discarded as its not needed anymore.

# Cup modifications

Attach the printed drill guide by sliding it into the bottom hole (the one where the audio cable used to be).

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/drillguide.jpg "drillguide")

Drill the 2mm microphone hole first. Its location isnt super critical. Keep the 2mm drill bit in the formed hole to keep the guide aligned while drilling the button holes.

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/drilling.jpg "drilling")

Drill the remaining 3 holes. Make sure to keep the guide aligned. Its easy with a pin vice but a battery powered drill works too.

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/drilling_done.jpg "Drilling Done")





