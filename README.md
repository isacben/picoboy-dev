# picoboy
A handheld console for PICO-8 games. Runs with a Raspberry Pi.

This project is ongoing. An MVP is not available yet.

## TODO list
- [x] Prototype of a game pad using a breadboard.
- [ ] Prototype a display using an Adafruit TFT display.
- [ ] Test PICO-8 on the Raspberry Pi.
- [x] Look for a power supply board and a battery.
- [ ] Look for an audio amplifier board and a speaker.
- [ ] Look for a perf board and buttons for the game pad.
- [x] Look for a display.
- [ ] Design a PCB for the game pad?
- [ ] Design an enclosure?

## RetroPi

To configure wifi see the following links:

- https://funconsumertech.com/retropie-wi-fi-setup-an-illustrated-step-by-step-guide/
- https://retropie.org.uk/docs/Wifi/

Configure SSH:

https://retropie.org.uk/docs/SSH/

1. Boot to RetroPie
2. Enter shell by pressing Ctrl + F4
3. cd /boot
4. sudo touch ssh
5. sudo reboot now

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

Another option is to use something like the Adafruit PiTFT Plus 320x240 2.8" TFT + Capacitive Touchscreen. The HAT uses the high speed SPI interface on the Pi. This will require a tool called fbcp (framebuffer copy). See Pocket PiGRRL:

https://www.adafruit.com/product/2423

The Adafruit PiTFT 2.2" HAT Mini Kit - 320x240 2.2" TFT - No Touch could also be a good option:

https://www.adafruit.com/product/2315

## Power

> For the MVP, I might not install a power booster nor a battery!

For the MVP, this wall power supply can be enough:

https://www.adafruit.com/product/1995

Since the battery will provide 3.7V only, we will need a circuit that can boost the battery voltage up to 5V and 1A (for a Raspberry Pi Zero, at least).

We also need to charge (constant current and constant voltage) and a protection circuit (over discharge and short circuit).

Thi video shows how to use the following components:

https://www.youtube.com/watch?v=VczNDDkFiAI

tp4056 
MT3608
3.7V lithium battery
switch

Interesting videos:

- Power for your electronic projects (does not talk about battery charging): https://www.youtube.com/watch?v=IT19dg73nKU
- DIY LiPo Charge/Protect/5V Boost Circuit: https://www.youtube.com/watch?v=Fj0XuYiE7HU

## Enclosure

- Wooden box: https://www.youtube.com/watch?v=iPKIugXvlM4

## Similar projects

- PICO-8 handheld: https://www.youtube.com/watch?v=R3GZflUXv0g
- Pocket PiGRRL: https://learn.adafruit.com/pocket-pigrrl/overview
- PiGRRL Zero: https://learn.adafruit.com/pigrrl-zero/overview
- Game Boy Zero: https://www.youtube.com/watch?v=XzYMWNiUN_M&t=229s
- Easier Game Boy Zero with parts and diagrams: https://www.youtube.com/watch?v=KfKn2JdnxF0
- TurtlePi: https://www.youtube.com/watch?v=BnAuwz3R98o
- Just a controller: https://www.youtube.com/watch?v=1k49VVNHvtU
- No battery: https://www.youtube.com/watch?v=IP3QVGmd_90 and https://www.youtube.com/watch?v=VYeIR5n5Few
- A PCB like the one I am imagining: https://www.youtube.com/watch?v=pEI89ICLwIE and the GitHub repo: https://github.com/Gaboze-Pocaio/Round-2