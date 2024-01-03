[[COMP37111]]

- bernstein polynomials, named after Sergei Natanovich Bernstein, initially existed simply for approximating continuous functions, and to prove the Weierstrass approximation theorem
- a bernstein polynomial of degree $n$ is made up of $n$ bernstein ==basis polynomials==, which are calculated in a binomial expansion type manner

- bernstein basis polynomial $i$ in bernstein polynomial of degree $n$:
$$B_{i,n}(t) = {i \choose n} t^i(1-t)^{n-i}$$

- bernstein polynomials also have 2 main constraints:
	1. non-negativity: $t$ is always between 0 and 1
	2. sum of all bernstein basis polynomials =1 (partition of unity)

- bernstein polynomials can also be represented as matrices, to allow for fast calculation of bezier curves using t, as well as the inversion of the matrix in order to find t based off curve points ($t\rightarrow B(t)$ and $B(t) \rightarrow t$, respectively)