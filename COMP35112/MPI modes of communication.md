[[COMP35112]]

- ==standard mode== - `send` will complete once a message has been sent, but there is no guarantee at that point that the message has been received by the recipient
- ==synchronous mode== -  `send` does not complete until the message has been received, and will only return a confirmation at that point
- ==buffered== - the user supplies a buffer for `send` to use, in which confirmations will be stored