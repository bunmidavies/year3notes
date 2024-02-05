[[COMP35112]]

- threads in java can be defined two different ways
	- creating a class which inherits from `java.lang.Thread`
	- creating a class which implements `java.lang.Runnable`

- in both cases, a function you define called `run()` defines what the thread does when it is started by some other thread
- use `<threadObject>.start()` to start the thread, and `<threadObject>.join()` to wait for its completion

# simple threading example

```Java
class MyThread extends Thread {

int id;

MyThread(int id) { this.id = id; }

public void run() { System.out.println("Thread " + id + " running"); }

}

class Demo {

public static void main(String[] args) {

int NOWORKERS = 5;

MyThread[] threads = new MyThread[NOWORKERS];

for (int i = 0; i < NOWORKERS; i++)

threads[i] = new MyThread(i);

for (int i = 0; i < NOWORKERS; i++)

threads[i].start();

for (int i = 0; i < NOWORKERS; i++)

try {

threads[i].join();

} catch (InterruptedException e) { /* do nothing */ }

System.out.println("All done");

}

}

// compile and launch with:

//javac java-thread.java && java Demo
```