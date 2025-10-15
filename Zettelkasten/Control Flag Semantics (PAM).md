# Control Flag Semantics (PAM)

- Required:
	- Must pass but PAM continues checking other modules.. Failure is returned after all modules
- Requisite:
	- Must pass, PAM stops immediately on failure doesn't run other modules
- Sufficient:
	- Success means stop immediately and return success. Failure means continue to the next module
- Optional:
	- Result ignored unless only module in the stack
---
Links ::  [[PAM (Pluggable Authentication Modules)]]
Reference ::
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2025-10-05 10:40
