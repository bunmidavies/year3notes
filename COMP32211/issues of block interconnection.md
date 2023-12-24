[[COMP32211]]

- the issues concerning block interconnection can be split into two main topics:
	- ==logical interfacing problems== - this has led to the use of standardised interfaces e.g. AMBA (developed by ARM), OCP
	- ==electrical interfacing problems== - issues such as clock skew between the source and destination block, as well as bit skew within buses are prevalent. Issues such as round trip delays (the delay involved with a signal being acknowledged after being received) and drive capacity are also of concern
- week 7 predominantly focuses on logical interfacing issues