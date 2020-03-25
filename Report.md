# Project Report

## Learning Algorithm 
Deep Deterministic Policy Gradient(DDPG) algorithm uses four neural networks: a Q network, a deterministic policy network, a target Q network, and a target policy network to solve continuous control problem. And Multi Agent Deep Deterministic Policy Gradient(MADDPG) is a variant of DDPG used in multiagent environment.

<div align="center"><img width="600" height="400" src="https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/screenshot.png"/></div>

(screenshot from [the paper](https://arxiv.org/abs/1706.02275))

> we accomplish our goal by adopting the framework of centralized training with decentralized execution. Thus, we allow the policies to use extra information to ease training, so long as this information is not used at test time. It is unnatural to do this with Q-learning, as the Q function generally cannot contain different information at training and test time. Thus, we propose a simple extension of actor-critic policy gradient methods where the critic is augmented with extra information about the policies of other agents.

In brief, the agents do not need to access the central critic during the test; they will act based on their own observations and predictions of other agents' behavior. Since centralized critics can be learned independently for each agent, MADDPG can also be used to model arbitrary reward structures between agents, including adversarial cases.

### Hyperparameters
```
```
The actor neural networks use the following architecture:
```
```
The critic neural networks use the following architecture:
```
```

### Pseudocode
![MMDDPG Pseudocode](https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/Pseudocode.png)
This MADDPG Pseudocode screenshot is taken from [the paper](https://arxiv.org/abs/1706.02275)

## Plot of Rewards

As my trained multiagent shown below, two tennis racket collaborate to hit the ball over the net and keep it in play
![My Trained Agent](https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/trained_agent.gif)

## Ideas for Future Work
- Try to solve a more difficult soccer environment, where the goal is to train a small team of agents to play soccer.
- Get a deep-in understand about OU-noise, which help to improve the convergence speed in this project.
