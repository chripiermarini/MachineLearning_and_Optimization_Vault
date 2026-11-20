Tags:
- #optimization
- #convex-optimization
A mathematical optimization problem has the usual form:

$$
\begin{aligned}
&\min &f(x) & \\
& s.t. &f_i(x) \leq b_i, \quad & i= 1, \dots m.
\end{aligned}
$$
We will skip from now on the classical terms on *objective functions*, *constraints* and *variables*.

If $f(x)$ satisfy the following rule:

$$
f(\alpha x + \beta y) = \alpha f(x) + \beta f(y)
$$
then the function is defined *linear*. ***Nonlinear otherwise***.

In this folder we will focus on the class of convex optimization. In *convex optimization problems*,  both objective functions and constraints benefit from a specific property, being the following

$$
f(\alpha x + \beta y) \leq \alpha f(x) + \beta f(y)
$$

where we have $\alpha, \beta \geq 0, \alpha + \beta = 1, x,y \in \mathbb{R}^{n}$. Of course, recall that this property refers to nonlinear functions, as linear functions (being both *concave* and *convex*) satisfy this property at the equality. 

[[The least-squares problem]] and the linear programming problem are both special cases of the general convex optimization problem.