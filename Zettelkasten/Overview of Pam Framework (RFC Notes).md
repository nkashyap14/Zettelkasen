# Overview of Pam Framework (RFC Notes)


- Core components:
	- Authentication Library API (front end)
	- Authentication mechanism specific modules (backend)
	- Service Provider Interface (SPI)
		- Connects front end and backend

- Applications write  to the PAM API (front end)
	- Applications being entry points that users interact with like telnet, ftp, or login
	- These call pam API functions like pam_authenticate()
		- Application doesn't care how you authenticate it just calls pam
	- Pam will read /etc/pam.d/login (if using login)
	- PAM front end reads the config and then loads the specific authentication modules via the PAM spi (service provider interface) which calls the modules 
		- pam_unix.so, pam_sss.so which then communicate with the actual authentication systems configured ie (LDAP, Kerberos etc)
- Authentication system providers write to the SPI and supply the backend modules that are independent of the application
- Old way had a single global config file at /etc/pam.conf but modern systems have a /etc/pam.d directory where you can have a single file per service
	- there are global files to use like /etc/pam.d/system-auth and /etc/pam.d/password-auth that all configs for other services include
- Four areas of functionality for the interfaces:
	- Authentication
		- pam_authenticate(): to authenticate user
		- pam_setcred() to set, refresh, or destroy the user credentials
	- Account management
		- pam_acct_mgmt() to check whether authenticated user should be given access to his or her afcount
			- Can implement account expiration and access hour restrictions
	- Session management
		- pam_open_session()
		- pam_close_session() 
			- Session management and accounting
				- ie store total time for session
	- Password management
		- pam_chauthtok() to change password
- SPI:
	- each set of pam transactions starts with pam_start() and ends with pam_end()
	- pam_get_item() and pam_set_item() are used to read and write state infromation associated with a pam transaction
	- Can enable inter module communication about common information for authentication session like user name, service name, password and fconversation function through pam_get_item and pam_set_item()

---
Links :: [[Computer Science]] [[PAM RFC Notes]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-05 10:22
