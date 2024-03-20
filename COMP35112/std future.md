[[COMP35112]]
[cppreferenence]([std::future - cppreference.com](https://en.cppreference.com/w/cpp/thread/future))

- `std::future` provides a mechanism to access the result of asynchronous operations
- asynchronous operations including:
	- `std::async
	- `std::packaged_task`
	- `std::promise`
- can provide an `std::future` object in the operation call to modify/access some shared state linked to the future object
- additionally, `std::future.get()` can be used to simply access a value from the future - this method blocks the program until the value is generated/available