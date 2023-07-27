# Remote Switch Board

This hardware project aims to provide a small form factor board for smart home projects.

The primary goal is to have a platform for remotely switching a garden watering system. The board can be partially populated if fewer switching outputs or other features are not required.

The board was made with KiCad 6.0.

## Main Features

* 8 solid state switches with current measurement
* SX1231 RF chip (compatible to RFM69, 433 / 868 / 915 MHz ISM frequency bands)
* STM32L0 microcontroller (optional)
* Raspberry PI header (optional)
* Frequency counter input
* Thermistor input
* Operating voltage: 12 V DC

## Microcontroller

The board has the option to either use an STM32L0 microcontroller or a Raspberry Pi to control the RF module and the switches. The microcontroller uses SPI to:
* control the switches via a shift register
* read the current feedback from a MCP3008
* communicate with the SX1231 RF chip

Further digital/analog inputs are used for:
* Thermistor input (analog input)
* Frequency counter (digital input)

Both SPI and digital input is also wired to the Raspberry PI header, such that a Raspberry Pi could be used instead of the microcontroller.

## SX1231
The SX1231 is a RF tranciever capable to be operated at license-free 433 / 868 / 915 MHz frequency bands. Tested range using 868 MHz was more than 500 meter in line-of-sight, sufficient for smart home applications.

## Electrical Characteristics
* Main operating voltage: 12 V
* Includes 5 V output to supply a Raspberry PI
* Total current limit approx. 5 A (might be more, untested)
* Switches: 12 V / 2.5 A each

# Licence
Shield: [![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
