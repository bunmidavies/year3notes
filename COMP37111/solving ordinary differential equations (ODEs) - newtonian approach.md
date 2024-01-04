[[COMP37111]]
*?*

- to solve ODEs, a number of tools can be used - the method below is known as the ==newtonian approach==
- in the example below, F and m are known to us, but we'd like to know x, the position of the object we're applying a force to
![200](https://i.imgur.com/2Y5oxHB.png)
- the bottom equation is a 2nd order ODE, as we're dealing with a 2nd differential (derivative of derivative of position is acceleration)
- to reduce this to a 1st order ODE, we find 2 ODEs which correspond to the same system
![200](https://i.imgur.com/dsv8xvC.png)
- we now have 2 unknowns (x,v) - by stacking the two into a state vector $X$, we can take the derivative of both sides and now solve this system
![300](https://i.imgur.com/FuWTJXV.png)

![](https://i.imgur.com/iMSTzjd.png)
