μC Mousejack
-------------

This is a version of https://github.com/insecurityofthings/uC_mousejack/ with a few changes to run on a arduino pro micro board instead.

It is also optomized to send up to 6 characters per Logitech message instead of the default 1. This increases attack speed as well as reduces the chances for lost messages.

 Building
 --------

 To build the software, download and install the [PlatformIO IDE](http://platformio.org/platformio-ide). It sucks much less than the Arduino IDE.

 Before building the software, be sure to modify the `attack.h` file using the `attack_generator.py` script:

 ```
 uC-mousejack $ cd tools
 tools $ ./attack_generator.py ducky.txt
 ```

 In the example above, the ducky.txt file contains our [Duckyscript](https://github.com/hak5darren/USB-Rubber-Ducky/wiki/Duckyscript). The `attack_generator.py` script will "compile" the ducky script into the `attack.h` file, which is included in `main.cpp`. This simplifies the code and makes it more compact.

 Using
 -----

 Once you power the device on, the internal LED connected to pin 13 (called ledpin in the code), will blink two times for each pass over the entire channel range. When it sends an attack, the LED will glow solid.

 If you monitor the serial port using the PlatformIO IDE, you will see a lot of debugging information being printed while scanning and during attack.

 Warning: No interaction is required to initiate an attack. Be careful where you use this device. We do not accept any responsibility for how this tool is used.
