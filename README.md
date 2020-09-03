# Deep Deterministic Policy Gradient: Continuous Control
Deep Deterministic Policy Gradient Actor-Critic method for solving the continuous control reacher problem.

## Project Details

The continuous control reacher environment is a Unity environment that consists of a double-jointed arm that can move to target locations. The goal is to keep the agents hand in the target area for as long as possible. 

- State space: 33 dimensions corresponding to position, rotation, velocity, and angular velocities of the arm.
- Action space: 4 dimensions corresponding to torque applicable to two joints (each with value in [-1,1]).
- Rewards: +0.1 is provided for each step that the agent's hand is in the goal location.
  
The environment is considered solved when the agents achieve an average reward of +30 (over 100 consecutive episodes, and over all agents)

The code in this project is based heavily off the code from the Udacity Deep Reinforcement Learning ddpg-bipedal [code](https://github.com/udacity/deep-reinforcement-learning/tree/master/ddpg-bipedal) and tuned based on discussion and code in the Udacity [mentor chat](https://knowledge.udacity.com/questions/277763) from Dmitry G.

## Getting Started

Follow the instructions at the Udacity [Deep Reinforcement Learning](https://github.com/udacity/deep-reinforcement-learning) repository for general instructions on setting up the environment. Specific instructions for installing and downloading required files for this project are at located in [Project 2](https://github.com/udacity/deep-reinforcement-learning/tree/master/p2_continuous-control). 

## Instructions

Run `control-ddpg/control.ipynb` to train the 20-agent model and visualize the scores over time. The logic for the agent and neural network are in `control-ddpg/ddpg_agent.py` and `control-ddpg/model.py`, respectively. The model weights for the successful agent are saved in `control-ddpg/checkpoint_actor.pth` and `control-ddpg/checkpoint_critic.pth`. Note that there is an alternative approach for the single agent model in the files appended `_vanilla`.


