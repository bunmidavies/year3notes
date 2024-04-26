[[COMP34212]]

- feedback control is good for low-level motor actions and resolving errors, while AI/cognition typically handles the higher-level behaviour
# proportional control (P)

- system responds based on the ==proportion of error== (considering direction and magnitude)
- gain = the parameter that determines the magnitude of the system's response
- the state typically oscillates, fluctuating between an underestimate/overestimate of the motion required to reach the desired state
- damping = process of systematically decreasing the oscillation

# derivative control (PD)

- system responds based on the ==proportion of error + derivative of error signal==
- this solves the previously mentioned gain/oscillation problem - when the system is close to the desired state, it is controlled differently to when it is farther away 
- momentum is adjusted as the system approaches the desired state (-(gain * velocity))
- used widely in industrial robotics

# proportional integral control (PID)

- the system has an integral term $I$ that integrates incremental errors over time - when this term reaches a threshold, the system compensates/corrects
- many joints use PID controllers

![400](https://i.imgur.com/rJZw7P7.png)
