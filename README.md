# LED Extender boards

**These LED Extender Teensy shields and non-shields are small, inexpensive expansion boards which support up to 16 leds strips in either simple strips or tiled arrays**

<img src="https://github.com/Paul47/LEDMatrix_22/blob/main/wiki_images/image_7.png" width = "300" align = "RIGHT">

**Schematics, Gerbers, BOM and Pick List files are included**

**See the wiki for detailed descriptions of each board version.**

* LED Extender PCBs can be used independently or, more conveniently, with my LEDMatrix_22/FastLED library (https://github.com/Paul47/LEDMatrix_22). 
* Combining the Extenders with these libraries allows you to design medium to large led strings and arrays of 4096 leds and more.
* Large led panels can be composed of multiple led tiles in numerous arrangements. 
* Versions support both 1-wire and 2-wire leds (see below).
* Using a multiplexing schema large 2-wire arrays use 8 MCU pins or less! Leaving lots of pins for sound and other uses.
* My LEDMatrix_22 library (https://github.com/Paul47/LEDMatrix_22) is configured in a well documented header file. 
* 3v3 data lines are converted to 5v while isolating the MCU from led voltages.
* See the Wiki above for complete details
* All gerber, BOM, and Pick Lists files are included.
* Includes DipTrace schematic and board files. (DipTrace is free to download for smaller PCBs)

## The Problem
Both 1-wire (data only) and 2-wire (data + clock) led strips longer than a few dozens of leds fall out of sync and begin to "pixilate" or flash randomly. Using voltage steppers to ensure full 5v signals and even injecting additional current to sustain brightness of leds can help to some extent. But out of sync timing still occurs.
Breaking led strips into shorter led strips running in parallel from the MCU required complicated code, and uses a large number of MCU pins.  
 
## The Solution 
These LED Extenders allow you to break-up the strings into shorter strips running in parallel by multiplexing MCU a minimum of output pins to a large number of strips. 

1. Teensy 3.5 to 4.1 **shield format** 
    Plug directly in Teensy either above or below
    1 to 4 extenders can be added ("long leg" female headers required)
2. non-shield format
    32 bit MCU recommended for larger LED matrices
    Sufficient memory to accommodate the CRGB LED array
    Requires jumper wires or ribbon cable-not supplied 


### supported led strips (as strips or matrix/array panels)

LEDS (2-wire) using DATA and CLOCK pins (partial list)
```c
    LPD6803 
    LPD8806 
    WS2801
    WS2803
    SM16716
    P9813  
    DOTSTAR  
    APA102  
    SK9822
```
LEDS (1-wire) using DATA only pin (partial list)
```c
    TX1813N1
    TX1812
    WS2811
    WS2812
    WS2812B
    WS2815
```
Any other 1-wire or 2-wire leds supported by FastLED
