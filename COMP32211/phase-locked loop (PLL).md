[[COMP32211]]

- PLLs are widely used for synchronisation purposes, but are also used in circuits to generate an output signal of a frequency that is a multiple of some reference input signal - there are 4 main components involved:
	- Frequency Divider - divides the output frequency by $N$ (whatever you're aiming to multiply the input frequency by), and feeds the output into the phase comparator to make sure the output signal is of a frequency as expected
	- Phase Comparator - returns an error depending on the phase of the input reference signal, and what would be our ouput, multiplied signal
	- Low Pass Filter (LPF) - smooths the output signal from the phase comparator, producing a voltage which is stable over many clock periods
	- Voltage Controlled Oscillator (VCO) - this generates the frequency that is some multiple of the input reference frequency
- the output multiplied signal is divided and compared with the original signal to ensure that you have ended up with a signal that is a multiple of the input signal, and the same phase
![](https://i.imgur.com/JXM3f4w.png)
$$\frac{f_{out}}{N} = f_{in} \textrm{   }\therefore\textrm{   }f_{out}=N\times f_{in} $$
