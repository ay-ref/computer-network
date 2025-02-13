# temp

## network devices

### router

#### routing

- routing
  - static
    - manual routing
  - dynamic
    - distance vector
    - link state
    - hybrid (ex: eigrp)

- static routing
  - which network you want to go: **Network** (given in packet)
  - what is the subnetmask: **Subnet Mask**
  - which ip of next router i should send you: **Next Hop** (wanted/task)

```shell
ip route destinationnetworkip destinationnetworksubnetmask nexthop administrativedistance
```

- solving routing loops
  - ttl (time to live)
  - maximum hop count
  - split horizon
  - loop-free alternative path (lfa)

- administrative distance (ad)
  - a number with arbitary unit assigned to routes for priority in routing
  - lowest ad has the highest priority

- distance vector
  - bellman-fold algorithm
  - metric is hop count
  - every router just compute next route (neighbours updating)
  - implementation is rip and igrp
  - not scalable

- link state
  - dijakstra's algorithm
  - implementation is ospf
  - scalable

- rip
  - v1 (just classful and broadcast) and v2 (also classless and multicast)
  - use distance vector
  - metric is hop count
  - set max hop count for preventing loops
  - not scalable

  1. routing table creation
  2. neighbour periodic update
  3. update propagation

  - timers
    - update timer
    - invalid (expiration) timer
    - hold-down timer
    - flush timer

- igrp
  - use distance vector
  - combinations of metrics
  - also manual metric is possible
  - combinations of approach for preventing loops
  - scalable

- eigrp
  - enhanced igrp
  - use distance vector and link state together (hybrid algorithm)
  - combination of metrics

- rtp
  - reliable transport protocol
  - ensure no routing information is lost for route finding algorithm

- dual
  - diffusing update algorithm
  - sharing node information to neighbours fast

- ospf
  - open shortest path first
  - link state algorithm
  
  1. assign router id (rid)
  2. link state advertisement (lsa)
  3. centeral database stores all lsas (lsdb)
  4. routing table creating in lsdb with dijstra algorithm

  - routers and networks
    - internal routers (ir) (same area routers)
    - backbone routers (br) (routers in area 0)
    - area border router (abr) (routers connect different areas)

- bgp
  - border gateway protocol
  - used for maximize scalability
  - divide whole network in 2 parts
    - igp (interior gateway protocol)
    - egp (exterior gateway protocol)

- as (asn)
  - autonomous system number
  - used in bgp
  - same as are in same gateway (igp)

- nat
  - network address translation
  - mapping one or some internal ip addresses to one or some external ip addresses
  - used for
    - sharing multiple private system to one ip
    - more security (hiding ip)
    - solving ipv4 ip count limitation
  - types
    - static nat (snat)
      - one-to-one ip mapping
    - dynamic nat (dnat)
      - list-to-pool ip mapping (ip is not constant each time!)
    - port address translation (pat)
      - list-to-ip:port ip mapping (not overloading)

##### vlan

#### private networks range

- 192.168.0.0 – 192.168.255.255 (65,536 IP addresses)
- 172.16.0.0 – 172.31.255.255 (1,048,576 IP addresses)
- 10.0.0.0 – 10.255.255.255 (16,777,216 IP addresses)

#### subnetting

- practice
  - initializing the network-id (constant part with all zeros)
  - initializing the broadcast-ip (constant part with all ones)
  - manage ips
  - easy control
  - performance
  - security

- classful subnetting
  - a (/8) (255.0.0.0)
  - b (/16) (255.255.0.0)
  - c (/24) (255.255.255.0)

- (/8 or 255.0.0.0) are examples of subnet mask.
  (32bit - subnet mask) determines how many ips (usually hosts) can be exists as valid.

- for solving issues first you should find the subnet ip range (start(nid) to end(broadcast) interval).
  then you can response any problems against subnetting.

- cidr (agains classfull subnetting)
  - classless inter-domain routing
