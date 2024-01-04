[[COMP32211]]

- occasionally, certain pipeline stages may require multiple cycles to fully evaluate - there are no clever tricks to implement this, the CAD tools just must be aware that inputs to a subsequent register for the stage may not stabilise in a single clock period