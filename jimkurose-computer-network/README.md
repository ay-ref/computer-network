# Jim Kurose - Computer Network

 [Link](https://www.youtube.com/@JimKurose/videos)

## 3.1 - introduction and transport layer services

- protocols
  - udp
  - tcp

- tcp
  - transmission control protocol
  - flow control
  - congestion control
  - connection setup
- udp
  - user datagram protocol
  - unreliable, unordered delivery
  - no-frills extesion of best-effort ip

## 3.2 - multiplexing and demultiplexing

- multiplexing (routing) all ports to below layer
- demultiplexing (routing) below layer to all ports
- **SO ONE OF SEGMENT FORMAT HEADER IS PORT HEADER**
- in tcp mux/demux is done by 4-tuple
  - `(source_ip, source_port, destination_ip, destination_port)`
  - **SO IT IS POSSIBLE TO MULTIPLE PROCESSES HAVE SAME TCP PORT, (BUT IF SUPPORTED AND ENABLED)**

## 3.3 - udp

- connectionless
  - no handshake

- advantages
  - simple
  - small header size
  - fast
  - work on congestion control

- HTTP Version Transport Protocol
- HTTP/1.0 TCP
- HTTP/1.1 TCP
- HTTP/2 TCP
- HTTP/3 UDP (QUIC)

## 3.4-1 - Principle of Reliable Data Transfer (Part 1)

- we first start the designing the systems by relaxing all of limitation and then improve it.
- IP or internet protocol in network layer is a unreliable protocol.
- so we should design a reliable data transfer protocol on it in the transport layer.
- as usual we have 2 side:
  - sender side
  - receiver side
- communication between sender and receiver is bi-directional.
- complexity of reliable data transfer protocol depends on characteristics of the bottom unreliable channel:
  - lose messages
  - corrupt messages
  - reorder data

> sender and receiver don't know the state of other one and just found by the sending message.

- interfaces:
  - sender side:
    - `rdt_send()`
    - `udt_send()`
  - receiver side:
    - `rdt_receive()`
    - `deliver_data()`
- we should implement `rdt_send` and `rdt_receive` method interfaces.
- we show the systems by designing an FSM (finite state machine).
- every state is shown by a circle and inside it we write the state description and every state go to next by an event/actions pair.

### rdt 1.0

- underlying channel perfectly reliable
  - no lose messages
  - no corrupt messages
  - no reorder messages

- in this limitation we just call `udt_send` and `deliver_message` in the `rdt_send` and `rdt_receive`.

### rdt 2.0

- underlying channel:
  - no lose messages
  - has corrupt messages
  - no reorder messages

- in this limitation we should use from a detection/recovery corrupt message.
  - we do this by checksum for detection.
  - how to recovery
    - re-transmit corrupted message by sender
    - receiver should explicitly tell to the sender that it is received corrupted or not corrupted messages by ACK/NACK.
  - this is an stop and wait behavior.

- rdt 2.0 solution has a fatal flaw!
  - what if the ACK/NACK themselves being corrupted
  > assume that receiver says ACK and prepare for getting next message but sender receives the NACK! so it decide to send that message again but receiver think that it is new message and so receiver deliver one message 2 times (or more) and we have a duplicate problem!

### rdt 2.1

- for solving [rdt 2.0](#rdt-20)
  - sender sends the sequence number with each packet and receiver understands that this packet is re-transmitted or not

### rdt 2.2

- we can improve the [rdt 2.1](#rdt-21) by combining ACK/NACK with sequence number and has a NACK-free version.

## 3.4-2 - Principle of Reliable Data Transfer (Part 2)

### rdt 3.0

- underlying channel:
  - has lose messages
  - has corrupt messages
  - no reorder messages

- add a timer for waiting reasonable time
- we have duplicate problem again
  - we solve it in same way that we solve in [rdt 2.1](#rdt-21)

- this works fine, but!
- utilization

$$
U_{sender} = \frac{L/R}{RTT + L/R} \approx 0
$$

> stop-and-wait strategy always is bad in utilization and so performance

- the solution is pipelining technique
  - this is done with the sequence number

### go back n

#### sender

- window with length of n (working frame)

- packet categories
  - already acked
  - sent, not yet acked
  - not yet sent
  - for future

- cumulative ack
  - all in window packet should be acked
  - it moves window while in-order message from first ack received
  - if some timer timed out then sender sends all in window packets again!

#### receiver

- ack only
  - send ack to successfull packet highest sequence number in-order
  - if it is not in order it ignores

### selective repeat

- window with length of n (working frame) for both sender and receiver
- not in same layout and type of packets

#### sender side

- packet categories
  - already acked
  - sent, not yet acked
  - not yet sent
  - for future

#### receiver side

- packet categories
  - past acked
  - out of order acked
  - expected, not yet acked
  - acceptable
  - for future

## 3.5-1 - tcp (part 1)
