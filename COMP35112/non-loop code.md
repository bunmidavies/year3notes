[[COMP35112]]

- not all code is loop based, thus loop-based [[thread-level speculation (TLS)]] is not always applicable
- a common example is recursion, but cases like large loops are rarely parallelisable, although code inside the loop body may be
- a potential workaround to this is [[method-level TLS]], and ==arbitrary point TLS==