# Jim Kurose - Computer Network

 [Link](https://www.youtube.com/@JimKurose/videos)


## 3.4 - Principle of Reliable Data Transfer (Part 1)

 [Link](https://www.youtube.com/watch?v=nyUHUtmxWg0)

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

- for solving [rdt 2.0](#rdt-2-0)
	- sender sends the sequence number with each packet and receiver understands that this packet is re-transmitted or not

### rdt 2.2

- we can improve the [rdt 2.1](#rdt-2-1) by combining ACK/NACK with sequence number and has a NACK-free version.



