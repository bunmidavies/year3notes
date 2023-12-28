[[COMP32211]]

- maintaining variability, thus guaranteeing reliability within devices today is already difficult, and will only become more difficult for future devices

*taken from COMP22111 [[verification vs testing]]*
- **by nature, some chips made with silicon will just be faulty by chance** - the percentage of chips that **do** work is known as the 'yield'. This should be expected to be around 80%+. Chips with a bigger area are more likely to be faulty, but with smaller chips the variations are ==proportionally larger==
![](https://i.imgur.com/J9vm2BC.png)

- in this picture, the big circle is a silicon wafer, and each square within the grids are individual chips - the red dots indicate some sort of fault (32211 says diffusing atoms)

![](https://i.imgur.com/y72SBSG.png)


- as reliability decreases, the need for redundancy becomes more appealing (take how commercial planes have multiple engines when not all engines are required, it is simply the case that they are less reliable but most crucial)
- redundancy already exists within RAM, especially on server systems - error detection and correction codes ([[hamming codes]]) already exist to increase memory reliability

