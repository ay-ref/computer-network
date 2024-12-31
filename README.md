# computer-network

## principles

### basics

- protocol (in communication)
  - message format
  - message order ordered
  - **actions needed for message transferring**

- network
  - communicating graph

- network
  - core (centeral points)
  - edge (marginal points)

- link
  - connection
  - media
  - wire

- bandwidth
  - width of  band
  - maximum capacity of transferring in same time

- network core types
  - packte switching
    - going through devices dynamically
    - flexibility
  - circuit switching
    - dedicated end-to-end connection
    - guarantii
    - types
      - fdm (frequency division multiplexing)
      - tdm (time division multiplexing)

> we works with packet-switched networks usually!

- internet
  - one case of networks of networks

### delay

- delay types
  - nodal processing delay (order: microsecond)
    - lookup delay in cam (content addressable memory)
  - queueing delay (trafic (congestion) delay) (order: microsecond-milisecond)
    - waiting to transmit delay
    - **without congestion we have no queueing delay**
    - $d_{que}$
  - transmission delay (order: milisecond)
    - node to link delay
    - $d_{trans} = \frac{L}{R}$
  - propgation delay
    - in link delay
    - $d_{prop} = \frac{d}{s}$
    - $(s=3 \cdot 10^8 \frac{m}{s})$
  - nodal delay
    - summation of all delays
  - end-to-end delay **(without congestion)**
    - $\sum \text{nodal delays}$
    - $d_{e2e} = N \cdot (d_{proc} + d_{trans} + d_{prop})$
  - average throughput
    - **used in end-system (client) application to show network speed to user**
    - $\text{average throuput} = \frac{F}{T}$

- trafic congestion
  - **situation where input rate is more than function rate or function rate is more than output rate!**

- **delay packet loss occurs on queueing delay!**
  - after the queue capacity is full

- trafic
  - $a=\frac{\text{packets count}}{t}$
- trafic intensity
  - $\text{trafic intensity} = \frac{L \cdot a}{R} = a \cdot d_{trans}$

- bottleneck
  - congestion point!
  - other system components should wait for it!
  - "a chain is no stronger than its weakest link"

### architecture

- layered architecture
  - Layered Architecture is a design approach in computer science
    where the application is divided into separate layers that can
    be managed and maintained **independently** (scalable approach!!!).

## application layer

### http

### https

### dhcp

- dynamic host configuration protocol
- used for automatic ip settings

1. client dhcp sends dhcpdiscover request broadcast
2. server responds dhcpoffer response including ip/subnet, default gateway, lease time, ...
3. client sends dhcprequest for accepting dhcpoffer
4. server responds dhcpack that finalize the settings

> dora!

## transport layer

### udp

### tcp

## network layer

### ip(v4)

### ip (v6)

### icmp

- internet control message protocol

> ping command uses icmp protocol!

### rip

### ospf

### bgp

## data link layer

### arp

- address resolution protocol
- used for creating ip-to-mac table in switch

1. an arp request go to switch
2. if switch has arp request key it returns
3. else source sends a broadcast request to lan to find the ip address
4. then destination after getting arp request sends arp response to source
5. source find the mac address from arp response

## physical layer

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
