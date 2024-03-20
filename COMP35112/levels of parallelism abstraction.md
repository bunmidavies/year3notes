[[COMP35112]]

- ==Parallel libraries== - libraries which may not even state they're parallel (i.e. you have no idea how the parallelisation works), just that they're high performance abstracted functions and are easy to use
- ==Domain Specific Languages== - R, SQL, Tensorflow - the user has the ability to specify more functionality, but the underlying execution is parallel + the compiler knows about domain specific constraints and information flow
- ==Algorithmic skeletons== - STL algorithms, MapReduce, OpenMP, Microsoft PPL, Intel TBB - General algorithmic patterns e.g. `map`, `reduce`, `for_each`, pipeline. How the threads communicate + work split is defined, as well as possible optimisations. The programmer can  then combine these to build complete algorithms/tasks
	Note that the re-factoring effort can be a downside sometimes, some parallelism is not structured, and the performance is constrained by the compiler
	The multicore 'cambrian explosion' in hardware design has led to a wide range of software optimisation strategies, with not enough time for all to be explored - this makes skeletons more applicable

![](https://i.imgur.com/HyMAMqw.png)
