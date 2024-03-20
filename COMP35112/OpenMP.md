[[COMP35112]]

contents:
- [[OpenMP#intro|Intro]]
- [[OpenMP#parallel region|Parallel Regions]]
- [[OpenMP#number of threads|Modifying thread count]]
- [[OpenMP#omp thread_id|Getting thread IDs]]
- [[OpenMP#omp for|Loop splitting]]
- [[OpenMP#reduction clause|Reduction]]
- [[OpenMP#variable visibility|Variable Visibility]]
- [[OpenMP#synchronisation|Synchronisation Mechanisms]]
- [[OpenMP#loop scheduling|Loop Scheduling]]
- [[OpenMP#omp sections|Sections]]
- [[OpenMP#omp tasks|Tasks]]
# intro
- openMP is a [[levels of parallelism abstraction|skeleton-ish]] library allowing for the automatic parallelisation of code, with multiple patterns available
- skeleton-ish as there is no global optimisation, nor does it allow you to fully compose functions like actual skeleton algorithms
- openMP offers compiler directives and library functions, with implementations existing in C, C++ and fortran
- the overarching goal of openMP is to provide users the ability to exhibit parallel performance from serial code with minimal effort

- openMP uses the fork-join model - when entering a parallel region, openMP creates a number of secondary threads which execute in parallel. Once this parallel region ends, all secondary threads are joined back into a single thread
![500](https://i.imgur.com/ZMAs4oE.png)

# parallel region
- a parallel region is indicated with `#pragma omp parallel` in c/c++ openMP
	- `#pragma` tells the compiler this is a directive to be followed
	- `omp` passes the directive to the openMP system
	- `parallel` notes that the following region enclosed in braces is a parallel region
- multiple threads then execute the code in the block
# number of threads
- by default, openMP will create the same number of threads as the machine has cores, or some other safe choice
- to statically change this within a parallel region, `num_threads(n)` can be used
- in runtime code, `omp_set_num_threads(n)` can be used
# omp thread_id
- the current openMP thread running can be obtained using `omp_get_thread_num()`
- this function is part of the runtime openMP interface, thus `<omp.h>` must be included 

# omp for
- openMP's `for` directive automatically assigns iterations of the loop to threads - this can be useful for time consuming loops
- the parallel region is initially declared with `#pragma omp parallel`, then `#pragma omp for` is used to split the for into separate iterations

# reduction clause
- the reduction clause in openMP is similar to `reduce` operations, but allow multithreading to be introduced, reducing serial bottlenecks
- `reduction(+:var)` does the following for `var`
	- on loop entry, creates a local copy of `var` for each thread
	- inside each loop, each thread only updates its copy of `var
	- when the loop exits, the local results of `var` are combined with the specified operation, in this case, `+`
- in short, `operation:variable` allows local copies of `variable` to be made then combined using `operation`

- for array sections, `reduction(operation:array[start:end])` must be used
- for user declared reduction operations, `reduction(user_defined_operation:variable)` must be used

# variable visibility
- by default, anything declared outside a parallel region in openMP will be copied by all threads, such that they all use the same copy (bar the loop iteration counter)
- anything declared inside the parallel region is private, and each thread will have its own uninitialised copy
- variable visibility can be controlled through the using the data sharing directives
	- `shared()`
	- `private()` + `firstprivate()`/`lastprivate()
	- `reduction()`

# synchronisation
- openMP has the following directives/runtime functions for coordination between threads:
	- `barrier` - all threads wait - implicit barrier after work sharing constructs
	- `nowait` - skip implicit barrier after work sharing constructs
	- `omp_(un)set_lock()` - manual locks (library calls)
	- `critical` - critical section, executed only by 1 thread at a time
	- `atomic` - the memory update in the next statement is atomic

# loop scheduling
- the `schedule()` clause can define how iterations are divided between threads - by default openMP tries to divide these evenly
- `(static, 1)` - cyclic scheduling
![](https://i.imgur.com/SuKoZkk.png)
- `(static, 2)` - block-cyclic scheduling
![](https://i.imgur.com/IHvvn9K.png)
- `(dynamic, <n>)` - each thread processes `n` iterations before asking the scheduler for another chunk
- work becomes more balanced, but more overhead is required
![](https://i.imgur.com/ML5qyBf.png)

# omp sections
- sections are used for parallelising straight line code
- the overall parallel region is firstly defined with `#pragma omp parallel sections`
- `#pragma omp section` is used to indicate blocks of code to be executed by singular threads asynchronously
- there is an implied barrier at the end of the parallel sections
# omp tasks
- tasks are for asynchronous computation (in a loop or not)
- `#pragma omp task` indicates code that can be asynchronously placed in some task queue to be executed in the future, but in the correct order
- `#pragma omp single` can also be used to indicate that the following block should be executed only once, even if multiple worker threads are used within the block
- `#pragma omp taskwait` is a barrier for tasks, which prevents the following code from running until all children tasks are complete (though children of those children are not waited for)
- to solve dependency issues, the `depend()` clause can be used to indicate a list of items that are input/output dependencies of the task, preventing certain tasks from running if a value has not yet been generated
- creating a new task or not can also be controlled by conditional statements, just by adding them on the end of the task directive e.g. `#pragma omp task shared(x_1) if (num > 30)`