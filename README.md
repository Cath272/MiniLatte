# MiniLatte



## Introduction
MiniLatte is a Mini Pc made using the LattePanda Mu compute module

## General description
The device is a x86 desktop comuter with lots of IO ports like USB, PCIe, Ethernet and more. 

## Problems
Esp32 and GL3224 do not enumerate sometimes
The headphone jack is not correctly wired and i did not figure out how to fix it yet

### Block diagram
![block diagram](lucrare%20licenta/images/MiniLatte_block.png)

## Hardware Design
### LattePanda Mu 
The LattePanda Mu is a compute module with rich IO with up to 9 PCIe slots, lots of usb, gpio and much more.
The module is Avaliable with 8 or 16gb of LPDDR5 ram, and an Intel N100 or Intel N305 CPU, the module uses a SODIMM DDR4 slot to connect to the carrier pcb

## ICs 
The board uses a lot of ics, so to avoid a long section about ics you can find the complete list of ICs in an the BOM generator in KiCad
All parts that are not generic (Like caps and resistors) are directly imported from LCSC so they also have an LCSC id 
Please read the warning on the IT8851-128 if you want to build the board.

Some of the chips are not available on components sourcing sites like DigiKey or LCSC but can be easliy found of Aliexpress.
Some notable Ics used by the board:

### VL822-Q7
USB 3.2 Gen 2 USB Hub 10Gbps with 4 downstream ports, used to increase the number of usb from 2 to 8

### GL3224ONY
USB 3.2 Gen 1 to dual Sd card controller, used to have 2 sd cards slots on the pcb

### IT8851FN-128
Usb Type C DP alt mode Controller, used for having a usb C port with Displayport output, the chip is a bit hard to get but you can find it on Aliexpress if you ask some BOM sellers. The chip also needs to be flashed so ask the Lattepanda team for the flashing firmware.
The chip variant needs to be "IT8851-128" EXACTLY, other variants do not work.  

### TPS51275

Main Power Ic, used for DC-DC from 20v to 3.3v and 5v

### VL162
USB Type-C 2:4 differential channels mux switch and integrated CC logic function for USB 3.1 type-C application. Needed for the type C ports to work both ways.

### RTL8125BG
PCIe to 2.5Gbps Ethernet controller

## Schematic
[Schematic](PCB/MiniLatte.pdf)


## PCB

![kicad_front](lucrare%20licenta/images/pcb_kicad_front.png)
![pcb_front](lucrare%20licenta/images/pcb-top-front_2.jpg)
![pcb-bottom.jpg](lucrare%20licenta/images/pcb-bottom.jpg)

## LED Array

The board connects to a secoundary board that an WS2812C LED Array made out of 220 leds (5x44). The Controller for the LEDs is on the main pcb and it is a ESP32 C3


## Case and 3d design

![case](lucrare%20licenta/images/case.jpg)
![case_front](lucrare%20licenta/images/case-front.png)
![case_back](lucrare%20licenta/images/case-back.png)


The case was make using AutoCad and exported to stl
The stl files can be found in the 3D Models folder.
The case is made of 2 parts and there is a diffusion layer for the LED PCB

## Bachlors Degree
This project was made as a project for my bachlor's degree, you can find the thesis and a shorts powerpoint in the "lucrare licenta" folder but it is in romanian. It provides some details of the building process of this pcb. You can also find some extra pics in the same folder.



