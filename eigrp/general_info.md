# EIGRP Info

- EIGRP is know as an advanced distance vector protocol.
- Used to share routes with other routers in the same Autonomous System

## Communications
- Sends updates and hellos to multicast address 224.0.0.10
- Default hello interface is 5 seconds
- The hold or dead timer is usually 3 times the hello interval, default 15
- The hold and hello intervals do not need to match to form a neighborship. The hold interval is sent in the hello packet.  This is displayed in the 
`show ip eigrp neighbors` output.

## Routing
- The administrative distance is 90 for Internal EIGRP and 170 for External
  EIGRP.
 

## Adjacencies
 
## Updates
- Unlike other distance vector protocols EIGRP only sends incremental updates 
