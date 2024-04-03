# socket function C
#### Socket function
	- To perform network input/output first thing a process must do is call the socket function
	'''
			#include <sys/socket.h>
			int socket (int family, int type, int protocol);
	'''
	-family specifies protocol family
		-AF_INET: IPv4 protocol
		-AF_INET6: IPV6 protocol
		-AF_LOCAL: UNIX domain protocols
		-AF_ROUTE: Routing Sockets
		-AF_KEY: Key Socket
	-type specifies type of socket
		-SOCK_STREAM: Stream socket
		-SOCK_DGRAM: Datagram socket
		-SOCK_SEQPACKET: Sequenced packet socket
		-SOCK_RAW: Raw Socket
	-protocol specifies the protocol
		-IPPROTO_TCP
		-IPPROTO_UDP
		-IPPROTO_SCTP
	-On success the socket function returns a small non-negative integer value. Called a socket descriptor.

---
Topics :: [[C]] [[socket]] 
Reference :: [[Unix Network Programming Volume 1]]
Type :: #atom
Creator :: Nikhilesh Kashyap
TAF ::
Discussion ::
Dis_Topic :: [[Computer Science]] [[Networking]]
Resolved ::
Date :: 2024-03-27 10:01
