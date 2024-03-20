[[COMP35112]]

- scoped locks will lock multiple existing locks at creation, and unlock all of these at destruction
- this essentially avoids deadlocks from occurring when used (though in many cases you might not want to lock/unlock all locks at once)