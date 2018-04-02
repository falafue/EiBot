# EiBot
Remix of https://wiki.section77.de/projekte/eggbot77-2018-eh-edition

Suggested Inkscape extension for eggbot: https://github.com/section77/eggbot_extension

Firmware tested: https://github.com/russhughes/EggDuino

Original firmware and inskcape extension: https://github.com/evil-mad/EggBot

## Components

 * Aluminium rod 8mm diameter, 120mm long
 * Spring 11mm diameter, 54mm long
 * Arm axis: Steel wire 1mm. 50mm long.

## ULN2003 assembly for unmodified EggDuino firmware

Studying https://github.com/russhughes/EggDuino/blob/master/EggDuino.ino
we find the electical connections.

I have two boards

* Arduino Pro Micro with ATMEGA 32U4
* Arduino Nano with ATMEGA328P and CH340G

The boards have enough GND pins, two on the Nano, three on the Pro Micro. 
I need three, one for each ULN-Board and one for the servo.
Both boards only have one 5V (VCC) pin, I also need three.

I choose the Nano, because it has pinheaders already soldered, 
so that I can use only dupont cables without much soldering to connect 
the ULN-boards. 

The +5V and GND connections needs some soldering, as we do not have enough 
pins on the board. The easiest is a 2x8 pinheader, each row of 8 soldered 
together, with a thin piece of wire. One row serves ase a GND distributor, the 
other row as a VCC distributor. 
The only other soldering is two dupong cables to the power connector.
The distribution rails have 3 unused connetors each, sufficient for 
adding the buttons.

### Pin assignment
                     
<pre>
Arduino         ULN2003 rotation motor

 * D2 ----------- IN1
 * D4 ----------- IN2
 * D3 ----------- IN3
 * D5 ----------- IN4
 * GND ------+--- (-)                      Servo cable
             +---------------------------- (*) brown  GND
 * VIN ---+------ (+)
          |
          +------------------------------- (*) red    VCC 
          |
          |     ULN2003 pen motor         
          +------ (+) 
 * GND ---------- (-)
 * D6 ----------- IN1
 * D8 ----------- IN2
 * D7 ----------- IN3
 * D9 ----------- IN4
 * D10 ----------------------------------- (*) orange PWM
 
</pre>

TODO: Buttons?

<img height=200 src="https://github.com/falafue/EiBot/raw/master/photos/20180402_154731.jpg"/>&nbsp;<img height=200 src="https://github.com/falafue/EiBot/raw/master/photos/20180402_160306.jpg"/></br>
<img src="https://github.com/falafue/EiBot/raw/master/photos/20180402_161511.jpg"/></br>
