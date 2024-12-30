# computer-network

## principles

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

- delay types
  - nodal processing delay (order: microsecond)
    - lookup delay in cam (content addressable memory)
  - queueing delay (trafic (congestion) delay) (order: microsecond-milisecond)
    - waiting to transmit delay
    - **without congestion we have no queueing delay**
    - $d_que$
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

## application layer

### http

### https

## transport layer

### udp

### tcp

## network layer

### ip(v4)

### ip (v6)

### icmp

### rip

### ospf

### bgp

## data link layer

## physical layer

## network devices

### router

#### routing

- static routing
  - which network you want to go: **Network** (given in packet)
  - is subnetting valid: **Subnet Mask**
  - which ip of next router i should send you: **Next Hop** (wanted/task)

#### private networks range

- 192.168.0.0 – 192.168.255.255 (65,536 IP addresses)
- 172.16.0.0 – 172.31.255.255 (1,048,576 IP addresses)
- 10.0.0.0 – 10.255.255.255 (16,777,216 IP addresses)

#### subnetting

- why?

  - initializing the network-id (constant part with all zeros)
  - initializing the broadcast-ip (constant part with all ones)
