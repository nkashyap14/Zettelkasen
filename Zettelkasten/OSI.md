# OSI

- Stands for Open System Interconnection
- 7 Layers
- Please Do Not Throw Sausage Pizza Away
	- Physical:
		- Handles transmission of [[bitstreams]] on the physical link between the sender and the immediate next hop receiver
		- Physical link can be [[Ethernet]], [[DSL]], and so on
	- Datalink
		- This layer is responsible for [[frame]] transmission, address for [[LAN]] (local area network), and [[logical link control]]
		- Data unit is considered to be a packet in the [[network]] layer and frame in the datalink layer
	- Network
		- [[IP]] addressing and routing is amongst its responsibility
	- Transport
		- Responsible for data ordering, [[reliability]], and error checking
		- Involves [[TCP]] or [[UDP]]
			- Determine app using [[port]] number and sends data to relevant app
	- Session
		- Creates, manages, and terminates the sessions between end to end devices
		- Responsible for [[authentication]] and reconnections
	- Presentation
		- Takes care of data format on sender and receiver sides
		- Ensures data is understandable at the receivers end 
		- Might do [[encryption]], [[decryption]], or [[compression]]
	- Application
		- Sender interacts with application layer
		- Various protocols
		- [[http]], [[smtp]], [[ftp]], [[dns]]
---
Links :: [[Computer Science]] [[Protocol]] [[System Design]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-04-02 12:19
