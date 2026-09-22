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

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/multiple.jpg "PCBs")

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

# LED Indicators
There are 3 LEDs to display the current status Red/Green/Blue. The light pipe makes them visible on the USB-C port.
Everything here can be configured according to your liking. The current config file results in the following behaviour:
Red LED -> shows battery status and charging status. When the battery state is lower than 10%, the red lights starts pulsing. When charging, the red light is solid.
Blue LED -> shows Bluetooth availability, when no bluetooth device is connected this light is flashing
Green LED -> shows connection and charging status, when a Bluetooth device is connected this LED fades slowly. When a device is sending audio, this light fades fast. When the battery is fully charged, this light turns solid.

# Button functions
The three buttons can be reconfigured. Current setup reacts like this:
Upper button -> "single click" Volume increase, "click and hold" Volume increase constantly, "Double click" next title
Upper button -> "single click" play/pause, "click and hold" power off/on, "Double click" enter bluetooth peering
Lower button -> "single click" Volume decrease, "click and hold" Volume decrease constantly, "Double click" last title


## Disassembly
###### Attention! The pictures show revision 1 of all the parts. The microphone placement and pcb changed a little. The guide still works the same.


![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/dissassembly.jpg "Disassembly")

Use the T2 screwdriver to remove the headband holders from the left ear cup. Remove the ear cushions by carefully sliding them from the rim.
A flathead screwdriver can now be inserted in slots around the ring that hold the driver inside. Use a prying motion to unclip the ring. 
Desolder all wires from the driver - including the wire for the right side driver as well as the audio input cable. 
Remove both cables from the cup by pulling the metal clips from the strain relive. 
The left Earcup should now be completely free.
Keep all the parts safe except for the Audio input wire. It can be discarded as its not needed anymore.

## Cup modifications

Attach the printed drill guide by sliding it into the bottom hole (the one where the audio cable used to be).

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/drillguide.jpg "drillguide")

Drill the 2mm microphone hole first. Its location isnt super critical. Keep the 2mm drill bit in the formed hole to keep the guide aligned while drilling the button holes.

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/drilling.jpg "drilling")

Drill the remaining 3 holes. Make sure to keep the guide aligned. Its easy with a pin vice but a battery powered drill works too.

You should end up with 4 clean holes afterwards. 

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/drilling_done.jpg "Drilling Done")

## Microphone

Glue the printed Mic holder into the ear cup centered over the drilled 2mm hole. Use the angled face on the print to align the holder. Make sure to not fill the 2mm hole or the printed part. Just a little glue on the outside is all thats needed. 

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/microphone.jpg "microphone")

Solder 50mm wire to the Mic. I used color coded flat ribbon but everything works. You can even use a bit of the discarded audio input wire. 

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/Micsoldered.jpg "microphone soldered")

Press the mic into the printed holder and seal the backside with hotglue.

## Lightpipe

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/lightguide.jpg "lightguide")

###### Use translucent Hotglue!
Apply two small drops of hot glue to the LEDs next to the USB-C connector. Press the lightpipe into it and keep it aliged to the PCB edge while the glue is still warm.

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/glued.jpg "glued")

Sqeeze out left and right of the connector doesnt matter and is expected. It wont interfere so dont worry about it.

## Glue the PCB into the earcups

Slide the PCB into the housing. Start with the upper button and work your way towards the USB connector. 

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/glueIn.jpg "PCB glued")

Apply two small drops of hot glue to keep it in place. Make sure the board is aligned while the glue hardens. 
Repeatedly click the buttons to make sure they spring back. If the board isn't aligned properly, the button may stay stuck!

## Solder the wires 

![alt text](https://github.com/farbefreak/DT770-BT-Mod/blob/main/Documentation/images/finished.jpg "Done")

Attach the battery last. The board goes live when you do so solder the drivers and microphone first to avoid shorts.

Now you are almost done. Close the headphones up - same as disassembly but in reverse ;)
Check for interference by checking if the driver sits flush and doesnt apply force to anything. Make sure all wires are where they belong and clip the ring back in. 

I found it easiest to twist the ear cushions onto the rim. 







