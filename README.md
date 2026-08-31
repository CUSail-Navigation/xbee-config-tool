Years of experience has taught us that the 900MHz Xbee support with XCTU is inconsistent, to say the least. The specific issue has to do with the Xbee Explorer modules, and is both unsolved and well-documented online. 

Instead of solving it directly (...we tried), this is a microcontroller-based tool for configuring 900MHz Xbees, which bypasses the Explorer module entirely. 

I used parts we already have, so the design is a bit bulkier than it needs to be (versus using less parts but having to buy them). Here is a parts list:

1. Raspberry Pi Pico
2. Raspberry Pi Zero 2 W
3. 7-inch Touchscreen Display I found in a random box

The Pico actually writes to the Xbees, the Zero 2 W is for interfacing with the display, and the display is to make a usable interface.
