# Collaboration and Competition Project

## Udacity Deep Reinforcement Learning - Nanodegree Program

Exercise for MultiAgent Deep Reinforcement Learning on Udacity Nanodegree

![Trained RL Agent](https://github.com/jbagnato/deep-rl-multiagent/blob/main/p3_collab_compet.gif)


In this Repo you will find my solution to 3rd Project of Deep Reinforcement Learning, Udacity Nanodegree called "Collaboration and Competition".

I will be training the First Version that consist of a SINGLE agent.

## Project Details

In this environment, a double-jointed arm can move to target locations. 
A reward of +0.1 is provided for each step that the agent's hand is in the goal location. 
Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 24 variables corresponding to position, rotation, velocity, and angular velocities of the arm. 
Each action is a vector with four numbers, corresponding to torque applicable to two joints. 
Every entry in the action vector should be a number between -1 and 1.


## Getting Started

To install and use the environment you have to follow these steps:

 1 Install Anaconda Suite and create (and activate) a new python environment
   ```python
   conda create --name drlnd python=3.6
   ```
 2 Install OpenAi gym
   ```python
   pip install gym
   ```
   
 3 Install the Unity Environment App (not Unity SDK!)
 
   Just copy your required os unity environment file on your working directory and decompress.
   
   * Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
   * Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
   * Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
   * Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)
 
 4 Clone this repository and install other dependencies:
   ```python
   pip install ./python
   ```
 5 Run [Tennis.ipynb](https://github.com/jbagnato/deep-rl-multiagent/blob/main/Tennis.ipynb) (Jupyter Notebook) with the working code and watch how it trains a new model and later use it to play alone.
   
## Instructions

To train a new agent, open [Tennis.ipynb](https://github.com/jbagnato/deep-rl-multiagent/blob/main/Tennis.ipynb) Jupyter Notebook file.

Follow the steps described on each cell. 

You will find a MADDPG function that will train until ```np.mean(scores_deque)>=0.5```This means that the average score of the agent is greater than 0.5 over last 100 episodes.

Then it will use saved agent in both files 'checkpoint_actor0.pth' and 'checkpoint_critic0.pth' to run a continuous episode that you can enjoy in realtime :-)

