Tags:
- #reinforcement-learning 
Critical concept is the Value function $V_{\pi}$, which represent, given a state $s$ and a policy $\pi$, what is the expected return obtained by following the policy $\pi$ from state $s$. 

Recalling the definition of the return $G_t$, we can then formalize the value function as follows:

$$
v_{\pi}(s) = \mathbb{E}_{\pi}[G_t | s_t] = \mathbb{E}_{\pi}[ \sum_{k = t+1}^{T} \gamma_{k-t-1} * R_k
| s_t]  
$$

The above version depends only on the current state of the agent, and it is defined *state-value* function. There is another version called *action-value* function, whcih depends on both state and action taken at a certain time $t$.

Value functions are important as they allow to compute a sort of ranking among policies, and they allow to compute the *optimal policies*. 