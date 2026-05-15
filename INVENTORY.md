# Electrical System Inventory

## Batteries

### House Bank
- 3x 105Ah 12V FLA batteries
- 300A fuse
- Bus bar (+)
- Bus bar (-)
- On/Off Switch
- Shunt on (-) side (*)
- Shunt on (+) side (**)
- Victron SmartShunt (**)

(*) All (+) loads must pass through (+) shunt. The shunt is between the positive bus bar and the loads.
(**) All (-) loads must pass through (-) shunt and the Victron SmartShunt. The shunts are in series between the negative bus bar and the negative distribution bus bar.


### Starter Bank
- 1x 105Ah 12V AGM battery
- 300A fuse
- Bus bar (+)
- Bus bar (-)
- On/Off Switch

### Parallel switch
- On/Off Switch

## Engine Starter
- Wired to starter battery

## Alternator
- Wired to house bank
- Electromaax regulator

## Starting Battery Charger
- Xantrex Echo charger from house to starter

## Solar
- 2x Victron SmartSolar controller

## Hydrogeneration
- 1x Watt&Sea Cruise 600

## Distribution
- 2x 8-circuit breaker panels
- Negative distribution bus bar

## Load Circuits
- Instruments
- Radar
- Nav Lights
  - Port Light
  - Starboard Light
  - Stern Light
  - Compass Light
- Steaming Light
- Anchor Light
- Autopilot 1
- Autopilot 2
- Cabin Lights
  - Galley Dome Light
  - Forward Dome Light
  - Port Reading Light
  - Startboard Reading Light
  - Port USB
  - Starboard USB
- Bilge Pump
- Ballast Pump
- Engine Room

### Instruments
- Additional 8 position fuse block
  - NKE
    - 12v-12v regulator
    - NKE box 1
  - VHF
  - PC
  - GPS
  - AIS
  - N2K

## Data Busses
- Wifi
  - PC
  - iPhone
  - Tablet
- Bluetooth
  - Victron SmartShunt
  - iPhone
  - Tablet
- Charging Data
  - Electromax Regulator
  - Shunt (+)
  - Shunt (-)
- Charging Data 2
  - Victron SmartShunt
  - Starter Battery
- NMEA0183 bus
  - AIS
  - PC
  - NMEA box
- N2K bus
  - AIS
  - PC
  - GPS Antenna
  - Electromaax regulator
- NKE Topline bus
  - NKE box 1 (port)
    - Multigraphic
    - GyroGraphic
    - Gyropilot
    - Compass
  - NKE box 2 (stbd)
    - Multigraphic
    - GyroGraphic
    - Gyropilot
    - Compass
  - NKE box 3
    - Radio Receiver
    - NMEA box
    - NKE Wind
    - NKE Boat Speed
    - NKE Depth
