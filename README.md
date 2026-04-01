# MiniLatte

!!THIS DOCUMENT IS NOT COMPLETE

## Introduction
MiniLatte is a Mini Pc made using the LattePanda Mu compute module

## General description
The device is a x86 desktop comuter with lots of IO ports like USB, PCIe, Ethernet and more. 

### Block diagram
![block diagram](lucrare%20licenta/images/MiniLatte_block.png)

## Hardware Design
### LattePanda Mu 
The LattePanda Mu is a compute module with rich IO with up to 9 PCIe slots, lots of usb, gpio and much more.
The module is Avaliable with 8 or 16gb of LPDDR5 ram, and an Intel N100 or Intel N305 CPU, the module uses a SODIMM DDR4 slot to connect to the carrier pcb

## ICs 
The board uses a lot of ics, so to avoid a long section about ics you can find the complete list of ICs in an spreadsheet [here]()
!NOT CURRENTLY CREATED

Some of the chips are not available on components sourcing sites like DigiKey or LCSC but can be easliy found of Aliexpress.
Some notable Ics used by the board:

### VL822-Q7
USB 3.2 Gen 2 USB Hub 10Gbps with 4 downstream ports, used to increase the number of usb from 2 to 8

### GL3224ONY
USB 3.2 Gen 1 to dual Sd card controller, used to have 2 sd cards slots on the pcb

### IT8851FN-128
Usb Type C DP alt mode Controller, used for having a usb C port with Displayport output, the chip is a bit hard to get but you can find it on Aliexpress if you ask some BOM sellers. The chip also needs to be flashed so ask the Lattepanda team for the flashing firmware.

### TPS51275

Main Power Ic, used for DC-DC from 20v to 3.3v and 5v

### VL162
USB Type-C 2:4 differential channels mux switch and integrated CC logic function for USB 3.1 type-C application. Needed for the type C ports to work both ways.

### RTL8125BG
PCIe to 2.5Gbps Ethernet controller

## Schematic
[Schematic](PCB/MiniLatte.pdf)

## Bill of Materials
As previosly said, the list is long so you can find it [here]()
!NOT CURRENTLY CREATED
## PCB


## LED Array

The board connects to a secoundary board that an WS2812C LED Array made out of 220 leds (5x44). The Controller for the LEDs is on the main pcb and it is a ESP32 C3


## Case and 3d design

The case was make using AutoCad and exported to stl
The stl files can be found in the 3D Models folder.
The case is made of 2 parts and there is a diffusion layer for the LED PCB
