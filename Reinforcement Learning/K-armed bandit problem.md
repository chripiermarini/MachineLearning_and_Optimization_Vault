Tags: #reinforcement-learning

The *k-armed bandit problem* is a specific instance of a reinforcement learning problem which it is *nonassociative*, meaning it does not involve learning to act in more than one situation. This example is self-explanatory and greatly simplifies the complexity of the general RL problem, and that is why it is usually explained as a pedagocical example. 

In an k-armed bandit problem, the user is faced by the decision of pulling one among *k* levers to play a game, and the objective is to maximise the overall reward after a specific number of plays. Let's assume that each action at time *t* is $A_t$, and the corresponding reward is $R_t$. Then, the value of the action is basically the following:

$$
q_*(a) = \mathbb{E}(R_t| A_t = a).
$$
Hence it is the expected value of the reward taken given a specific action $a$. This problem is simpler as we do not have any state: there is only one, and at each step we just have to pull the lever that maximises the reward.

Related topics:

- [[Action-value method]]