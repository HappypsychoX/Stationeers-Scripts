# Control Room - Power and Weather

## Overview
A multifunction script to be used in a control room. Handles the following tasks:
* Monitors battery charge and runs backup generator as needed
* Outputs battery charge through data channels
* Monitors the weather station
* Outputs weather data through data channels
* Ouputs Alarms through data channels

### Used data channels:

* Channel 0: Alarm Codes (see [Alarm System](#Alarm-System))
* Channel 1: Weather Station - TimeToNextWeatherEvent
* Channel 2: Battery Array -  Charge (Average)

### TODO:

- [x] Alarm system
- [ ] power data output to monitors
  - [x] PowerPotential
  - [x] PowerActual
  - [x] Charge (graph)
  - [ ] Time Remaining
  
<a name="Alarm-System" />

## Alarm System 

The alarm system outputs alarm codes on the data network through the Memory unit . The alarm code consists of a whole number, representing the alarm color, and a fractional number, representing the alarm sound. Take for example code 4.23, the whole number (4) represents a color of Red. The number after the decimal (23), represents the sound file for Low Power. These values can be written to lights and speaker for audio/visual indicators of monitored conditions.

*Note: The Alarm System has been adapted from a system used by CowsAreEvil.*

### Alarm Sound Codes: 

* StormIncoming 18
* Low Power: 23
  
### Alarm Color Codes:

* Red: 4
* Yellow: 5
* Green: 2
* Blue: 0
* Orange: 3

### Decipher Alarm codes

    l r0 'Alarm Code' # ex:4.23
    Trunc r1 r0 # gives color code
    sub r0 r0 r1 # gives sound code

## Setup

* 1 or more Large Station Batteries 
* Weather Station
* Solid Fuel Generator
* Logic Memory

