# MSGC-Waterproof-Termination
Files and Documentation for "V3" Waterproof Balloon Termination System

Designed by:
- Andy Kirby
- Tim Uhlenbruck
- Lance Nichols
- Isaac Schmidt

##Abstract: Waterproof Inline Flight Termination System for Ocean Bound High Altitude Balloons
This project sought to develop an inline flight termination system capable of surviving in damp and intermittently submerged conditions. These conditions would allow for this device's use in ocean bound flights and flights that start or fly through rain storms. 

##Waterproofing
The waterproof box was designed to be easily 3D printed in three parts. Two lids with O-ring grooves and counterbores for bolts on one lid and for nuts on the other that lie outside of the O-ring grooves. The main housing of the box has two shelves on either side for the cut down board to be bolted to. It also features holes for the bolts to pass through as well as a hole on the side to allow a seatbelt to be tied to the box. The final detail is the two holes on opposite ends intended to be taped so two nylon compression fittings (1/8” NPT - 1/4” tube Parker 2GUW3) can be screwed in. A 9/16” diameter silicon septum is cut from 1/8” thick 50A durometer silicone sheeting and inserted inside the nut of the compression fitting. A sewing awl is used to insert a length of waxed string through the septa.  When the awl needle is withdrawn the hole produced shrinks back forming a waterproof seal between the septa and the line.  Waxed thread is used to keep water from wicking down the fibers in the line and into the enclosure.

##Hardware
The PCB notably features a channel that contains the line against the attached nichrome wire. 80-34 gauge nichrome is suspended 0.1” between two terminals and is driven with a MOSFET making it red hot and severing the line. The system utilizes the XBEE 3 Micro for both radio and microcontroller purposes. This along with the improvements in reduction of components improved the size of the board. One 1.5V AAA battery is employed as the power source, along with a boost converter to achieve the 3.3V required for the XBEE. 

##Software
The software is written in MicroPython with little complexity, appropriate for its purpose. The program monitors the radio for the cutdown command and sets the MOSFET pin high for ten seconds when it is received. The program also ensures that the MOSFET is not run more than once per command sent from the ground team.

##Control
The system receives the command to cut down over a local XBEE 3 radio network. During testing, this command was sent from a central payload containing an Iridium satellite modem. The modem in turn received commands from the Iridium satellite network which were uplinked by the ground team.