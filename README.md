# LED Extender boards

** Dr Oldies LED Extender small, inexpensive expansion boards support up to 16 leds strips in either simple strips or tiled arrays. **

* LED Extender PCBs can be used independently or, more conventienly, with my LEDMatrix_22/FastLED library. 
* Combining the Extenders with these libraries allows you to design medium to large led strings and arrays of 4096 leds and more.
* Large led panels can be composed of multiple led tiles in numerous arrangements. 
* Versions support both 1-wire and 2-wire leds (see below).
* Using a multiplexing schema large 2-wire arrays use 8 MCU pins or less! Leaving lots of pins for sound and other uses.
* The LEDMatrix_22 library is configured in a well documented header file. 
* 3v3 data lines are converted to 5v while isolating the MCU from led voltages.
* See the Wiki above for complete details

## The Problem
Both 1-wire (data only) and 2-wire (data+clock) led strips longer than a few dozens of leds fall out of sync and begin to "pixilate" or flash randomly. Using voltage steppers can help to some extent. ing can help aEven when injecting additional current to increase brightness of leds, out of sync timing still occurs.
Breaking into shorter led strips running in parallel from the MCU required complicated code, and uses a large number of MCU pins.  
 
## The Solution 
These LED Extenders alow you to break-up the strings into shorter strips running in parallel by multiplexing MCU a minimum of output pins to a lage number of strips. 

1. Teensy 3.5 to 4.1 **shield format** 
    Plug directly in Teensy either above or below
    1 to 4 extenders can be added ("long leg" female headers required)
2. non-shield format
    32 bit MCU recommended for larger LED matricies
    Sufficient memory to accomodate the CRGB LED array
    Requires jumper wires or ribbon cable-not supplied 


### supported LEDs

LEDS (2-wire) using DATA and CLOCK pins (partial list)

    LPD6803 
    LPD8806 
    WS2801
    WS2803
    SM16716
    P9813  
    DOTSTAR  
    APA102  
    SK9822  
LEDS (1-wire) using DATA only pin (partial list)
    TX1813N1
    TX1812
    WS2811
    WS2812
    WS2812B
    WS2815

ANy other dual pin LED supportyed by FastLED