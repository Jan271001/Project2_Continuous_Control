# Report

## The result

![Plot of rewards](Continuous_Control_Performace.png)

The agent was able to solve the environment in 100 episodes. After 16 episodes the mean score over all twenty agents reaches +30 for one episode and follow this line till the end. The mean score over all episodes reaches +30 in episode 46. This gets a valid solution for this project in episode 100. After all 300 episodes the mean score over 100 consecutive episodes has reached a value above 38. In detail: 38.10474414829258. 

## The algorithm

For this project I used the DDPG-Algorithm (Deep Deterministic Policy Gradient). I operate with two four layer feed-forward neural networks. One for the actor and one for the critic. The actor-network consists of 33 input nodes, 400 nodes in the first hidden layer, 300 in the second one and 4 output nodes which represent the four actions the agent can take. The output value of each node in the outputlayer represents the continuous value for the action. The input layer is designed to obtain an input vector with 33 dimensions representing the current state of the environment. The evaluation of the actions takes part in the critic-network. This network has nearly the same architecture as the actor-network but has only one output node and receive next to the state of the environment additional the action the agent takes. Using this information it calculates the Q-value of this state-action-pair. In order to explore the environment i added a noise function following the *Ornstein-Uhlenbeck process*. Also I use a Noise decay to reduce the randomness with time. To prioritize the current reward higher then the expected one of the following time steps I operate with a discount rate of 0.99. To guarantee the repeatability I applied a random seed of 0. The algorithm uses two main optimisations of the Deep
-Q-Learning. At the one hand there is a Replay-Buffer and on the other hand it uses target-networks to stabalize learning. One target network for the critic and one for the actor. To update the target networks a soft update function is used. DDPG is an off-policy algorithm. This means it uses a different policy to update the weights then it uses to interact with the environment. In my solution there are twenty agents interacting parallel with the environment, all of them collect information which get stored in the replay-buffer. Every 20 timesteps the networks gets updatet using 10 samples of the replay-buffer. Because of the usage of two different networks there
are also two different ways to update each one of them. On the one hand the actor is updatet much like in the Deep-Q-Learning algorithm I used and explained in the first project of this nanodegree. However, here the Q-value to update the network-weights is calculated using the target-critic-network. In equations this looks like this:

![grafik](https://user-images.githubusercontent.com/78097127/119993730-2cc0d280-bfcc-11eb-8775-66d74ddf0689.png)

![grafik](https://user-images.githubusercontent.com/78097127/119993767-39452b00-bfcc-11eb-9f08-ba2c006e3058.png)

Its important to mention, that only the target networks get updatet directly. The online networks get slowly ubdatet by using a soft update function. On the other hand the critic gets updatet using samples of replay-buffer (same by actor) here the actor generates an action and the critic has to evaluat this action by calculating the Q-value of this action. The needed loss for the backpropagation for this network is calculated by using the target network of the critic to generate a Q-value as well as the reseived reward for this action. 

