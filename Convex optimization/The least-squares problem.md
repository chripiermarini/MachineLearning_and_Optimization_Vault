Tags:
- #convex-optimization 
- #convex-model

The *least-squares* problem is widely known and used formulation that entails to compute the value of $x$ that minimizes the following quantity:

$$
\min \quad  \lVert Ax -b \lVert^2_2 = \sum_{i = 1}^{k}(a_i^Tx -b)^2 
$$
where we have $A \in \mathbb{R}^{n \times k}$ , and we have k > n. $x \in \mathbb{R}^n$ and also $a_i^T$ are the rows of the matrix A. The problem, in its 

The least-squares problem has a closed form solution: if $f = \lVert Ax -b \lVert^2_2$ , then 

$$
\nabla f = (A^TA)x - A^Tb
$$
which means that $x = (A^TA)^{-1}A^Tb$ is a solution of our problem. 