[[COMP35112]]

- `std::atomic<>` is a generic type that multiple threads can simultaneously operate on without raising undefined behaviour
- normally with a library like [[POSIX threads (Pthread)|pthread]], one has to wrap any operations on a shared variable with a [[pthread mutex|mutex]]
- meanwhile, with `std::atomic`, any concurrent alteration/access of the object is free from data races

# atomic_ref

- `atomic_ref` simply creates a reference to a variable in which altering the reference is atomic, but altering the underlying variable is not atomic