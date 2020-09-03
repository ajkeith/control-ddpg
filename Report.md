# Deep Deterministic Policy Gradient: Continuous Control

This report describes the implemenation of a deep deterministic policy gradient (DDPG) to solve the reacher continuous control problem.

## Learning Algorithm

This problem is solved using a deep deterministic policy gradient approach. This is a an actor critic method that uses an actor neural network and a critic network to approximate the optimal value function and policy. 

The actor neural network architecture consists of two 256-node linear hidden layers with batch normalization in between and with ReLU (rectified linear unit) and tanh activation functions. 

The critic neural network architecure consists of two 256-node linear hidden layers (plus action nodes on the second), followed by batch normalization, followed by a 256-node linear hidden layer, followed by a 128-node hidden layer. This network uses leaky ReLU activation functions to prevent plateaus in learning. 

The overall hyperparameters are:
- Replay buffer size: 1e6
- Minibatch size: 128
- Discount factor: 0.99
- Soft update factor: 1e-3
- Initial noise epsilon: 1.0
- Noise decay: 0.9995
- Minimum noise: 0.01
- Network update frequency: 2

The training hyperparameters are:
- Max training of episodes: 1000
- Max timesteps per episode: 1000

These parameters were chosen based on trial and error and based on discussion and code in the Udacity [mentor chat](https://knowledge.udacity.com/questions/277763) from [Dmitry G](https://github.com/dimaga/drlnd-p2-continuous-control/tree/fb74f243bf83818da2cf81843006737ca3ce8388). Default ADAM parameters are used. The reacher environment was sensitive to parameter selection and I think having the more robust neural network models for the actor and critic was a key change in code that allowed it to learn 20 times faster or more, in terms of episodes.  

## Results

This implementation solved the problem by achieving an average reward of at least +30 over 100 episodes in less than 200 total episodes. The full results are shown below. The saved weights are available for the [actor](./checkpoint_actor.pth) and the [critic](./checkpoint_critic.pth). 

![Results](./results/score.png)

## Future Work

The agent's performance could be improved by implementing various alternative algorithms like PPO, A3C, or D4PG. It would also be feasible to step down the size of the actor and critic neural networks to find a more efficient DDPG implementation. 
