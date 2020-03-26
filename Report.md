# Project Report

## Learning Algorithm 
Deep Deterministic Policy Gradient(DDPG) algorithm uses four neural networks: a Q network, a deterministic policy network, a target Q network, and a target policy network to solve continuous control problem. And Multi Agent Deep Deterministic Policy Gradient(MADDPG) is a variant of DDPG used in multiagent environment.

<div align="center"><img width="600" height="400" src="https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/screenshot.png"/></div>

(screenshot from [the paper](https://arxiv.org/abs/1706.02275))

> we accomplish our goal by adopting the framework of centralized training with decentralized execution. Thus, we allow the policies to use extra information to ease training, so long as this information is not used at test time. It is unnatural to do this with Q-learning, as the Q function generally cannot contain different information at training and test time. Thus, we propose a simple extension of actor-critic policy gradient methods where the critic is augmented with extra information about the policies of other agents.

In brief, the agents do not need to access the central critic during the test; they will act based on their own observations and predictions of other agents' behavior. Since centralized critics can be learned independently for each agent, MADDPG can also be used to model arbitrary reward structures between agents, including adversarial cases.

### Hyperparameters
```
action_size=2
n_agents=2
buffer_size=10000
batch_size=256
gamma=0.99
lr_actor=1e-4
lr_critic=1e-3
tau=1e-3
update_every=2
mu=0                     #OU-noise parameter
theta=0.15               #OU-noise parameter
sigma=0.1                #OU-noise parameter
```
Two agents trained with the same size network, and the experience was added to a shared replay buffer. The actor neural networks use the following architecture:
```
ActorModel(
  (fc1): Linear(in_features=24, out_features=256, bias=True)
  (fc2): Linear(in_features=256, out_features=128, bias=True)
  (fc3): Linear(in_features=128, out_features=2, bias=True)
  (bn): BatchNorm1d(256, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)
)
```
The critic neural networks use the following architecture:
```
CriticModel(
  (fc1): Linear(in_features=52, out_features=256, bias=True)
  (fc2): Linear(in_features=256, out_features=128, bias=True)
  (fc3): Linear(in_features=128, out_features=1, bias=True)
  (bn1): BatchNorm1d(256, eps=1e-05, momentum=0.1, affine=True, track_running_stats=True)
)
```

### Pseudocode
![MMDDPG Pseudocode](https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/Pseudocode.png)
This MADDPG Pseudocode screenshot is taken from [the paper](https://arxiv.org/abs/1706.02275)

## Plot of Rewards
The Environment solved in 2863 episodes, which means it receive an average reward (over 100 episodes) of at least 0.5

The reward changes with the number of episode as shown below, the blue line is the score change with episode, while the orange one is the average score. 
![](https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/score.png)

As my trained multiagent shown below, two tennis racket collaborate to hit the ball over the net and keep it in play
![My Trained Agent](https://github.com/oliver1112/Deep-Reinforcement-Learning-CollabCompet/blob/master/assets/trained_agent.gif)

## Ideas for Future Work
- Try to solve a more difficult soccer environment, where the goal is to train a small team of agents to play soccer.
- Get a deep-in understand about OU-noise, which help to improve the convergence speed in this project.
