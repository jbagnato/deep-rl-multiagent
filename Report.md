# Project 3 Report: Collaboration and Competition

## Introduction

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

![Trained RL Agent](https://github.com/jbagnato/deep-rl-multiagent/blob/main/p3_collab_compet.gif)

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

## Learning Algorithm

I used MADDPG Algorithm to solve the excercise. 

I took a previous code from "Physical Deception" problem and modified it to make it work on this new environment.

To solve the problem I made some modifications on code:

* Episode Max length was gradually incremented over time and limit to 150.000
* Add Noise parameter set to False
* Neural Networks with layers of 200 and 100 hidden units.
* Agent learn method (with soft update) called every 7 steps.
* Actor and critic Learning rates of 1e-3 and 1e-4

After all those modifications and testing in CPU and GPU environments I could reach AVG of +30.0 (over last 100 episodes) after 563 episodes.

### MADDPG Algorithm

Multi Agent Deep Deterministic Policy Gradient (MADDPG) is an algorithm which concurrently learns a Q-function and a policy. It uses off-policy data and the Bellman equation to learn the Q-function, and uses the Q-function to learn the policy.

- DDPG is an off-policy algorithm.
- DDPG can only be used for environments with continuous action spaces.
- DDPG can be thought of as being deep Q-learning for continuous action spaces.
- The Spinning Up implementation of DDPG does not support parallelization.

### Hyperparameters

The hyperparameters used were:

```xml
BUFFER_SIZE = int(1e5)  # replay buffer size
BATCH_SIZE = 128        # minibatch size
GAMMA = 0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR_ACTOR = 1e-3         # learning rate of the actor
LR_CRITIC = 1e-4        # learning rate of the critic
WEIGHT_DECAY = 0        # L2 weight decay
```


### Neural Networks

There were used 2 NN for Actor and Critic models. The architecture used was the same:

#### Actor NN

- Hidden: (input, 200) - ReLU
- Hidden: (200, 100) - ReLU
- Output: (100, 4) - TanH

#### Critic NN

- Hidden: (input, 200) - ReLU
- Hidden: (200 + action_size, 100) - ReLU
- Output: (100, 1) - Linear


## Plot of Rewards

To solve the problem, the agent receives an average reward (over 100 episodes) of at least +30:

```xml
0 episode	avg score over 100 episodes 0.10000	 (max 0.10000)
100 episode	avg score over 100 episodes 0.01640	 (max 0.00000)
200 episode	avg score over 100 episodes 0.01370	 (max 0.00000)
300 episode	avg score over 100 episodes 0.01820	 (max 0.00000)
400 episode	avg score over 100 episodes 0.01850	 (max 0.00000)
500 episode	avg score over 100 episodes 0.00000	 (max 0.00000)
600 episode	avg score over 100 episodes 0.01940	 (max 0.10000)
700 episode	avg score over 100 episodes 0.07040	 (max 0.09000)
800 episode	avg score over 100 episodes 0.08650	 (max 0.10000)
900 episode	avg score over 100 episodes 0.10820	 (max 0.10000)
1000 episode	avg score over 100 episodes 0.16830	 (max 0.20000)
1100 episode	avg score over 100 episodes 0.31460	 (max 0.29000)
1151 episode	avg score over 100 episodes 0.50940	 (max 1.80000)
Environment solved after 1151 episodes with the average score 0.5094000076502562
```

Rewards plot image:

![Rewards Plot](https://github.com/jbagnato/deep-rl-multiagent/blob/main/p3_score.png)


## Ideas for future Work

On future work It would be great to use other RL models like:

* D4PG
* Try on the Version 2 Agent with 20 arms envornment.
* Try the Crawler optional excercise.


