[[COMP22111]]
[[COMP32211]]

MOSFETs are used within the vast majority of [[VLSI systems]] - MOSFET stands for ==Metal Oxide Semiconductor Field Effect Transistor==

this name comes from earlier designs where layers of metal and semiconducting material was separated by an 'oxide' layer

==MOS== refers to any type of transistor with a metal-oxide layer, whereas ==MOSFET== specifically refers to the transistors with a metal-oxide layer to control the flow of current through the transistor

- the ==channel== - made of a n-type material for pMOS transistors, and p-type material for nMOS transistors - is also called the ==substrate== - the channel sits between the source and drain, and is what the charge carriers travel across to reach each side
- the ==gate== of a MOSFET sits between above the channel (and a dielectric layer), between the source and drain - as can also be seen, the drain and source are of the same material - voltage is applied to the gate
- there is a thin insulating layer made of 'oxide' in order to prevent gate leakage - i.e. when the gate is turned off, prevent charge carriers from travelling across the gate resulting in power dissipation
- the main dimensions to consider are both the length of the channel and its width (L and W), as well as the thickness of the source/drain
![](https://i.imgur.com/G3FIrCn.png)


>[!note] Enhancement Mode Devices
> the MOSFETs we are concerned with in 32211 are ==enhancement== mode devices, meaning they are normally switched off, and require a voltage being applied in order to conduct charge

# operation
- the opposite type of dopant is used for both types in order to create a depletion region, such that no current can move from source to drain (the dopant of source and drain match the type of MOS)  
- nMOS transistors use a p-type doped substrate - as the gate is positively charged (i.e. positive voltage applied), electrons become attracted, eventually allowing current to flow from source to drain  
- pMOS transistors use an n-type doped substrate - taking the gate low (i.e. 'negative' voltage) repels electrons, causing 'holes' (positive charge carriers) to form in the channel, enabling current to flow from source to drain

![](https://i.imgur.com/3RR9DeD.png)

 