# Simon-game-Raspberry-Pico
Simon game on Raspberry pi Pico

# How to play Simon game

The classic Simon game is a circular object that has four colored quadrants. Each quadrant has a colored surface, which is a switch that also illuminates.

![Simon game image](/img/simon.jpg)

The quadrant colors are green, red, yellow, and blue.
You start by pressing a button, after which one of the quadrants flashes its light. It also plays a tone, with a unique sound for every quadrant.
The object of the game is to remember which light flashed, and then repeat it. 
If you succeed, then the game starts again, this time flashing the first light as well as a second one. Again, the object is to repeat the sequence.
As long as you successfully repeat the sequence, the game continues, flashing more lights and having you repeat them. It also gets faster as you get to higher levels.
If you fail, however, you are greeted with a disapproving tone, and you need to start again from scratch.

# Building Simon

We will construct our version of Simon using LEDs, and some pushbuttons. The “brains” of our game is the Raspberry Pi Pico microcontroller, a 4-dollar technical wonder.  And we’ll be programming it using C and state machine instead of the traditional Python.

# Parts Required

Here is what you’ll need to construct a Simon game:

- A Raspberry Pi Pico microcontroller. You’ll also want to solder the pins onto the microcontroller, so you’ll need 2 20-pin male Dupont terminals.
- Four colored LEDs. I suggest you emulate the original Simon by using a Green, Red, Yellow, and Blue LED.
- Four Dropping resistors. Any value from 100 to 220 ohms will work, I used four 120-ohm resistors in my game.
- Four Pushbutton switches. These need to be momentary contact, normally open switches. If you can get ones with colored tops to match your LEDs, that would be great, otherwise, any color will suffice.

![Simon game image](/img/simonpico.jpg)

# Build the pico firmware

This project has a github actions workflow that build the Pico firmware. 

Othewise the project can be build with the following commmand, the `cmake` may take a couple of minutes.

```
mkdir build 
cd build
cmake ..
make -j6
```

# flash the RaspberryPi Pico

Drag and drop the src/simon.uf2 on the Pico in bootsel mode, or use the following command:

```
cp src/simon.uf2 /media/<user>/RPI-RP2/
