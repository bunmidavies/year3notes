[[COMP32211]]

- a power distribution network is made of metal wires which have some inherent resistance - this means there will be a ==voltage drop== from the supply (at the 'pad ring') to the circuit itself
- this basically just means the supply voltage at the circuit is slightly less than specified, so the circuit operates under different conditions than intended, which can cause issues for the system if the voltage drops outside of some expected bound

- CAD tools typically allow for some estimation of this voltage drop, taking into account the logic, their activity and the power distribution wiring - the CAD tools thus can identify where issues may occur
- the typical solution is to provide additional wiring to those areas, or in more drastic cases, changing the entire floorplan