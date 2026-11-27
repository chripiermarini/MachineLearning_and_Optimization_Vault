Tags:
- #reinforcement-learning 
Possibly the simplest method to decide which action to take, an action-value method requires to  compute the *average of the rewards* obtained prior to the specific time step $t$.

Hence, a mathematical formulation of this would be

$$
Q_*(a) = \frac{\sum_{i=0}^{t-1}\mathbb{1}_{A_i = a}R_i}{\sum_{i=0}^{t-1} \mathbb{1}_i}
$$
