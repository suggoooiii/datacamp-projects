![My Image](images/Q-Learning.png)

# Steps to solve

1. We set up the Taxi-v3 environment and initialize our Q-learning parameters.
2. We create a Q-table to store the action-values for each state-action pair.
3. We train the agent for a specified number of episodes using the Q-learning algorithm. During training, the agent balances exploration (random actions) and exploitation (choosing the best-known action) using an epsilon-greedy strategy.
4. After training, we evaluate the agent's performance by running it for 100 episodes and calculating the average reward.
5. Finally, we visualize a single episode of the trained agent's performance, saving it as a GIF.

## To further improve the agent's performance, you could

1. Experiment with different hyperparameters (*__alpha__*, *__gamma__*, *__epsilon__*).
2. Implement a decaying epsilon value to reduce exploration over time.
3. Try more advanced reinforcement learning algorithms like **_SARSA_** or **_Deep Q-Networks_**.
4. Increase the number of training episodes or implement early stopping based on performance.

`new_value = (1 - alpha) *old_value + alpha* (reward + gamma * next_max)
`

This equation is derived from the *Q-learning update rule*, which aims to estimate the optimal action-value function. Here's what each component means:

1. __old_value__: This is the current Q-value for the state-action pair (s, a) that we're updating.
2. __alpha__: This is the learning rate (0 < α ≤ 1). It determines how much we update our Q-value based on new information.
3. __reward__: This is the immediate reward received after taking action 'a' in state 's'.
4. __gamma__: This is the discount factor (0 ≤ γ ≤ 1). It determines the importance of future rewards. A value close to 0 makes the agent "myopic" by only considering current rewards, while a value close to 1 makes it strive for long-term high rewards.
5. __next_max__: This is the maximum Q-value for the next state. It represents our estimate of the optimal future value.
The calculation can be interpreted as follows:

6. __(1 - alpha) * old_value__: This part keeps a portion of the old Q-value.
7. __alpha *(reward + gamma* next_max)__: This part updates the Q-value with new information.
    - __reward__: The immediate reward.
    - __gamma * next_max__: The discounted estimate of optimal future value.
The Q-learning algorithm combines these to create a new estimate that balances the old information with the new information we've just obtained from taking an action and observing its result.
This update rule allows the agent to learn from its experiences, gradually improving its estimates of the value of each action in each state. Over many iterations, these Q-values should converge to the optimal values, allowing the agent to make better decisions.
