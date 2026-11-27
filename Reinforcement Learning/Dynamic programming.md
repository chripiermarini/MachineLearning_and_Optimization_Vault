Family of algorithms which are of limited use in practical scenarios as they assume deterministic and perfect model. Still, they provide a strong foundation for understanding many of the real algorithms use to compute optimal agent policies. 

Usually, RL algorithms actually focus on alternating two steps: the first one being *policy evaluation* and the second one *policy improvement*.

# Policy evaluation

Policy evaluation entails computing the performance of the policy in terms of value function within the environment. We use the Bellman's equations to compute value function at each possible state $s_t$, by using the recursive formula:

$$
v_{\pi}(s_t) = \sum_{a_t}\pi(a_t|s_t) \left[ r(a_t, s_t) + \gamma \sum_{s_{t+1}}Pr(s_{t+1}| a_t, s_t) v_{\pi}(s_{t+1})\right]
$$
This is a recursive formula that needs to use each possible future state in order to compute the value function at the current state.

**Caveat:** how do we compute these values? 

States in an environment might not be sequential, it might be possible that multiple states in different ways. In the example of the GridWorld, multiple cells can be reached by all the adjacent cells. 

How do we solve such problem? When defining the multiple equations, we create a system of linear equations, where we have the *non-terminal* states as variables.. There are two ways to solve it:

1) We solve the system of linear equations directly, using the *elimination* method. 
2) We compute the solution *iteratively*, like Jacobi or Gauss-Seidel. 