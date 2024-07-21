# Neso Academi Course - Computer Network

Watch the course here: [YouTube Link](https://www.youtube.com/watch?v=VwN91x5i25g&list=PLBlnK6fEyqRgMCUAG0XRw78UA8qnv6jEx)

## EP 001

> This course go on a bottom up approach to study computer
> network.

**Computer Network**
: A Computer Network is a set of nodes
connected by communication links.

**Node**
: A Node can be a computer, printer, or any device
capable sending or (receiving data generated from nodes).


Nodes:
  - end devices
  - intermediary devices


Communication links:
  - wired link: **Cable**
  - wireless link: **Air**


**note**
: One of the important things in the computer networks is
the *Resource Sharing* !

**ex**
: consider 4 computers that all needs printer. we don't go
to provide one printer for every computer, we provide one
printer and then create a network from 4 computers to that
printer!

## EP 002

Basic **Characteristics** of every *Computer Network* :
  - fault tolerance
  - scalability
  - quality of service (QoS)
  - security


* fault tolerance: the ability to:
    1. continue working despite failure
    2. ensure no loss of service


* scalability:
    1. grow based on the needs
    2. have good performance after growth


* quality of service:
    1. set priority
    2. manage data traffic to reduce data loss or delay


* security:
    * prevent:
        1. unauthorized access
        2. misuse
        3. forgery

    * provide:
        1. confidential
        2. integrity
        3. availability


Internet guys:
  1. good guys
  2. bad guys (attackers)


integrity
: integrity is what one node receive what
another node send to that node.


## EP 003

* data communication
: exchanging data between 2 nodes by links.

* data flows:
    - simplex: always uni direction communication. ex: keyboards, traditional monitors
    - half duplex: both direction communication but not in the same time. ex: walkie-talkie
    - full duplex: both direction communication simultaneously. ex: telephone line

* all communications have:
    - source or sender
    - destination or receiver
    - channel or media


* protocols are rules that govern all methods of communication.

**ex**
: one person talk so fast to second person so this talk is
useless these 2 people should use protocols.


* protocols determines:
    - what
    - how
    - when

* elements of protocols:
    - message encoding
    - message formatting & encapsulation
    - message timing
    - message size
    - message delivery options

* message delivery options:
    - uni-cast: sender sends data to exactly for one node.
    - multi-cast: sender sends data to more than one and less than all nodes. ex: fm radio
    - broadcast: sender sends data to all nodes in network.

## EP 004

* data in:
    - cable: signal (electrical signal, light signal)
    - air: wave (infrared(short range), radio(WiFi), microwave(cellular system), satellite(long range - GPS))

And this affects on type of data encoding!

* networks:
    - peer to peer
    - client server

* peer to peer network:
    - no centralize administration
    - all peers are equal
    - not scalable

* client server network:
    - centralize administration
    - request-response model
    - scalable
    - server may be overloaded

## EP 005

* components in computer networks:
    1. nodes (devices)
    2. media (links)
    3. service


* nodes:
    - end nodes
    - intermediary nodes


* end nodes: sender or starter the communications
* intermediary nodes: nodes between end nodes


* media:
    - wired medium (guided medium)
    - wireless medium (unguided medium)

## EP 006

* classification of computer networks:
    - lan: local area network
    - man: metropolitan area network
    - wan: wide are network

* lan: limited area. ex: lab, school, home, university

* man: metropolitan area. ex: city, town

* wan: telecommunication (large geographical area)

* san: storage area network: cloud computing


## EP 007


* network topology = network arrange = network layout

* network topology:
    - physical topology
    - logical topology

* bus topology:  O -> O -> O -> O -> O -> O
  - advantages:
    - one wire - less expensive
    - good for temporary network (fast construct)
    - node failure does not affect others

  - disadvantages:
    - not fault tolerance (link failure affect others)
    - limited cable length
    - no security

* ring topology: link last node to first node in bus topology
    - circulate a token at a time stamp and turn determined by that token

    - advantages:
        - perform better than bus topology
        - all node equal access

    - disadvantages:
        - unidirectional
        - single node failure affect whole network (node and link affect on network)
        - no security

* star topology: connected to each other via a center node (hub or switch)
    - advantages:
        - easy design and implement
        - centralized administration
        - scalable

    - disadvantages:
        - single point failure (center node failure) affect whole network
        - increase cost due to switch or hub

* mesh topology: each node directly connected to all others
    - advantages:
        - fault tolerance
        - reliable

    - disadvantages:
        - issues with broadcasting messages.
        - expensive and impractical for large networks


* hybrid topology: combination of one or some different topology


## EP 008

* IP address: internet protocol address

* every node identify by IP address

* IP address:
    - ipv4
    - ipv6

* ipv4:
    - logical address
    - change by the location of the device
    - assigned manually or dynamically
    - represent:   
        - decimal x.x.x.x
        - binary  32bit 4byte

* mac address = media access control address

* mac address = physical address

* IP address = like location of a person
  mac address = like name of a person

* mac address:
    - every node in LAN identify by mac address
    - physical address or hardware address
    - unique
    - cannot be changed
    - assigned by the manufacturer
    - represented in hex (70-20-00-ed-fc)(48 bit)
    - separates hyphen(-) and period(.) and colon(:)

## EP 009

* packet reaching our network by IP address,
	reaching the host by mac address,
	reaching the right process by port number (port address)!

* port numbers:
	- fixed port numbers
	- dynamic port numbers

* ports are between 0 and 65535(2**16 - 1).


## EP 010


* switching in computer network helps in deciding the best route
	for data transmission if there are paths in a larger network.

* switching techniques:
	- circuit switching
	- message switching
	- packet switching

* packet switching:
	- data-gram approach
	- virtual circuit approach

* circuit switching: dedicated path is stablish between sender
	and receiver before data transfer. ex: telephone network

* phases in circuit switching:
	1. connection establishing
	2. data transfer
	3. connection disconnection

* message switching: store and forward mechanism.

* packet switching: the internet is a packet switched network.
	- message is broke to individual chunks called as packets
	- each packet is sent individually
	- each packet has sequence number

* data-gram approach in packet switching:
	- connection-less switching

* virtual circuit in packet switching:
	- connection-oriented switching
	- virtual circuit established before data transmission


## EP 011


* layering: decomposing the problem into more manageable components(layers)
	- modular development
	- easy to troubleshooting

* layered models:
	- osi model
	- tcp/ip model

* osi model: open system interconnection model
	- it is just a guidline and should be implemented
	- purpose: how to faciliate communication between
		difference hardware and software
	- was never fully implemented!!!

* tcp/ip model: transmission control protocol/internet protocol.



## EP 012


* osi reference model layers:
  - (7) application layer
  - (6) presentation layer
  - (5) session layer
  - (4) transport layer
  - (3) network layer
  - (2) data link layer
  - (1) physical layer

* data in:
	- sender: 	go from layer 7 to layer 1
	- reciever: 	go from layer 1 to layer 7

* application layer:
	- enables user to access the network resources

	- services:
		- ftam (file transfer and access management)
		- mail services
		- directory services

* presentation layer:
	- check syntax and semantics of the information

	- services:
		- translation
		- encryption
		- compression

* session layer:
	- establishes, maintains and synchronizes the interaction among communication

	- services:
		- dialog control
		- synchronization


## EP 013


* transport layer:
	- responsible for delivery process to process entire message

	- services:
		- port addressing
		- segmentation and reassembly
		- connection control (connection-less or connection-oriented)
		- end-to-end flow control (speed matching mechanism)
		- error control

* network layer:
	- responsible for delivery network to network data

	- services:
		- logical addressing (IP addressing)
		- routing


* data/link layer:
	- responsible for moving data(as frame) from one node to another node

	- services:
		- framing
		- physical addressing (mac addressing)
		- flow control
		- error control
		- access control

* physical layer:
	- responsible for transmitting the bits over a medium
		(mechanical and electrical specifications)

	- services:
		- physical characteristics of the media
		- representation of bits
		- data rate
		- synchronization of bits
		- line configuration
		- physical topology


## EP 014



* osi model vs tcp/ip model:

| osi model | protocols | tcp/ip model     |
| :------------- | :------------- | :------------- |
|  (7) application layer (6) presentation layer (5) session layer  | http, dns, dhcp, ftp		       | (4) application layer       |
| (4) transport layer	 | tcp, udp | (3) transport layer |
| (3) network layer | ipv4, ipv6, icmpv4, icmpv6 | (2) internet layer |
| (2) data link layer (1) physical layer | PPP, frame relay, Ethernet | (1) network access layer |



* tcp/ip model:
	- (4) application layer: representing data to user, encoding, dialog control
	- (3) transport layer: make communication between devices and networks
	- (2) internet layer: find best path through the network
	- (1) network access layer: controls hardware and medias that make networks

* PDU: protocol data unit (naming units convention)
	- application layer PDU: data
	- transport layer PDU: segment
	- network layer PDU: packet
	- data link layer PDU: frame
	- physical layer PDU: bits

## EP 015

* network commands for windows cmd:
	- ip configuration:
		- $ ipconfig
		- $ ipconfig/all
	- dns ip:
		- $ nslookup
	- connection reachable:
		- $ ping <dns-ip-address>
	- trace packet:
		- $ tracert <dns-ip-address>

* network commands for ubuntu terminal:
	- ip configuration:
		- $ hostname -I
		- $ ifconfig
		- $ ip a
		- $ ip route show
	- dns ip:
		- $ nslookup
	- connection reachable:
		- $ ping <dns-ip-address>
	- trace packet:
		- $ sudo apt-get install traceroute
		- $ traceroute <dns-ip-address>

* default gateway: ip address of the first router that is
	hitting from the local area network.


## EP 021

* CPT = Cisco Packet Tracer


## EP 022

**Hub**
  - a.k.a Network Hub
  - Used to set up LAN
  - Has multiple ports
  - Star topology

> When a packet arrives at one port, it is copied
> to the other ports, so that all segments of the
> LAN can see all packets.

**Hub**
  - pros:
    - cheaper than switches
    - works good for smaller networks

  - cons:
    - issues with broadcast
    - no memory
    - normally half duplex

## EP 023


**Switch**
  - Similar to Hub
  - Used to set up LAN
  - Hub has not memory, Switch has
  - Stores MAC ADDRESS TABLE
  - Layer 2 device for setting up LAN

> Hubs just can create broadcast, while Switches can create
> broadcast, multi-cast and uni-cast.


## EP 024

**Router**
  - Used to connect computer networks
  - Hub layer 1, Switch layer 2, Router layer 3
  - has memory
  - Stores routing table

**Router**
: Router connects to a LAN and a sender device send data
to that Router by LAN and Router play sender role this time
and sends data to destination of packet in new LAN!


## EP 025


## EP 026

**Repeater**
  - Regenerates signals
  - Used in same network!
  - Layer 1
  - 2 ports

## EP 027

* Bridge = Repeater + functionality of reading mac address
  - Bridge a layer 2 device!
  - interconnection for 2 LANs on the same protocol.
  - 2 port device

* types of bridges:
  - transparent bridge:
    - otheres are unaware from their existence
    - reconfiguration for nodes is unnecessary even new bridge added or
  - source routing bridge:
    - routing operation is performed by source station
    - frames specifies which route to follow

## EP 028

* list of various network devices:
  - Repeater - layer 1
  - Hub - layer 1
  - Switch - layer 2
  - Bridge - layer 2
  - Router - layer 3
  - Multi-Layer Switch (Layer 3 Switch) - layer 3
  - Brouter - (combination of bridge and router)
  - Modem
  - Firewall

## EP 029

### _solving_examples_

- nic: network interface card
- modem: modulator & demodulator
  - modem modulates analog signal to digital signal and opposite

## EP 030

- one of the major functions of the physical layer is to move data
in the form of electromagnetic signals across a transmission layer

## EP 031

**Signal**
: function of one physical quantity respect to time

signals:
  - analog signals
    - signal that can take any value in the defined range
    - all real-life signals are analog in nature
  - digital signals
    - signal that can take on the finite value at any given time

## EP 032

- Copper cable (Ethernet cable):
  - utp: unshielded twisted pair
  - stp: shielded twisted pair

- Copper Coaxical cable:
  - for audio and video communication

- Fiber Optic cable

## EP 033

- services provided by physical layer:
  - physical characteristics of the media
  - representation of bits
  - data rate
  - synchronization of bits
  - line configuration
  - physical topology
  - transmission mode: (simplex, half-duplex, full-duplex)

- line configuration = connection:
  - wireless
  - wired

- types of line configuration:
  - point-to-point:
    - the entire capacity of the link between 2 nodes are reserved
    for that 2 nodes
  - multippoint = boradcast:
    - 2 or more devices share a single link
    - the capacity of the share link is shared between connected devices
    - types:
      - spatial
      - temporal

## EP 034

* data link layer = link layer

- services by data link layer:
  - responsible for frames from one node to another node
  - framing
  - physical addressing
  - flow control
  - error control
  - access control

- physical addressing:
  - a frame is the encapsulation of the header and trailer information
  with the packet.
    - header: source and destination mac address

- flow control:
  - speed matching mechanism
  - coordinates the data that can be sent before recieving an acknowledgement

- access control:
  - media access control

- error control:
  - error detection
  - error correction

## EP 035

- data link layer sublayers:
  - llc = logical link control: bluetooth
  - mac = media access control: wifi

- llc or dlc sublayer:
  - handles communication between upper and lower layers
  - takes the network protocol and adds control information to help
  deliver packet to the destination. (flow control)

- mac sublayer:
  - data encapsulation
  - media access control
  - error control
  - responsible for the placement of frames on the media and the removal
  of frames from the media

- data encapsulation:
  - frame assembly before transmission & disassembly upon reception of a frame.

- mac layer adds a header and trailer to the network layer pdu.

## EP 036

- adaptor exchange bits, host exchange data.
- one way for framing is to have a common sequence in first and last
part of message:
  - issue: data may include same sequence in it

## EP 037

- frame = header + network layer pdu + trailer

- one way for framing is to have a fixed frame size

- framing types:
  - fixed-size framing:
    - it does not need to have additional bit for determining boundary
    the start and end of frame
  - variable-size framing:
    - it needs to have additional bits for determining boundary

- framing
  - bit oriented
  - byte oriented

## EP 038

- bit oriented:
  - frame is bits
  - interpreting bits as data by upper layers
  - bit oriented protocol: hdlc (high-level link control)

- byte oriented:
  - frame is bytes (characters)
  - a.k.a character oriented approach
  - protocols:
    - bisync: binary synchronous communication protocol
    - ddcmp: digital data communication message protocol
    - ppp: point-to-point protocol

## EP 039

- hdlc:
  - frame format:
    - 8bit beginning sequence + 16bit header + body + 16bit crc + 8bit
    ending sequence
    - beginning & ending sequence: 01111110
  - beginning and ending sequence sent even while link is idle to synchronizes
  clocks.
  - header:
    - address field
    - control field
  - body has variable size
  - crc: cyclic redundancy check - error detectoin
  - types of frames: (determined by control field)
    - i-frame: information frame (control field first bit: 0)
    - s-frame: supervisory frame (control field first bits: 10)
    - u-frame: un-numbered frame (control field first bits: 11)

## EP 040

- issue: data may include same sequence as begin and end in it

- solution: bit stuffing
  - suppose we have 01111110 in data so we create a rule that where we see
  this, insert 0 as the 7th bit! so we send 011111010!
  - and reciever also knows the rule and remove the additional 0.
  - the point is we should ensure that 011111010 is not in data before!

## EP 041

- bisync: binary synchronous communication
  - frame format:
    - 8bit syn + 8bit syn + 8bit soh + header + 8bit stx + body + 8bit etx +
    16bit crc
    - use from character (byte) stuffing

## EP 042

- ppp (point to point protocol)
  - data link layer protocol
  - wan protocol that run over internet links
  - broadband and heavy loads and high speed
  - it is used to transmit multiprotocol data between 2 directly connected
  computers

- ppp frame format
  - 8bit falg + 8bit address + 8bit control + 16bit protocol + payload +
  16bit checksum + 8bit flag
  - flag: 01111110
  - control: 11000000
  - payload: from network layer with different length

- boradcast address: 11111111

## EP 043

- ddcmp
  - data link layer protocol
  - devised by digital equipment corporation
  - it is byte-counting approach
  - count filed in the frame format
  - count: how many bytes are contained in the frame body?

- ddcmp frame format
  - 8bit syn + 8bit syn + 8bit class + 14bit count + 42bit header +
  body + 16bit crc

- danger with the ddcmp is count field
  - tranmissoin error could corrupt count field, so it is possible that
  end of frame not recieved by the reciever!


## EP 044

- for reliable communications, error must be detected and corrected
- error detection implementation
  - data link layer
  - transport layer

- error types:
  - bit error
    - aka single bit error
    - only one bit is changed
  - burst error
    - 2 or more bits in data is changed
    - length of burst error is the length of bits
    between last and first error

- how to detect?
  - adding redundancy bits (like checksum)

- how to correct?
  1. sender retransmitting data
  2. error correcting algorithm

- error detection
  - vertical redundancy check (vrc)
  - longitudinal redundancy check (lrc)
  - checksum
  - cyclic redundancy check (crc)

## EP 045

- vertical redundancy check (vrc) (parity check)
  - 1: odd number of ones
  - 0: even number of ones

## EP 046

- longitudinal redundancy check (lrc) (2d parity check)
  - data as a 2d array
  - concatenating parity of every columns

## EP 047

- checksum
  - sender
    1. break the original message into 'k' number of blocks with
    'n' bits in each blocks.
    2. sum all the 'k' numbers
    3. add the carry to the sum
    4. do 1's complement to the sum
  - so checksum is 'n' bits
  - reciever
    - calculate same to sender but not 1's complement
    - sum its result with sender result
    - all bits in out should be 1 to sure data is correct

## EP 048

- cyclic redundancy check (crc)
  1. must having divisor
  2. L = divisor length - 1
  3. append L zero to data
  4. divide result to divisor (xor division)
  5. divison reminder with L bit is the crc

## EP 049

- divisor is the same in sender and reciever
- reciever divide the whole recieved block into
divisor and its reminder all should be 0 to accept

## EP 050

- solving examples

## EP 051

- network performance
  - bandwidth (capability)
    - the bandwidth of a network is given by the number of
    bits that can be transmitted over the network in a certain
    period of time
    - 1Gb ethernet can provide a bandwidth of 1Gbps
    - unit
      - bps (bits per second)
      - hz (hertz)
  - throughput (reality)
    - the throughput is a measure of how fast we can actually send data
    - T (throughput) < B (bandwidth)
    through a network
  - latency (delay)
    - how long it takes for an entire message to completely arrive
    at the destination from the time the first bit is sent out from the
    source
    - four components
      - transmission
      - propagation
      - queueing
      - processing

## EP 052

- latency components
  - latency = transmission + propagation + queueing + processing
  - transmission delay
    - putting information on the medium
    - transmissionTime = messageSize / bandwidth
  - propagation delay
    - in medium delay
    - propagationTime = distance / propagationSpeed
  - queueing delay
    - in intermediate node queue delay
    - depends on congestion of network
  - processing delay
    - calculations in the transfer packets

## EP 053

- latency = delay
- simulation site

## EP 054

- bandwidth-delay product
  - defines the number of bits that can fill the link
  - so the capacity of the link is equal to this product

## EP 055

- solvinng problems

## EP 056

- rout trip time = rtt
  - aka round trip delay = rtd
  - it is the length of time it takes for a signal to be sent
  plus the length of time it takes for an acknowledgement of
  that signal to be received.
  - $rtt = 2 \times t_{propagation}$

## EP 057

- flow control
  - noiseless channel
    - simplest
    - stop & wait
  - noisy channel
    - stop & wait arq (automatic repeated request)
    - go-back-n-arq
    - selective-repeat-arq

## EP 058

- stop & wait protocol
  - **is a data link layer protocol**.
  - after tranmitting one frame, the sender waits for an
  ack before transmitting the next frame.
  - so order of messages are correct in this protocol
  - sender
    - send one data packet at a time
    - send the next packet only after receiving ack for the previous
  - receiver
    - receive and consume data packet
    - after consuming package ack need to be sent

  - advantages
    - simplicity
  - disadvantages
    - no loss consideration
    - no corrupt consideration
    - very low utilization

## EP 059

- stop & wait arq protocol
  - after tranmitting one frame, the sender waits for an
  ack before transmitting the next frame.
  - if the ack does not arrive after a certain period of time
  the sender times out and retransmits the original frame.
  - stop & wait + timeout timer + sequence number

## EP 060

- stop & wait arq disadvantages
  - poor utilization

- sliding window protocol
  - send multiple frames at a time
  - number of frame to be sent is based on the window size (N)
  - each frame in window has a sequence number







# End
