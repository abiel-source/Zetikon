**Tripartite Equivalence**

An algorithm may be axiomatized.

Any program has multiple equivalent forms.

The way an algorithm changes is reflected in these equivalent forms.

Namely, it may be the case that any algorithm is equivalently:

- A geometric space or manifold which may take an irregular shape
- A tensor or matrix equation of program axioms

These are equivalent forms.
The optimization of an algorithm, for instance, also reflects the equivalence.

<br>
<hr>
<br>

**Hypothesis: Master Representation**

Any arbitrary algorithm or program can be represented as a sequence of nested loops.

- The proof of this hypothesis can be repurposed as an algorithm called $I$ that takes an algorithm $\alpha$ and returns a master representation called $\iota \in Ι(\alpha)$

Suppose the algorithm $I$ holds

- if it doesn't hold generally, we consider the space of algorithms where it does hold
- i do not see generally why it wouldn't necessarily hold

**Hypothesis: Minimizing or Simplified Master Representation**

- amongst all possible master representations $\iota \in I(\alpha)$ for a given algorithm $\alpha$, we can choose the "simplest" or "minimizing" master representation called $\iota^* \in I(\alpha)$

What do we mean by simple or minimal? It is the master representation $\iota^*$ which visits as many "program states" or "configurations" as $\alpha$.

- equivalent cost function
- or
- preserves the complexity and behaviour of $\alpha$

$\iota^* \in I(\alpha) = argmin \iota \in I(\alpha) : cost(\iota)$

- the proof will likely hinge on 2 observations:
-       Any master representation can't magically reduce the complexity
-       It is possible to write a master representation which adds redundant program states

- (e.g., an unnecessary infinite loop)

<br>
<hr>
<br>

Consider some program called $\alpha$

Rewrite $\alpha$ in its simple master (master-iterator) form: $\iota^* \in I(\alpha)$

Suppose that there are $n$ loops in $\iota^*$ and that each loop is written as any of the below:

- $for \ each \ x_i \ in \ \{ x_{i1} \ x_{i2} \ ... \ x_{ik_i} \}$
- $i$ indexes one of the $n$ loops

- $for \ each \ x_i \ in \ \{ x_{1} \ x_{2} \ ... \ x_{k} \}_i$

- a simplified expression of the above

- $X^i = \{ x_1 \ x_2 \ ... \ x_k \}_i$

-       a loop can be written like a vector

index a particular element as $X^i_j$ which gives the j-th element of the i-th loop vector

A few interesting properties emerge when inspecting $\iota^*$:

- the cost of the algorithm has the simple form of an $n$-chain multiplicate: $\prod^n_{i=1} k_i$

- the set of configurations or program states of $\iota^*$, or any valid $\iota$, is equal to: $CFGN(\iota) = X^1 \times X^2 \times \dots \times X^n$

-       Equivalent to the problem-solution search space

- $\iota^*$ induces a geometry or vector $n$-space called the **vector-iterator space** over the (discrete) spanning vector set: $\{ X^i \}^n_{i=1}$

Now we have represented an algorithm as a vector space denoted as the composition: $CFGN(I(\alpha))$ or $CFGN(\iota^*)$

We can call the $n$-dimensional vector space of the simple master-iterator space: $\chi$

- where $CFGN(\iota^*) \in \chi$
-       configuration set interpretation
- Or
- $CFGN(\iota^*) \subset \chi$
-       geometric vector subspace interpretation

**_WARNING: the definition and notion of $\chi$ has changed in a later revision_**

This is the **geometric representation** of the algorithm $\alpha$

<br>
<hr>
<br>

Interestingly, it may be possible to interpret the geometric representation in 2 separate ways:

1. Continuous $CFGN(\iota^*) \in \chi$

- Configurations or program states correspond to discrete points or shapes (interval ranges) with non-zero volume - connection to point processes and possibly stochastic geometry
- We permit the encapsulating space $\chi$ to be continuous

2. Discrete $CFGN(\iota^*)$

- Discretized view where $CFGN(\iota^*)$ is the encapsulating space itself- loosely equivalent to discretizing the subspace: $CFGN(\iota^*) \ \cap \ \chi$
- the space $CFGN(\iota^*)$ becomes like an n-dimensional lattice or blocky grid where each cell is a concrete configuration

Both geometric interpretations are useful in separate ways.

- it may be useful to think of the discrete representation as a special case of the continuous interpretation.

<br>
<hr>
<br>

**Geometric Consequences of Algorithm Optimization**

Suppose we optimize some algorithm $\alpha$ to get $\alpha'$

- $\alpha'$ may be less asympotatically complex (superior)

**Hypothesis: $|CFGN(I(\alpha'))| < |CFGN(I(\alpha))|$ or $CFGN(I(\alpha')) \subset CFGN(I(\alpha))$**

- the first expression (set) helps give an intuition why the second expression (space) holds
- $\alpha$ is formed by reducing the size of the problem-solution search spaceo of $\alpha$
- Or equivalently,
- The geometric representation of $\alpha'$ is a space that is strictly smaller than the space of $\alpha$. Or more ambitiously: $\alpha'$ induces a strictly smaller subspace contained within the space induced by $\alpha$

<u>Proof sketch/intuition:</u>

The proof of the hypothesis is by algorithm of a technique to be called **Redundancy Pruning** or **Vector Pruning**:

- Consider the (discrete) space or program state set: $CFGN(I(\alpha))$
  - Let $X^1, ..., X^n$ be the spanning loop-vectors of $I(\alpha)$
- Formulate a mathematical equivalence (if any) between any 2 vectors $X^u$ and $X^v$
  - where possibly $u=v$ if $X^u_i$ depends on $X^u_{i-1}$ for instance?
  - could collapse the vector into a singleton
- Discovering a dependency, or equivalently, an equivalence between $X^u$ and $X^v$ allows us to rewrite them as one vector
  - Or again- a smaller or singleton vector if $u=v$
  - Certainly if a loop-vector is written like as an arithmetic or geometric series for example
- This collapses a vector (dimensional collapse) and folds the space into itself
  - Equivalent to finding (linear?) dependence in a spanning vector set (more on this in the matrix representation chapter)

- Notice that the new space is strictly contained within $CFGN(I(\alpha))$
- If we can call this new space $CFGN(I(\alpha'))$ then $CFGN(I(\alpha')) \subset CFGN(I(\alpha))$
  - We should be able to since $I(\alpha')$ returns an equivalent volumetric space for any admissible $\alpha'$
  - Or- map it to an algorithm $\alpha'$ which induces the space $CFGN(I(\alpha'))$ and then show that it is contained in $CFGN(I(\alpha))$ via a technique to be called **Vector Padding**

This hypothesis only holds for when you optimize an algorithm: You chisel out a smaller box from a larger one.

But a structurally distinct algorithm ideally represents a distinct (separate) box (still existing in the same space as the first box)

And- it may be possible to describe "warping" or geometrically transforming one box to another so they become equivalent. I also suspect however, that this is only possible if they have the same number of dimensions (amongst a couple other assumptions borrowed from pure geometry).

<br>
<hr>
<br>

**Vector Padding**

Given any volume $CFGN(I(\alpha))$ we can redundantly expand the space to cover more volume.

- $|CFGN(I(\alpha))| \to |\chi|$
- Augment one or more of the loop-vectors with more (possibly infinite) elements
  - $AUG(X^i) = X^i \ \cup \ \{ z_i \}^\infty_{i=1}$

Even more so, we can expand $\chi$ itself- the only way to do that is by increasing the number of dimension, $n$:

- Augment the spanning vector set itself with redundant loop-vectors
  - $AUG(\{ X^i \}^n_{i=1}) = \{ X^i \}^n_{i=1} \ \cup \ \{ Z^i \}^\infty_{i=1}$

The consequence of this is that $\chi$ is embedded within an $\infty$-dimensional space

- $span(\{ X^i \}^n_{i=1}) \subseteq \chi \subseteq \Upsilon$
  - Where $\Upsilon$ is an $\infty$-dimensional (vector) space
  - Potential connection to a hilbert space?

Note: $CFGN(I(\alpha)) = span(\{ X^i \}^n_{i=1})$

<br><hr><br>

**On the Definition of the Embedding Space $\chi$**

Our spaces are not necessarily numerical- but mathematical objects

- It may be useful to consider $\chi$ as correspondent to the induced space of the most brutally forceful algorithm possible, $\alpha^\chi$

Thus we can preliminarily consider: $\chi = CFGN(I(\alpha^\chi))$ where $I(\alpha^\chi) = argmax \ \forall \alpha \ I(\alpha) : |I(\alpha)| < \infty$

- Where $\alpha^\chi$ is maximally brutal (redundant)
- Or
- _The algorithm $\alpha$ that induces the space with maximum spanning volume (which is also finite?)_

<br><hr><br>

**On Pruning, Optimization, and Redundancy**

$CFGN(\iota) = X^1 \times X^2 \times \dots \times X^n$ is a special space called the **complete space** or **complete box** induced by $\iota$ wrt the spanning loop-vectors

- No holes, tears, or irregular shapes
- Equivalent to a solid $n$-dimensional hyperrectangle or orthotope

**Lemma: Branching in $\alpha$ can be a form of redundant pruning**

- branching allows us to make decisions within a bounded search space traversal (search space being the complete box)
- branching and boxing must be analyzed deeply...

If the master-iterator representation $I(\alpha)$ induces a complete box, then the volume of the induced box equals a function of the worst time of $\alpha$

- In other words, $CFGN(I(\alpha))$ has a deep connection with the complexity analysis of $\alpha$
  - _interesting relationship between geometry and complexity theory_

<br>

$\alpha$ must have what is to be called a **realized space** or **actual space**:

- the realized space of $\alpha$ is the concrete space or geometry that is induced by $\alpha$ depending on the inputs of $\alpha(\{ x^{input}_1, ..., x^{input}_m \})$
- this corresponds to the concrete geometry induced by $\alpha$ as a function of its inputs
- Which is equivalent to a measure or geometry of how much, and what of, the larger configuration search space was realized

**Corollary/Hypothesis: $CFGN(I(\alpha(\{ x^{input}_1, ..., x^{input}_m \}))) \subseteq CFGN(I(\alpha))$**

- All realized spaces of $\alpha$ can never escape the complete box
- And the volume of any realized space is bounded by the volume of the complete box of the master-iterator representation

Note: $\Xi(\alpha) = CFGN(I(\alpha))$

- shorthand notation to denote the induced geometry of an algorithm's master-iterating representation implicitly
- It is now clearer to say: $\Xi(\alpha(\{ x^{input}_1, ..., x^{input}_m \})) \subseteq \Xi(\alpha)$
  - for any concrete input vector or configuration: $\{ x^{input}_1, ..., x^{input}_m \}$

<br><hr><br>

_I think the smallest possible box, denoted as $\Xi(\alpha)_{min}$ might be equivalent to some kind of convex hull\_

- It is the smallest solid box $\Xi(\alpha)$ within the problem's solution search space (minimal redundancy) which includes/contains the solution for all possible program inputs $\{ x^{input}_1, ..., x^{input}_m \}$
  - phenomenon to be called **box-capture**
  - note that the pathological singleton box, which only works for a given realized program input vector, but not any other

But we're muddying the definitions a bit here- I'm defining the embedding space differently. Let's clarify:

- Input space
- Solution space
- Loop-vector space (induced master-iterator space)

**Hypothesis: It may be the case that Solution Space = Induced Loop-Vector Space**

- If we fix the program input size, $m$, to be constant?
- And/or even hold the values of the input(s) to be arbitrary?

There is likely a hidden relationship between these 3 spaces

We can simplify the framework by formulating any algorithm as a search algorithm

- whether its one explicitly or implicitly
- Recall the epiphany I had some years ago

<br><hr><br>

**It may be that we can Define Optimizations, Redundancy, and Big-O notation in the Geometric Representation**

An object $\Xi$ doesn't necessarily encode Big-O of $I(\alpha)$

But rather, it is a measure or representation of the search space induced by $I(\alpha)$.

- Any solution in $\Xi$ is considered- we box capture the desired solution

Im sure there's a hidden relationship between $\Xi$ and Big-O

- I'm almost certain that $\Xi$ encodes the Big-O complexity of the algorithm

Let the spanning loop vectors of some $\Xi$ be $\{ X^i \}^n_{i=1}$

- Deduce the complexity of each loop-vector e.g., O(n), O(logn), etc.
- For some loop vector $X^i$ let $T(X^i)$ be its cost function

Then the complexity of $I(\alpha)$ is denoted as: $\prod^n_{i=1} O(T(X^i))$

_Limitation: this does not account for branching- which we briefly considered earlier... Can we express branching as a loop vector?_

<br><hr><br>

**Revisiting: Branching as a Loop Vector**

The most primitive form of branching is a true vs not true branch (if/else).

The loop vector is written in set notation (like a sequence) which we can utilize.

- let the branching condition be called $p$

We interpret vectors as sets equivalently, and vice-versa

- Note that sets and vectors can be recursively defined...

One possible representation of a branching loop-vector is as follows:

- Let $S$ contain all possible distinct loop vectors (while being agnostic about input size and possibly values)

We are interested in the subset of loop vectors of largest cardinality

- Let the max cardinality be noted as m'

If we are permitted to be agnostic to values (which im pretty sure we can) then we construct the branching loop vector as a vector of cardinality m'.

Equivalent to taking any one of the largest sets:

- $X = \{ Y \ if \ p \ otherwise \ Z \}$
  - where $Y$ and $Z$ are also loop vectors

<hr>

It is easy to see that branching can poke holes or tear the box $\Xi$

- as a matter of fact, I suspect you can approximate any (nonlinear) shape with branching
  - Take some box $\Xi$
  - Write conditional loop vectors in such a way that you sculpt a butterfly out of $\Xi$
    - Prove the framework. We can draw this in MATLAB.

This, however, should be worked on more. This is a difficult problem. It typically won't be enough to simply define the branching loop vector as any one of the largest ones.

- The box $\Xi$ might start becoming nonsensical since the branch loop vector could hold any $m'$ elements

<br><hr><br>

**Singleton Loop Vector**

O(1) work in the search space can be represented as a singleton loop vector

- i.e.,
  - instead of: $let \ x \gets \infty$
  - rewrite as: $X^i \gets \{ \infty \}$
  - or equivalently: $for \ each \ x_i \ in \ \{\infty\}_i$
- The consequences of this discovered formulation is nontypical

This is important since variables are still axes or iterators of a configuration space.

- Its just a trivial axis of a configuration or state search space of only 1 element
- Note that it does not increase the volume of the space induced by $\alpha$ as per product rule

<br><hr><br>

Follow ups:

Proving a lot of these hypotheses require a more rigorous definition of a loop vector itself

- requires rigorous work and clear definitions of the master-iterator representation
- rigorous definitions of the various spaces
- rigorous loop vector definitions, especially branching loop vectors
- Need to figure out how to cleanly translate arbitrary while loops into loop vectors...
  - should actually be easier to do than branching loop vectors

As we work through to the nonlinear cases, keep in mind:

- branching is likely a form of nonlinearity (nuanced but generally nonlinear in nature)
- it might be worth exploring once we begin integrating nonlinear dependencies in the spanning set
