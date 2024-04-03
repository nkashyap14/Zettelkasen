# Connect Function
#### Connect function
	-Used by a TCP client to establish a connecction with a TCP server
	'''
	int connect (int sockfd, const struct sockaddr *servaddr, socklen_t addrlen);
	'''
		-sockfd is a socket descriptor returned by the socket function
		-second and third arguments are pointer to a socket address structure and its size
		-socket address structure must contain ip address + port number of the server
	-In the case of a TCP socket initiates TCP's 3 way handshake

---
Topics :: [[C]] [[socket]]  [[TCP]]
Reference ::[[Unix Network Programming Volume 1]]
Type :: #atom
Creator :: Nikhilesh Kahsyap
TAF ::
Discussion ::
Dis_Topic :: [[Computer Science]] [[Networking]]
Resolved ::
Date :: 2024-03-27 10:03
