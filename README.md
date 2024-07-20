# Optimizing Performance in Autonomous Racing Cars Using Deep Q-Learning: A Comparative Study of Reward Systems

## Overview

This repository contains the code and resources for our project on optimizing performance in autonomous racing cars using Deep Q-Learning. The project compares different reward systems to evaluate their impact on the performance of the autonomous racing cars in a custom simulated environment.

## Abstract
The use of Reinforcement Learning is gaining popularity due to its application in
autonomous vehicles. Race cars, in specific can be well trained with the help of
Reinforcement Learning in order to optimize several factors like speed, decision
making, and steering and control. Through this study, the aim is to utilize Deep
Q Learning to optimize the performance of autonomous racing cars. The race
car is trained on a custom built environment and is evaluated based on two
different reward systems. The outcome of the study reveals that the second set
of rewards are more suitable and yield better performance when compared for
10,000 episodes, with the second set of rewards over performing with an average
of 282 units of distance more than the first set of rewards. These findings reveal
that structuring rewards is an important factor and plays a crucial role while
designing Reinforcement Learning systems.

## Proposed Solution
First, the environment is
built using Pygame, a Python module ideal for creating GUI and gaming functionalities. Subsequently, several essential modules necessary for training the agent are
developed. The Deep Q Network module constructs the DQN and defines the layers
and parameters for each layer. The Replay Buffer module creates a buffer that stores
the experience tuple (state, action, reward, next state). The Agent module manages
the agent’s policy, balancing exploration and exploitation through the epsilon-greedy
strategy. The Environment module sets up the environment, creates the track and
checkpoints, and provides an interface for the agent to interact with
![image](https://github.com/user-attachments/assets/f1915be2-f216-413c-a35e-476b7e51dd56)

# RL Formulation

The RL formulation provides a structured way to define and analyze RL problems, facilitating the development of algorithms and strategies for solving them. The following is a description of the formulation used in this particular study.

## 1. State Space
\[ S : \{(x, y), \theta, \cos(\theta), \sin(\theta), d, i\} \]

Where:
- \((x, y)\) is the agent position
- \(\theta\) is the car angle
- \(\cos(\theta)\) is the cosine of the car angle
- \(\sin(\theta)\) is the sine of the car angle
- \(d\) is the distance traveled
- \(i\) is the current checkpoint index

## 2. Action Space
\[ A : \{\text{Forward, Forward and Left, Forward and Right}\} \]

## 3. Reward Space
The race car’s performance will be assessed using two distinct sets of rewards. The details of the two reward sets are as follows:

### (a) First set of rewards \(R_1\) :
\[ R_1(s, a) = \begin{cases}
\text{Step Reward} = -1 \\
\text{Reward for crossing checkpoints} = 100 \times 2 \text{ subsequent checkpoints} \\
\text{Penalty for going off-track} = -100 \\
\text{Penalty for backtracking} = -50 \\
\text{Reward for reaching the goal} = +1000
\end{cases} \]

### (b) Second set of rewards \(R_2\) :
\[ R_2(s, a) = \begin{cases}
\text{Step Reward} = +1 \\
\text{Reward for crossing checkpoints} = 100 \times 2 \text{ subsequent checkpoints} \\
\text{Penalty for going off-track} = -100 \\
\text{Penalty for backtracking} = -50 \\
\text{Reward for reaching the goal} = +1000
\end{cases} \]
## Environment
The Pygame environment is set against an expansive 800x600 pixel green backdrop,
featuring a sleek black elliptical track with a generous width of 60 pixels. Encircling
an inner sanctum with a radius of 200 pixels and an outer boundary stretching to
260 pixels, the track offers a challenging course for the red race car, measuring 50x25
pixels. The 15-pixel-wide start line spans the track’s width at its midpoint, marking the
beginning of each race. Along the track, ten equidistant white dots act as checkpoints,
guiding the car’s path and adding strategic depth to the thrilling simulation of speed
and precision.
![image](https://github.com/user-attachments/assets/6ad4f471-2f59-4814-93db-c8d43e54ccbe)


- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Reward Systems](#reward-systems)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

The goal of this project is to develop and train autonomous racing cars using Deep Q-Learning (DQN) and
