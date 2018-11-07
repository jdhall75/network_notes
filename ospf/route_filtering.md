The rules for filtering in OSPF is kind of confusing at first. It can only be done at certain locations in the network for certain types of LSA's.

## Filter list
	- Done at the ABR 
	- Only able to filter inter-area type 3 LSA's 
	- Uses a prefix-list to identify the prefix's to filter
	- Applied to the area you are filtering


This will filter any type 3 LSAs from being sent into area 3 for network 192.168.99.0/24

```

+---------------------+         +--------+         +--------+         +----------------------+
| 192.168.99.1 area 1 |--<--->--| area 0 |--<--->--| area 3 |--<--->--| 172.16.10.0/24 EIGRP |
+---------------------+         +--------+         +--------+         +----------------------+


prefix-list BLOCKED_ROUTE deny 192.168.99.0/24 

router ospf 1
 filter-list area 3 prefix BLOCKED_ROUTE in
!

```


## Network range
	- Filters intra-area routes
	- Applied at the ASBR
	- filters type 5 LSA
	- identifies the network with the range command ending in no-advertise

The type 5 LSA will not continue past the ABR for area 3.  
	
```
!! Area 0-3 ABR 

router ospf 1
 area 3 range 172.16.10.0 255.255.255.0 no-advertise
!
```

## Distribute list
	- Filters a route from being installed in the RIB 
	- Acts upon routes in summary LSAs(type 3)
	- uses access list to identify the LSA

```
!!Area 3 router

access-list 1 deny 192.168.88.0 0.0.0.255

router ospf 1
 distribute-list 1 in
!
