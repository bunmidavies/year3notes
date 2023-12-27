[[COMP32211]]

- one of the main issues within the technique of [[power domains]] is that when crossing domains, the voltage which is 'high' in one domain may not be 'high' in the next domain (?)
- this can mean that in some cases the pull-up and pull-down network are both activated (since certain transistors wont fully turn 'off'), and power dissipates from the supply voltage to ground
![](https://i.imgur.com/tpQcldU.png)

![](https://i.imgur.com/bCPzW3L.png)

# Level Shifter
- a level shifter essentially transforms a 'high' when moving from one power domain to another, to prevent problems described above
- there are different designs of level shifters, and in a lot of typical designs 'low' might always be 0.0V, so translation for low isn't required 