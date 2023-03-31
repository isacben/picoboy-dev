# picoboy

Development repository of a handheld console for PICO-8 games that runs with a Raspberry Pi Zero.

This project is ongoing. An MVP is not available yet.

The picoboy will be available here: https://github.com/isacben/picoboy

## TODO list

### Pre-study

- [x] Define requirements (actually, limitations) for an MVP on a PCB
- [x] Prototype of a game pad using a breadboard.
- [x] Look for a power supply board and a battery.
- [x] Look for an audio amplifier board and a speaker.
- [x] Learn about displays.
- [ ] ~~Look for a perf board and buttons for the game pad.~~
- [ ] ~~Design an enclosure?~~

### General

- [ ] Test Raspberry Pi GPIOs voltage: should be 3.3V.
- [ ] Test PICO-8 on the Raspberry Pi.
- [ ] Test PICO-8 on the RG35XX.
- [ ] Prototype a display using an Adafruit TFT display.
- [x] Learn about Eagle CAD

### For the MVP

- [x] Order a Game Boy Pocket shell.
- [ ] Look for a display that fits on a Game Boy Pocket shell.
- [ ] Design a PCB based on the Gaboze Pocail (see [Similar projects](#similar-projects))
- [ ] List MVP components
- [ ] Order display
- [ ] Order RPi Zero W and charger
- [ ] Order audio amp plus components (~~speaker~~, headphones jack, volume wheel, capacitors & resistors)
- [ ] Order PCB

## Requirements and limitations for PCB version (MVP)

- PCB that fits in a Gam Boy Color or Pocket shell
- Holes for RPi headers
- Power the device by powering directly the RPi (no battery)
- Connect a display to the PCB
- Display connector on the PCB?
- Buttons directly on the PCB (Retrogram from Adafruit will be needed)
- Amplifier on the PCB with through holes components or the Adafruit PAM8302
- Volume wheel and headphone jack
- 8 ohms speaker
- Power switch?
- USB (mini?) connector to plug the chord on the PCB and a connection to the RPi
- Game Boy Pocket shell with no modifications (hopefully)

## MVP Bill Of Materials (BOM)

| Part | Product | Estimated Price |
| --- | --- | --- |
| Raspberry Pi Zero 2 W | [Adafruit](https://www.adafruit.com/product/5291) | $15.00 |
| Raspberry Pi charger | [Adafruit](https://www.adafruit.com/product/1995) | $8.25 |
| Display | ? | $0.00 |
| RPi headers | ? | $0.00 |
| Audio amplifier | [Adafruit PAM8302](https://www.adafruit.com/product/2130) | $3.95 |
| Volume wheel | ? | $0.00 |
| Headphone jack | ? | $0.00 |
| 100uf capacitor (headphones) | ? | $0.00 |
| 100K ohms resistor (headphones) | [Temp link](https://www.digikey.ca/en/products/detail/mallory-sonalert-products-inc/PSR-20F08S-JQ/2071438) | $0.00 |
| 8 ohms speaker | [Handheld Legend](https://handheldlegend.com/products/game-boy-color-pocket-clear-speaker-funnyplaying?_pos=1&_sid=534442f70&_ss=r) | $3.99 |
| Game Boy Pocket Shell | [Handheld Legend](https://handheldlegend.com/products/game-boy-pocket-replacement-shell-housing?_pos=1&_sid=d40894297&_ss=r) | $7.99
| Game Boy Pocket Silicone Membranes | [Handheld Legend](https://handheldlegend.com/products/game-boy-pocket-silicone-button-pads?_pos=1&_sid=6641bb0e7&_ss=r) | $2.79 |

## MVP specifics

### Audio Amplifier

The amplifier can consist of a circuit similar to the one present on the Gaboze-Pocaio, using the LM4875M/NOPB. The circuit is basically the example documented in the data sheet.

The LM4875M/NOPB provides a way to disconnect the speaker when headphones are detected.

The circuit itself includes the following components:

| Component | Description | Reference part | Value |
| --- | --- | --- | --- |
| R17 | Potentiometer | | ? | 27 kOmhs |
| R18 | Resistor | ERJ-PA3J151V | 150 Ohms |
| R19 | Resistor | ERJ-PA3J104V | 100 kOhms |
| C7 | Capacitor | CL10C221JB8NNNC | 220pF |
| C8 | Capacitor | CL10A105KP8NNC | 1uF |
| C9 | Capacitor | CL10A105KP8NNC | 1uF |
| C10 | Capacitor | 6TPH100MAEA | 100uF |
| J1 | Audio Jack | SJ1-3525NG-GR | - |
| J2 | Speaker | SKU PRT-09914 | - |

### Headphones jack

*TODO*

### Speaker

*TODO*

### Volume wheel

*TODO*

### Display

Possible displays, based on the Game Boy Pocket shell window size:

- Maybe the best option, although I would need to modify the GBP shell and the display would not cover the entire window (in the Game Boy Color, the display does cover the shell's window): https://www.adafruit.com/product/1774
- https://www.digikey.com/en/products/detail/displaytech/DT024CTFT/6650296
- https://www.digikey.com/en/products/detail/newhaven-display-intl/NHD-2-4-240320CF-CSXV-F/6193108
- https://www.digikey.com/en/products/detail/displaytech/DT024DTFT/6650298
- https://www.digikey.com/en/products/detail/focus-lcds/E22RA-FW280-N/12182136
- https://www.digikey.com/en/products/detail/focus-lcds/E22RB-FW1180-N/12182167
- https://www.digikey.com/en/products/detail/focus-lcds/E24GA-I-CW1000-N/16602032
- https://www.digikey.com/en/products/detail/dlc-display-co-ltd/DLC0240AAM06CB-2/13624834
- Only option? https://4dsystems.com.au/mwdownloads/download/link/id/777/

Game Boy measurements: 

https://www.nintendo.co.uk/Support/Game-Boy-Pocket-Color/Product-information/Technical-data/Technical-data-619585.html

### Game Boy pocket shell

Screen area measurements:

| Area | Width | Height |
| --- | --- | --- |
| Display area (with screen protection frame)| 4.9cm (49mm) | 4.4cm (44mm) |
| Screen holder | 5.9cm (59mm) | 5.9cm (59mm) |


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

Interesting way to connect the RPi to a PCB: pogo pins

https://www.adafruit.com/product/5382

## Buttons

### Buttons location on the PCB

Grid is configured to 0.5mm (Alt 0.125mm)

| Button | X | Y | Angle |
| --- | --- | --- | --- |
| UP | 12.2 | 44.4 | 270 |
| DOWN | 12.2 | 29.4 | 90 |
| LEFT | 4.7 | 36.9 | 0 |
| RIGHT | 19.7 | 36.9 | 180 |
| A | 62.47 | 38.7 | 180 |
| B | 48.42 | 34.21 | 180 |
| START | 40.655 | 16.01 | 0 |
| SELECT | 29.055 | 16.01 | 0 |

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
switch: https://www.adafruit.com/product/805

Interesting videos:

- Power for your electronic projects (does not talk about battery charging): https://www.youtube.com/watch?v=IT19dg73nKU
- DIY LiPo Charge/Protect/5V Boost Circuit: https://www.youtube.com/watch?v=Fj0XuYiE7HU
- How to design a battery charger circuit: https://www.youtube.com/watch?v=XBKOkvwgwNw

## Audio

The easiest option is to use the Adafruit PAM8302:

https://www.adafruit.com/product/2130

This is the wiring tutorial:

https://learn.adafruit.com/pocket-pigrrl/pam8302

Another option is to make a circuit using the LM4875M/NOPB:

https://www.digikey.com/en/products/detail/texas-instruments/LM4875M-NOPB/1871687

This looks pretty simple, and it is implemented in the Gaboze-Pocaio as well!

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
- A PCB like the one I am imagining: https://www.youtube.com/watch?v=pEI89ICLwIE and the GitHub repo: https://github.com/Gaboze-Pocaio/Round-2 and https://github.com/32teeth?tab=repositories
- Retro-esp32: https://github.com/retro-esp32/RetroESP32-Hardware
- SAMEBOY (pretty cool project, but no open sourced): https://www.youtube.com/watch?v=S-_VMUlxPx4 and https://www.youtube.com/watch?v=WAgPQLskKko.
- SAMEBOY idea for the display: https://youtu.be/CCwOafAE-Js?t=698
- CircuitPython Deshipu projects: https://hackaday.io/project/186921-game-22
- PiOCKET Tiny: https://hackaday.io/project/21553-pi0cket-tiny and https://www.youtube.com/watch?v=xnwMN_q6XjE

## Other resources

- Getting started with Eagle Part 1 (Autodesk) - https://www.youtube.com/watch?v=j79RRCUsD2c
- Getting started with Eagle Part 2 (Autodesk) - https://www.youtube.com/watch?v=rboxHQR4OCQ
- Inspecting parts in Eagle (Adafruit): https://www.youtube.com/watch?v=VfyzJXDpCm8
- Eagle cross-reference LABELS: https://electronics.stackexchange.com/questions/334798/what-do-decimal-alphanumeric-suffixes-after-a-slash-mean-in-a-schematic-cross-re
- Copy the PCB outline: https://community.element14.com/products/eagle/f/forum/8069/eagle---how-to-copy-between-board-files
- Circle board with flat sides: https://www.youtube.com/watch?v=-vxEbdl68Ro
- Game Boy shells scans: https://www.reddit.com/r/Gameboy/comments/sn3k7u/attention_gameboy_modders_and_tinkerers/
- Game Color digital camera patent: https://patents.google.com/patent/US7972216B2/en?q=(gameboy+color)&oq=gameboy+color
- Electronic Product Development MASTERCLASS: https://www.youtube.com/watch?v=LxtdV_6XW6A

