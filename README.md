
# TinyPower dev board

Welcome to the Github page of the TinyPower dev board. This page is dedicated to the development board designed for tinyAVR micro-controllers. TinyPower is an minimalistic development board with micro USB power connector, voltage regulator, decoupling capcitors, and V-USB circuit for software USB. The PCB has all pins of Attiny1604 broken out, include the USB pins. You will find in this repo some resources for TinyPower board, and I will provide information about the TinyPower board itself, including its (relative) impressive feature set and specifications. 

![pcb_front_back](https://i.postimg.cc/XYgpMDkg/full-populated-v1b-small.jpg)

While the majority of the content on this page is intended for individuals who are not yet familiar with tinyAVRs, if you already have experience with AVRs outside Arduino, you may already be familiar with much of it. However, there is also additional information provided about the board, pin layout, features, tips, and more.

To begin, Microchip provides extensive documentation on the attiny1604 microcontroller, offering numerous helpful PDFs that comprehensively explain its features. These resources often include informative code examples written in C for AVRstudio. Another valuable resource is the Atmel START code generator, which not only provides example code but also serves as an excellent starting point for new projects by offering initial code for the desired peripherals you intend to utilize. Utilizing these resources from Microchip and Atmel START can greatly aid in understanding the attiny1604 and facilitate the development process.

- https://www.microchip.com/en-us/product/ATTINY1604#document-table 
- https://start.atmel.com/

It's possible to use the TinyPower board with arduino IDE, you can install a bootloader if you like to program the chip direct from the arduino IDE. 
With megaTinycore you can add support for attiny1604 to Arduino and output HEX file that you can upload with one of the programming options. Or direct from the IDE if you have an bootloader installed. 

- https://github.com/SpenceKonde/megaTinyCore

The megaTinyCore Github has also some interesting information about the tinyAVR series. 

## How to program the TinyPower Board?
We have couple of option to program the TinyPower Board
- Arduino with UPDI sketch : https://github.com/ElTangas/jtag2updi + avrdude
- USB-to-Serial with bootloader(optiboot, etc)
- Microchip ICEII programmer
- pyupdi with USB-to-Serial converter

You only need two wires, GND and the UPDI data wire. 
- You need to connect GND of the programer to one of the GND of the TinyPower board
- And connect updi data pin to PA0 of the TinyPower board. 


### How to program the fuses 
You can use AVRdude or pyupdi to program the fuses. However, most older avrdude GUIs do not have support for avrTiny fuses, so you will need to utilize the command line to program the fuses.

### Reset the fuses with 12v programmer
If you lock yourself out after wrong fuse settings it's possible to reset the tinyavr with 12v and high voltage programmer protocol. 
Here are some link that can help you reset you TinyPower board. 

- TinyHVSP programmer https://github.com/wagiminator/ATtiny84-TinyHVSP
- UPDI HV programmer https://github.com/wagiminator/AVR-Programmer/tree/master/UPDI_HV_Programmer

## V-USB (software USB) circuit information

If V-USB circuit is present but there is no vusb firmware the pc will see that usb is connected but will give an error, that is normal, that is what suppose to happen. Mean that circuit works correct. USB low speed is recognized but PC don't get response back because there is no firmware. Just ignore it when you use tinypower board it for something else when powering thought the USB port.

Waveform of V-USB circuit, D- and D+ <br>
![USB_waveform](https://i.postimg.cc/hvK2gjHZ/usb-sync-signal-from-PC-to-device3-SOF.jpg)

## How to install or remove the TinyPower board from a breadboard?
Push only on the sides of the PDB, and try to avoid excessive presure on the USB port and switch.
![push-pcb-in1](https://i.postimg.cc/4xxDdtCX/push-pcb-in1.jpg)

Same for deinstalling the PCB, try to avoid to pulling on the USB, try to grap the pcb on the sides or use someting to lift the pcb. 
But watchout that you don't break components on the other side with big screwdriver or so. 
![pull-pcb-out1](https://i.postimg.cc/W1YQJ3jg/pull-pcb-out1.jpg)


### Attiny1604 Specs
- 16KB Flash
- 1KB Ram
- 256B EEPROM
- 12 GPIO pins (all 12 usable for I/O, but one has some restrictions)
- Hardware Multiplier
- One 16-bit Timer Type TCA with 3 x 16bit PWM output, or in split mode has 6 x 8bit PWM channels. And much more
- One 16-bit Timer/Counter type TCB, capture mode, waveform gen, etc
- Max 6 PWM outputs (Arduino UNO has only 5)
- One 16-bit RTC (Real-Time Counter), Attiny1604 has an internal 32.768Khz occsilator.
- Improved 10-bit ADC with 10 channels, 115 ksps (Arduino UNO has only 6 channels)
- One USART with a baud rate generator, auto-baud, and start-of-frame detection.
- Multiple voltage references (VREF): 0.55v, 1.1v, 1.5v, 2.5v, 4.3v (changeable at runtime)
- One host/client hardware SPI interface with Buffer Mode
- One Two-Wire Interface, 100Khz, 400Khz, 1Mhz bus speeds
- Hardware Event System with external input and output
- Configurable Custom Logic (CCL) with two programmable look-up tables
- External interrupt on ALL general-purpose pins(falling edge, raising edge, both edges)

## Compare the Attiny1604(tinyAVR) vs Attiny84 (classic attiny)
The Attny84 can be seen as a predecessor to the attiny1604, so lets compare those two. 
[![at1604-vs-at84-2s.jpg](https://i.postimg.cc/BZBHVCdH/at1604-vs-at84-2s.jpg)](https://postimg.cc/yWWDJ068)

## TinyPower Layout R1
![App Screenshot](https://i.postimg.cc/k58bzTJ4/Pin-layout-tinypower-v1-b.jpg)
- The pin discriptions are correct, there is one mistake in the silkscreen, VUSB and VCC are swapped on the left side. 

## Example codes
I will make list of good sites/repos/etc with example code for Attiny1604

- In this repo I have some of my personal example code for Attiny1604: https://github.com/JacobIkke/Attiny1604-examples



