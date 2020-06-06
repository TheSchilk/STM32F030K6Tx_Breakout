# STM32F030K6Tx Breakout

A very simple breakout board for the STM32F030K6Tx MCU. 

Philipp Schilk 2020

https://github.com/TheSchilk/STM32F030K6Tx_Breakout

![Board](https://raw.githubusercontent.com/TheSchilk/STM32F030K6Tx_Breakout/master/Doc/Board.jpg)

![3D Render](https://raw.githubusercontent.com/TheSchilk/STM32F030K6Tx_Breakout/master/Doc/Render.jpg)

## Overview

Besides SWD, 2 LEDs, space for a crystal and other supporting circuitry,
there are bells and whistles.

I did however aim to expose as much functionality of the STM as possible:
The crystal is optional and the IO can be exposed with two jumpers if needed.
Also the VDDA Supply can be separated from VDD if a separate supply is wanted.

In fact, with the right jumper configuration this board can serve as a direct
LQFP32 breakout board with all pins exposed and not set connections.

Because I hate nothing more than digging through PDFs to find out what
pins the LEDs where connected to again, I included as much information
as possible in the silkscreen. 

## Features on Board:

**ARM SWD**:  
Connector footprint can accept both an SMD and a TH programming header. 

**2 LEDs**:
Connected to pins PB0 and PB1


## Compatibility 

According to CubeMX this breakout should also be compatible with:
 - STM32F031K6Tx
 - STM32F051K4Tx
 - STM32F051K6Tx
 - STM32F051K8Tx
 - STM32F042K4Tx
 - STM32F042K6Tx

But that is untested. Please double check the pinout. 

## Jumper Configuration

Here is what the Jumpers do:

JP1: Connects BOOT0 to either GND (indicated by a small arrow) or VDD, both through R1.
JP2: Connects pin F0 of the STM to the breakout header. Should only be set when not
     using a crystal.
JP3: Connects pin F1 of the STM to the breakout header. Should only be set when not
     using a crystal.
JP4: Connects pin 1 of MCU (VDD) to shared VDD  
JP5: Connects pin 16 of MCU (GND) to shared GND  
JP6: Connects pin 17 of MCU (VDD) to shared VDD  
JP7: Connects pin 32 of MCU (GND) to shared GND   
JP8: Connects pin 5 of MCU (VDD) to shared VDD  


Which means, to use this as a STM breakout:
Set the following jumpers: JP4  JP5  JP6  JP7  JP8  

If you want a straight LQFP Breakout:
Set the following jumpers: JP2 JP3 
Populate R1 with a 0R resistor.
Populate U1 and nothing else

## Pinouts

With an STM32F030K6Tx the pinout is as follows:

| *Pin* | *Function* | *Pin* | *Function* |
|-|-|-|-|
| 1 | Vdd  | 32 |  GND |
| 2 | F0(1) | 31 | BOOT0 |
| 3 | F1(1) | 30 | PB7 |
| 4 | nRST  | 29 | PB6 |
| 5 | VDDA  | 28 | PB5 |
| 6 | PA0  | 27 | PB4 |
| 7 | PA1  | 26 | PB3 |
| 8 | PA2  | 25 | PA15 |
| 9 | PA3  | 24 | PA14 |
| 10 | PA4 | 23 | PA13(3) |
| 11 | PA5 | 22 | PA12(3) |
| 12 | PA6 | 21 | PA11 |
| 13 | PA7 | 20 | PA10 |
| 14 | PB0(2) | 19 | PA9 |
| 15 | PB1(2) | 18 | PA8 |
| 16 | GND | 17 | GND |

(1): Crystal
(2): LEDs
(3); SWD
