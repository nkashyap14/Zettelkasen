# PAM RFC Notes

## General Details

- Developed as a framework to shield higher level consumers of [[authentication]] mechanisms from changes made at a lower level to authentication mechanisms
- Provides pluggability for a variety of system entry services
	- Account Management
	- Session Management
	- Password management
- As we can stack authentication modules can integrate login with variety of authentication mechanisms like [[RSA]], [[DCE]], [[Kerberos]]
- [[Linux System Entry Services]]
	- These are various ports of entry into the system
	- Examples are [[login(linux)]]
	- [[dtlogin]]
	- [[rlogin]]
	- [[ftp]]
	- [[rsh]]
	- [[su]]
	- [[telnet]]
- System entry services need to be independent of the specific authentication mechanisms used by the machine so there needs to be a framework to plug in various mechanisms hence PAM's introduction
- Goal of pam development was for modular integration of the network authentication technologies with login and other system-entry services
- [[Identification and Authentication]] mechanism is used to establish a users identity to the system and to other principals on the network
	- For all ports of entyr into the system the user has to be identified and authenticated before granting appropriate access rights ot the user.
- Most current Unix systems the login mechanism is based on verification of the password using [[Modified DES algorithm]]
- Due to stacking the PAM api's are designed to not return any data to the application except status
	- would be hard to decide which module to send data to
- Multiple authentication mechanisms with the same password means there is increased surface area for the attack vector if password is compromised
- Configuration files must be well protected as it dictates how hte user is authenticated

## Subtopics

- [[Design Goals of PAM (Pluggable Authentication Modules)]]
- [[Overview of Pam Framework (RFC Notes)]]
- [[Configuration File Details (PAM)]]
- [[Stacking in PAM (Pluggable Authentication Modules)]]
- [[Password Mapping in PAM (Pluggable Authentication Modules))]]






Author::
Type:: #source #RFCPaper
Org::
Link::
Topics::
Date:: 2025-10-05 10:00
