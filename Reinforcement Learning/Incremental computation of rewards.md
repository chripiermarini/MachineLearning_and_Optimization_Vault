Tags: #reinforcement-learning #first-chapter

Given a current value of performance 

$$ 
Q_{t-1} = \frac{R_1 + R_2 + \dots + R_{t-1}}{n-1}
$$
and the new reward $R_t$ at time $t$, computing the sum and then the average at each time step might be computationally expensive in terms of requirements. 

Hence, a simple idea would be to use the latest value of the performance in $t-1$ and then add incrementally the new value, using the following formula:

$$
Q_t = \frac{1}{n}\sum_{t=1}^{n} R_t = Q_{t-1} + \frac{1}{n-1}[R_{n-1} - Q_{n-1}].
$$

The general form of the above formula would be the following:

NewEstimate = OldEstimate + StepSize(Target - OldEstimate),

where the term (Target - OldEstimate) is the *error* in the prior estimate. 