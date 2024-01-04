[[COMP32211]]

- reducing frequency by an integer factor is straightforward - note that dividing by an odd integer will result in a frequency 
- increasing frequency is slightly less straightforward - typically, a [[phase-locked loop (PLL)]] is used

- there are various reasons for why adjusting signal frequency might be desired:
	- it can be difficult to transfer UHF (ultra high frequency) signals across a PCB
	- switching signals dissipates power, and also emits Radio Frequency Interference (potentially illegal, type shit you put your phone on airplane mode for ?)
	- typical crystal controlled oscillators are quite cheap and precise, but come in frequencies ranging from 1-100MHz - modern computers are typically clocked much faster, so just multiplying the crystal frequency is a common option

