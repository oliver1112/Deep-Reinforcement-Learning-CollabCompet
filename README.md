# Deep-Reinforcement-Learning-CollabCompet
My solution to Udacity Deep Reinforcement Learning Nanodegree 's Project 3 - Collab Compet

## Environment Details
In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping. 

### Solving condition
The mission is episodic. In order to solve the environment, your agent must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents).

## Instructions
This project implement a multi-agent reinforcement learning method called Multi Agent Deep Deterministic Policy Gradient (MADDPG). DDPG is an Actor-Critic algorithm which concurrently learns a Q-function and a policy. And MADDPG expands DDPG algorithm in multiagent environments for centralized learning and decentralized execution, allowing agents to learn to collaborate and compete with each other. Refer the paper [Multi-Agent Actor-Critic for Mixed Cooperative-Competitive Environments](https://arxiv.org/abs/1706.02275) or [the openAI blog](https://openai.com/blog/learning-to-cooperate-compete-and-communicate) to see more MADDPG algrithm details.
<div align="center"><img width="600" height="400" src="https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/screenshot.png"/></div>

This screenshot is taken from the OpenAI blog.

And refer the Report file to see my hyperparameters details, along with ideas for future work.

Follow the code in the ipynb file in order to train the agent.

The algorithm is written in PyTorch and Python 3

## Getting Started
To set up your python environment to run the code in this repository, follow the instructions below.


1. please follow the instructions in the python file to set up your Python environment. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.
```bash
pip install .
```


2. The environment is based on [Unity ML-agents](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis). The project environment provided by Udacity is similar to the Tennis environment on the Unity ML-Agents GitHub page.
> The Unity Machine Learning Agents Toolkit (ML-Agents) is an open-source Unity plugin that enables games and simulations to serve as environments for training intelligent agents. Agents can be trained using reinforcement learning, imitation learning, neuroevolution, or other machine learning methods through a simple-to-use Python API. 

I use the Windows (64-bit) operating system, [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip) to install the banana game environment. And unzip (or decompress) the file in the folder.
For other operating system, please download the environment from one of the links below.
- Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
- Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
- Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)


3. Follow the instructions in `Tennis.ipynb` to see my code!  
