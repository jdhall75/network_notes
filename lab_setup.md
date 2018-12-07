# Lab Setup
![Lab logical layout](https://photos.app.goo.gl/WHpgeafJvbQKKPqs6)

- This is how I keep my lab configured for work with OSPF, EIGRP, and RIP

## Hardware
- D1, D2, A1 are all 3560's
- R1 and R2 are Mikrotik 750's.
  - The functionality for the price can't be beat with this things.  
  - They work well for injecting routes into the environment.
- R1-R4 and FR(Frame Relay, you're reading that right) are ISR 2811's
- Various RPi like devices for network endpoints. 

## Omissions 
- A1 is in area 3 to both D1 and D2 
- Area 2 is switched between a stub and nssa for various testing
