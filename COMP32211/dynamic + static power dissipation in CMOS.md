[[COMP32211]]

- dynamic dissipation is caused by switching gates - therefore, it is proportional to clock frequency, and related to the activity in the circuit

- static power dissipation is close to zero and happens continuously, regardless of switching activity
- its essentially just charge leakage through paths where charge should not be, and two main types exist:
	- ==subthreshold leakage== - current through a transistor which is 'turned off'
	- ==gate leakage== - the leakage of charge from the transistors gate to the silicon channel, via the insulating layer

- static dissipation can be reduced by ==power gating== - placing a high threshold transistor in series with the power supply which is switched 'off' when a set of gates is not in use