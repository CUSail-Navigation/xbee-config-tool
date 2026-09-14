Years of experience has taught us that the 900MHz Xbee support with XCTU is inconsistent. The specific issue has to do with the Xbee Explorer modules - it is both unsolved and well-documented online. My best guess is that the modules mess with the firmware on the Xbees under some very specific (and unknown) condition. Xbee modules themselves are great for our use case and very flexible, it's just XCTU and the explorer module that are behaving poorly.

Instead of solving it directly (...we tried), this is a microcontroller-based tool for configuring 900MHz Xbees, which bypasses the Explorer module entirely. To be clear, this is designed to work with the **Digi XBee-PRO 900HP RF Module** specifically, the ones without the black chip (microcontroller) on them. 

Here is a parts list:

1. Raspberry Pi Zero 2 W + 16GB Micro-SD card already on it
2. 7-inch Touchscreen Display I found in a random box
3. Box I 3D printed
4. Custom PCB for housing everything + interfacing with Xbees

The Zero 2 W has GPIO so it can read/write to the Xbee. I use it over a Pico because the random display I found only has HDMI, I'd rather use it than spend like $40 on a Pico-compatible display. The box is my first time using 3D modeling software so that's why it's kind of bad. 

I thought of using a battery, but opted instead to have a wall-plug so we don't need to deal with charging. **Make sure to use a 5V wall plug, ideally >3A.** I'm not putting overvoltage protection because I'm lazy and this is not that serious of a project; less than 5V won't properly power the system, greater than 5V will fry everything (except possibly the Xbees). Currents below 3A might be fine but I won't test it, so call it undefined behavior. 

INTENDED (CRITICAL) FUNCTIONALITY:
1. Ability to configure all Xbee functions, identically to how it's done on XCTU.
2. A 'quick-pair' button for pairing 2 Xbees (if you want to pair more than 2, just do it manually)
3. The ability to reset the firmware on an Xbee to a factory state

FEATURES I MIGHT ADD OR MIGHT NOT IDK:
1. Keyboard+mouse support through USB (should be very easy but idk)
2. Status LEDs throughout
3. (As mentioned before) overvoltage/overcurrent protection
4. Ability to save profiles locally (also should be easy)
