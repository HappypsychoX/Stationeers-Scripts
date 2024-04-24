# Control Room - Power and Weather

A multifunction script to be used in a control room. Handles the following tasks:
* Monitors battery charge and runs backup generator as needed
* Outputs battery charge through data channels
* Monitors the weather station
* Outputs weather data through data channels

#### TODO:
* Alarm system
* power data putput to monitors
  * PowerPotential
  * PowerActual
  * Charge (graph)

#### Used data channels:
* Channel 0: Weather Station - Mode (Depricate and use for alarm code)
* Channel 1: Weather Station - TimeToNextWeatherEvent
* Channel 2: Battery Array -  Charge (Average)

#### Alarm Sound Codes 
* StormIncoming 18
* Low Power: 23
  
#### Alarm Color Codes:
* Red: 4
* Yellow: 5

#### Decipher Alarm codes
    l r0 'Alarm Code' # ex:4.23
    Trunc r1 r0 # gives color code
    sub r0 r0 r1 # gives sound code
    

