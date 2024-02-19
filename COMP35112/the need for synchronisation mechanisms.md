[[COMP35112]]

- in a multithreaded program, threads rarely execute completely independently:
	- in many scenarios, one thread will need to wait for another to communicate by accessing shared data
	- this introduces the need for ==synchronisation mechanisms==
- multiple synchronisation mechanisms exist, including:
	- [[barriers]]
	- [[locks]]

- areas of code in a program where shared data is accessed/updated are known as ==critical sections== - identifying these are the job of the programmer