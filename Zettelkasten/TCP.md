# TCP

## Summary
-TCP is a network protocol that is one of the backbones of the internet
-TCP is involved in the transport layer of the OSI stack and is one of the most widely used protocols in that layer alongside protocols such as UDP, SCTP
-TCP is a duplexed bidirectional byte stream. It provides reliable, ordered, and error checked delivery of a stream of octets (bytes) between applications running on hosts (nowadays higher level programming code that is broken down into machine code and executed on computing hardware) communicating via an IP network.
-Involves a three way handshake and also utilizes both asymmetric and symmetric encryption in a way to ensure security in transit
## Subtopics
### Three Way Handshake
- **Step 1 (SYN):** In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with
- **Step 2 (SYN + ACK):** Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with
- **Step 3 (ACK):** In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer
## Details

## Conclusion


Type :: #topic
Creator ::
Date ::  2024-03-26 23:49
References :: [[Unix Network Programming Volume 1]] [[Computer Science]] [[Networking]]