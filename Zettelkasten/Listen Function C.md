# Listen function C

Listen Bind function
	-Called only by a TCP server
		-Listen function converts a created socket which is assumed to be an active client socket into a passive socket. This indicates that the kernel should accept incomign connectoin requests directed to the socket
		- Second argument specifies max number of connections kernel should queue for the socket
	- Called after [[socket function C]] and [[bind function C]]
	- Must be called before [[Accept function C]]
	
	'''
	int listen (int sockfd, int backlog);
	'''

---
Topics :: [[bind]] [[C]] [[socket]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: [[Computer Science]] [[Networking]]
Resolved ::
Date :: 2024-03-27 10:02
