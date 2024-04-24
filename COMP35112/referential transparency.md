[[COMP35112]]

- referential transparency is the idea of labels meaning the same thing regardless of where they occur
- this means one can replace a name with a singular value, without changing the program semantics, since the label would have been the same everywhere
- can essentially be thought of as constants, where replacing references to the constant will not result in any side effects

- example: mathematical functions are referentially transparent, such that $f(5) = 10$ - therefore, any mention of $f(5)$ could just be replaced with $10$, and the program will act exactly the same