# Design Goals of PAM (Pluggable Authentication Modules)

- System administrator should be able to choosethe default authentication mechanism for the machine
- Should be possible to configure user authentication mechnaism on a per application basis
	- ex: specific auth for telnet access
- Support display requirements of the application
- Configure multiple authentication protocols for each application
- Sys admins hould be able to stack multiple user authentication mechanisms such that the user is authenticated with all auth protocols without retyping password
- Should allow for multiple passwords if needed for higher secuirty
- System entry services should not be required to change when the underlying mechanism changes
- Provide a pluggable module for system authentication as well as other related tasks like password, account and session management
- Support the authentication requirements of the current (at the time of design) system entry services

---
Links :: [[Computer Science]] [[PAM RFC Notes]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-05 10:11
