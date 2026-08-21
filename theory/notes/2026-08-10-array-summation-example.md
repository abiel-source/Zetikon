Consider the example of a summation program.

- An algorithm which takes 2 arrays and returns the sum of all elements in both arrays

One possible implementation using for loops only is as follows.

<br>

$Algorithm \ \alpha(A, B, n, m):$\
$\quad Input: A \ and \ B \ are \ both \ arrays \ of \ numbers$\
$\quad Input: n \ and \ m \ are \ the \ lengths \ of \ A \ and \ B \ respectively$\
$\quad Output: Return \ the \ sum \ of \ both \ arrays$

$\quad let \ s \gets 0$\
$\quad For \ i \ in \ 1 .. n: $\
$\quad \quad s = s \ + \ A[i]$\
$\quad For \ j \ in \ 1 .. m: $\
$\quad \quad s = s \ + \ B[j]$\
$\quad Return \ s$

<br>
<hr>
<br>

The first question to ask is: What is the configuration space of this algorithm?

Or perhaps, what is the solution space that this algorithm is searching through?

And then, we can identify the particular axes of the solution space- each axis is a loop vector.

The master iterating representation can be written as a loop of loops. Each loop corresponds to one such loop vector. e.g., We have $X^1, X^2, ..., X^n$ loop vectors.

The answer is given in the master-iterator representation when a particular cell in this $CFGN$ space is a solution. i.e., $X^1[j_1] \ X^2[j_2] \ ... \ X^n[j_n]$

The return value is an integer.

At first, we immediately know that the $CFGN$ space that the algorithm searches through is at most $\mathbb{Z}$- the set of integers.

We encounter the first loop (a "loop literal"), which adds each element of $A$ to $s$.

But since this loop is deterministic (closed form) the loop-vector actually reduces to only 1 cell - the singleton loop vector - which is equivalent to $sum(A)$.

Then, we encounter the second "loop literal". Same thing. We can detect that we add all elements of $B$ to $s$ like in the first loop literal.

The resulting $CFGN$ space is actually just defined by the singleton.

The master-iterator representation might look like:

$X^1 = \{ sum(A) \ + \ sum(B)\}$

Where the return value (solution) is a trivial case since the volume is precisely 1.

<br>
<hr>
<br>

Computation in the text representation does not appear to equal the computation in the search space.

The distinction between a "loop vector" (search space, $\Xi$) and "loop literal" (text space, $\alpha$) is therefore well justified.

The deeper relationship is hidden.
