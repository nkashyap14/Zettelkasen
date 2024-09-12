# Reliability (Probability)

- [[Probabilistic Model]]'s of complex systems involving several components where we assume the behavior of components are uncoupled/[[Independence|independent]]
- Two types of subsystems:
	- Series
		- Series subsystem succeeds if all of its components are up 
		$$
		P(Series SubSuccess)=p_1*p_2*...p_m
		$$
	- Parallel
		- Parallel subsystems succeed if any one of its components succeed
		$$
		P(ParallelSubSuccess)=1 - P(Parallel Subsystem fails)
		$$
		$$
		P(ParallelSubsystemFails)=(1-p_1)(1-p_2)(1-p_3)*...*(1-p_m)
		$$
		$$
		where p_i = probability-component-i-fails
		$$
---
Links :: [[Probability]]
Reference :: [[Introduction To Probability 2nd Edition]]
Type :: #atom
Creator ::
TAF ::
Discussion ::
Dis_Topic :: 
Resolved ::
Date :: 2024-05-01 10:32
