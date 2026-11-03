Florida Polytechnic University RoboBoat main board development tracking. 

<img width="6000" height="6000" alt="logoTP" src="https://github.com/user-attachments/assets/03fd0c31-e668-4284-8ae5-73d3e616ccd2" />

This board contains circuitry for power delivery, ESC commanding, and LoRa interfacing for a robust electrical system.

**Power Delivery:**

12V, 15V, 5V rails. Powers everything on the boat (LiDar, Jetson Nano, etc).

**Remote & On-board E-stop:**

LoRa module & the Big Red Button (BRB) plugs into the board via JST-XH connector, interfaces with Pi Pico. Pi Pico controls the optocoupler LED. 

The Pico will run a simple if statement, only when the BRB isn't pressed & the LoRa module isn't sending an open command will the Pico turn on the optocoupler LED, closing the contactor. In this configuration, the Pico is holding the contactor closed, meaning if power is lost for any reason the contactor defaults to being open.

The board will also include a "READY" LED and a "INDICATOR" LED, the former only being on when the contactor is closed and the latter providing status updates.

**Thruster Control**

The Pico will also interface and command the thruster ESC via a JST-XH connector. Commands to the Pico will be gathered over serial via the RX pin from either the FlySky transmitter or the Jetson Nano.
