# picoboy
A handheld console for PICO-8 games. Runs with a Raspberry Pi.

This project is ongoing. An MVP is not available yet.

## TODO list
- [x] Prototype of a game pad using a breadboard.
- [ ] Prototype a display using an Adafruit TFT display.
- [ ] Test PICO-8 on the Raspberry Pi.
- [ ] Look for a power supply board and a battery.
- [ ] Look for an audio amplifier board and a speaker.
- [ ] Look for a perf board and buttons for the game pad.
- [x] Look for a display.
- [ ] Design a PCB for the game pad?
- [ ] Design an enclosure?

## Buttons

### Raspberry Pi connection

To create a virtual keyboard using the GPIOs of the Raspberry Pi, I am using Adafruit's Retrogame software:

https://github.com/adafruit/Adafruit-Retrogame

Note this repository is in maintenance mode.

This is a tutorial on how to install Retrogame:

https://learn.adafruit.com/retro-gaming-with-raspberry-pi/adding-controls-software

## Display

A good idea might be to use a capacitive touch screen, such as the Waveshare 3.5inch DPI LCD:

- [See on Amazon](https://www.amazon.com/Waveshare-3-5inch-Capacitive-LCD-DPI/dp/B08TBF5PHH/ref=sr_1_1?crid=NSXCFL0ML9MO&keywords=3.5inch+DPI+LCD&qid=1679185510&s=electronics&sprefix=3.5inch+dpi+lcd%2Celectronics%2C309&sr=1-1)
- [See on waveshare](https://www.waveshare.com/3.5inch-DPI-LCD.htm)

DPI displays seem to be more appropriate, since this type of displays have a faster refreshing rate (compared to the SPI displays). Also, the capacitive screen would be useful to use PICO-8 Splore to look for games.

There is selection table at the bottom of this link:

https://www.waveshare.com/product/3.5inch-RPi-LCD-B.htm

This display connects on top of the Raspberry Pi as a hat, which make the handheld device too thick:

![Display on top of the Raspberry Pi](images/3.5inch-dpi-lcd-5.jpg?raw=true "3.5 inch DPI LCD")

This is a tutorial on how to connect and configure a display similar to the one mentioned above:

https://www.youtube.com/watch?v=vCAGzLGTUk4&t=11s

There is also a 4 inch square display, which would be perfect for PICO-8, but it might be too big. It is also more expensive:

https://www.waveshare.com/4inch-DPI-LCD-C.htm