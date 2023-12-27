[[COMP32211]]

![](https://i.imgur.com/dAofUfQ.png)
- in reality, the flow of design to production is not as simple as the diagram, but the overall view is still accurate
- some stages described below
- 'tape out' is simply the final stage after all design stages are successful - a finalised design is sent to a fabrication plant (though some changes may still be needed later on)

- ==P & R = Place and Route== = placement is the act of mapping cells onto the surface of the silicon such that nothing overlaps, and preferably connected cells should be placed adjacently
- an 'ideal' placement has all required cells clumped tightly together, but is typically infeasible for a number of reasons (space must be left for later stages, routing would become impossible)
- routing is the process of interconnecting all cells with wires - wires cannot touch or cross, but can use a number of wiring layers. Preferably, only lower layers should be use, to minimise parasitic load capacitance

- ==floorplanning== = the placement of logic blocks, rather than individual cells - essentially, some layout can get 'hardened' (like [[macrocells]] ?) and have multiple instances of that same block placed

- ==buffer insertion== = the insertion of electrical buffers (not 'latch' buffers), typically along data buses with long travel distances, in order to reduce the number of slow signal edges in the circuit
- most processes will automatically detect where buffers may be required - propagation delay may typically be introduced, but overall time is saved, and electrical integrity is preserved (i.e. noise is prevented)

- ==DRC = design rule checks== = see that the layout obeys geometry rules for fabrication
- ==ERC = electrical rule checks== = ensure that electrical connections e.g. power are legal
- ==LVS = Layout versus Schematic== = ensure that what is laid out is the same as what is wanted (i.e. layout is compared to cell netlist?)
- ==Antenna Checks== = test that the device will not be destroyed when manufactured
![](https://i.imgur.com/T1aKEsC.jpg)
