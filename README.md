
# TinyPower dev board

Welcome to the Github page of TinyPower dev board. This page is dedicated to the development board designed for tinyAVR micro-controllers. You will find some resources, and I will provide detailed information about the TinyPower board itself, including its (relative) impressive feature set and specifications. 

Most parts of this page are for people that don't know AVRs jet, if you are familiar with AVRs most of it you probably already know, but there is also some  info about the board, pin layout, feature, tips, etc.

Let's start with Microchip, Microchip has lots of good documentation, lots of good PDFs that explain lots of features of the chip, include some code example for AVRstudio. 

- https://www.microchip.com/en-us/product/ATTINY1604#document-table 

But you can also use tinyAVR with arduino, you can even install a bootloader if you like to program the chip direct from the arduino IDE. 
With megaTinycore you can add support for attiny1604 to Arduino and output HEX file that you can upload with one of the programming options. Or direct if you have installed an bootloader. 

- https://github.com/SpenceKonde/megaTinyCore

The megaTinyCore Github has also some interesting information about the tinyAVR series. 

## How to program tinyAVR?
We have couple of option to program the TinyPower Board
- USB-to-Serial : 
- Arduino with UPDI sketch : https://github.com/ElTangas/jtag2updi + avrdude
- ARV ICE programmer
- pyupdi with USB-to-Serial


## How to program the fuses
With AVRdude or pyipdi you can program the fuses
This is example command for avrdude: -Ufuse2:w:0x02:m 

## Reset the fuses with 12v programmer
If you lock yourself out after wrong fuse settings it's possible to reset the tinyavr with 12v and high voltage programmer protocol. 
Here are some link that can help you reset you TinyPower board. 

- TinyHVSP programmer https://github.com/wagiminator/ATtiny84-TinyHVSP
- UPDI HV programmer https://github.com/wagiminator/AVR-Programmer/tree/master/UPDI_HV_Programmer


## How to install or deinstall the PCB on breadboard?
Push only on the sides of the PDB, and try to avoid excessive presure on the USB port and switch.
![App Screenshot](https://i.postimg.cc/4xxDdtCX/push-pcb-in1.jpg)

Same for deinstalling the PCB, try to avoid to pulling on the USB, try to grap the pcb on the sides or use someting to lift the pcb. 
But watchout that you don't break components on the other side with big screwdriver or so. 
![App Screenshot](https://i.postimg.cc/W1YQJ3jg/pull-pcb-out1.jpg)


# Attiny1604 Specs
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

## TinyPower Layout R1
![App Screenshot](https://i.postimg.cc/k58bzTJ4/Pin-layout-tinypower-v1-b.jpg)
- The pin discriptions are correct, there is one mistake in the slickscreeen, VUSB and VCC are swapped on left side. 

## Example codes
I will make list of good sites/repos/etc with example code for Attiny1604

- In this repo I have some of my personal example code for Attiny1604: https://github.com/JacobIkke/Attiny1604-examples



