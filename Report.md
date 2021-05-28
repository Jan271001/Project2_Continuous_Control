# Report

## The result

![Plot of rewards](Continuous_Control_Performace.png)

The agent was able to solve the environment in 100 episodes. After 16 episodes the mean score over all twenty agents reaches +30 for one episode and follow this line till the end. The mean score over all episodes reaches +30 in episode 46. This gets a valid solution for this project in episode 100. After all 300 episodes the mean score over 100 consecutive episodes has reached a value above 38. In detail: 38.10474414829258. 

## The algorithm

For this project I used the DDPG-Algorithm (Deep Deterministic Policy Gradient). I operate with two four layer feed-forward neural networks with 33 input nodes, 400 nodes in the first hidden layer, 300 in the second one and 4 output nodes which represent the four actions the agent can take. The input layer is designed to obtain an input vector with 33 dimensions representing the current state of the environment. In order to explore the environment i added a noise function following the *Ornstein-Uhlenbeck process*. Additionaly I added a noice_decay to reduce the randomness with time. To prioritize the current reward higher then the expected one of the following time steps I operate with a discount rate of 0.99. To guarantee the repeatability I applied a random seed of 0. The actor-network is used to generate the action the agent will take, whereas the critic-network is used to get the optimal value for this action. The algorithm is trained with target-networks. There is one for the critic and one for the actor. To update the target networks a soft update function is used. While training there are twenty agents interacting parallel with the environment, all of them collect usefull information which is used to train the networks and will be stored in the replay-buffer. The latter is used to update the networks in an off-policy manner. Every 20 timesteps the network gets updatet using ten samples of the replay-buffer. For this task FNNs build the best working approach.
