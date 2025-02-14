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
  - width of band
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
    - $d_{queue}$
  - transmission delay (order: milisecond)
    - node to link delay
    - $d_{trans} = \frac{L}{R}$
  - propgation delay
    - in link delay
    - $d_{prop} = \frac{d}{s}$
    - $(s=3 \cdot 10^8 \frac{m}{s})$
  - nodal delay
    - summation of all delays
    - $d_{nodeal}=d_{proc}+d_{queue}+d_{trans}+d_{prop}$
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

- guarantees of transport layer
  - reliable transfer
  - throughput
  - timing
  - security

- throughput (focus on volume)
  - band-with sensetive (rate should be more that r)
  - elastic (any rate is okay!)

- timing (focus on time)
  - real-time application constraints

- messaging
  - connection-oriented (tcp)
  - connection-less (udp)

- connection
  - persistent (tcp persistent)
  - non-persistent (tcp non persistent)

- rtt
  - round trip time
  - time of packet to goes from client to server and back
  - $rtt = d_{process} + d_{queue} + d_{propagation}$

- proxy (ex: web cache)
  - sits front of clients and response to them
  - usually for caching

- reverse proxy
  - sits front of servers and redirect messages to correct server!
  - usually for routing and load balancing

- cache time calculation

$$
\text{HitRate} + \text{MissRate} = 1
$$

$$
t = (\text{HitRate} \cdot \text{CacheProcessTime}) +
(\text{MissRate} \cdot \text{CacheProcessTime + MainProcessTime})
$$

- conditional `GET`
  - first check is anything new exists

- http and ftp are on tcp

- ftp
  - control tcp connection
  - data tcp connection

- centeralized design problems
  - single point of failure (spf)

- dns server classes
  - root
  - tld (top-level-domain)
  - authoritative
  - local

- query to servers types
  - recursive (goes deep inside)
  - iterative (goes one by one)

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
