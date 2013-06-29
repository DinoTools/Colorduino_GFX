Colorduino GFX Library for Arduino
==================================

This library depends on a slightly modified version of the Adafruit GFX library and provides advanced drawing functions(lines, circles, text, ...) for the Colorduino or the Colors Shield.

Installation
------------

The Colorduino GFX library depends on slightly modified version of the Adafruit GFX library. Download and install this library first.

Download the source code and rename the uncompressed folder to Colorduino_GFX. The folder should at least contain the files Colorduino_GFX.cpp and Colorduino_GFX.h. Place the folder in your <Arduino-Sketch-Folder>/libraries/ folder and restart the Arduino IDE.

Usage
-----

Before you start set the right values in the Config section of the modified Adafruit GFX library. Use a struct for red, green and blue and 8 bit vars for the coordinates.

<code>
typedef struct {uint8_t r; uint8_t g; uint8_t b;} GFX_Color_t;
typedef int8_t GFX_Coord_t;
</code>

Include all required libraries first.
<code>
#include <Adafruit_GFX.h>
#include <Colorduino_GFX.h>
</code>

Create a new Colorduino instance.

<code>
ColorduinoPanel Colorduino;
</code>

Initialize the Colorduino and set the white-balance in the setup() function.

<code>
void setup() {
  Colorduino.init();
  Colorduino.setWhiteBalance(36, 63, 63);
}
</code>

Now the Colorduino is ready to use.

<code>
void loop() {
    GFX_Color_t color = Colorduino.color(255, 0, 0);
    Colorduino.drawLine(0, 0, 7, 7, color);
    Colorduino.swapBuffers(true);
}
</code>


Licenses
========

Library (LGPL)
--------------

The library is licensed under the LGPL 2.1 or a later version of the license.

The source code is based on C code by zzy@iteadstudio and Sam C. Lin
  Copyright (c) 2010 zzy@IteadStudio.  All right reserved.
  Copyright (c) 2011-2012 Sam C. Lin <lincomatic@hotmail.com>

Examples (LGPL)
---------------

The examples are licensed under the LGPL 2.1 or a later version of the license.

Additional resources
====================

* [Adafruit GFX Library](https://github.com/adafruit/Adafruit-GFX-Library)
* [Modified version of the Adafruit GFX Library, required by this library](https://github.com/dinotools/Adafruit-GFX-Library]
* [Original Colorduino Library](https://github.com/lincomatic/Colorduino)
* [Colorduino GFX Library](https://github.com/DinoTools/Colorduino_GFX)
