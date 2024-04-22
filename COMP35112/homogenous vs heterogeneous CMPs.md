[[COMP35112]]

- homogeneous CMPs have been the go-to as of recent times for the following reasons:
	- moore's law isn't completely dead
	- end of [[dennard scaling]] = cores not getting larger, more cores are just introduced instead - ==we cannot power entire homogeneous chips==
	- more transistors = more cores per chip
	- design of such chips is easy, and programmers do not need to program with specific cores in mind, and communication between cores is straightforward

- however, the following issues become more prevalent within homogeneous CMPs:
	- ==diminishing returns== - more cores past a certain point doesn't return a reasonable amount of performance gain ([[amdahls law]])
	- using better cores for better serial performance has been a dead end since the early 2000s ([[power wall]])
	- ==inflexibility== - different applications and program behaviours with different targets in terms of performance, energy efficiency and predictability could do better if not restricted to this one-size-fits-all approach

- so using ==different cores== has become the main point of interest as more cores and bigger cores have become unviable solutions
- while not all cores will be able to be powered at the same time, we can choose more appropriate cores to be powered on at any given time, given program requirements in terms of energy efficiency and performance