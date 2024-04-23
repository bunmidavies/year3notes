[[COMP35112]]

- in method-level TLS, once some method is encountered, a non-speculative thread can continue to run this method as normal, while a speculative thread can run whatever code follows in the hopes of committing:

![](https://i.imgur.com/fa2ZypX.png)

- as long as the speculative thread didn't miss a non-speculative write, then both threads can commit, otherwise the speculative thread must rollback