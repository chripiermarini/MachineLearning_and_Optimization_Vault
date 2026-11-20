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

In this folder we will focus on the class of convex optimization. Convex optimization problems benefit from the fact that both objective functions and constraints benefit from a specific 