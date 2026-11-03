# FPU RoboBoat Main Board

<img width="4341" height="2704" alt="logoTP" src="https://github.com/user-attachments/assets/ef87d0be-14d3-485b-b96a-e713eab52e08" />

This board contains circuitry for power delivery, ESC commanding, and LoRa interfacing for a robust electrical system.

## Features:

**Power Delivery:**

12V, 15V, 5V rails. Powers everything on the boat (LiDar, Jetson Nano, etc).

**Remote & On-board E-stop:**

LoRa module & the Big Red Button (BRB) plugs into the board via JST-XH connector, interfaces with Pi Pico. Pi Pico controls the optocoupler LED. 

The Pico will run a simple if statement, only when the BRB isn't pressed & the LoRa module isn't sending an open command will the Pico turn on the optocoupler LED, closing the contactor. In this configuration, the Pico is holding the contactor closed, meaning if power is lost for any reason the contactor defaults to being open.

The board will also include a "READY" LED and a "INDICATOR" LED, the former only being on when the contactor is closed and the latter providing status updates.

**Thruster Control**

The Pico will also interface and command the thruster ESC via a JST-XH connector. Commands to the Pico will be gathered over serial via the RX pin from either the FlySky transmitter or the Jetson Nano.

## Contributors

- [David Zambrano] - [@TheDogIsHungry](https://github.com/TheDogIsHungry)
- [Nerlin Charles] - [@NCharles101](https://github.com/NCharles101)
- [Gabriel Morgan] - [@GMorgan2776](https://github.com/GMorgan2776)
- [Ivan Domi]      - [@idomi17](https://github.com/idomi17)
