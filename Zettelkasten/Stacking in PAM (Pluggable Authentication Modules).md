# Stacking in PAM (Pluggable Authentication Modules)

- System administrator has to integrate multiple authentication mechanisms
- This feature used to address above problem + 
	- Unified login in the presence of multiple login mechanisms
- When any APi is called the backends for the stacked modules are invoked in the order listed and the result returned to the caller
![[Pasted image 20251005104550.png]]

- Since user should not know which authentication module failed when a bad password was typed the PAM framework continues to call other authentication modules on the stack even on failure
- [[Control Flag Semantics (PAM)]]
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
