# Password Mapping in PAM (Pluggable Authentication Modules))

- Feature used to solve for the issue if multiple authentication mechanisms used the same password then security could be weakened by one password becoming compromised
- Password mapping means using the users primary password to encrypt the secondary passwords nad storing the encrypted passwords in a place available to the user
- Once primary password is verified authentication modules can obtain the other passwords for their own mechanisms by decrypting the mechanism specific encrypted password with the primary password and passing it to the authentication service
- Assumes primary password is the strongest password
- If this doesnt work then user gets prompted for password by each authentication module
---
Links :: [[PAM RFC Notes]] [[PAM (Pluggable Authentication Modules)]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-05 10:40
