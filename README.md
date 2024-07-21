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

<div align="center">
  <img src="https://github.com/user-attachments/assets/f1915be2-f216-413c-a35e-476b7e51dd56" alt="Environment Image">
</div>

## Environment
The Pygame environment is set against an expansive 800x600 pixel green backdrop,
featuring a sleek black elliptical track with a generous width of 60 pixels. Encircling
an inner sanctum with a radius of 200 pixels and an outer boundary stretching to
260 pixels, the track offers a challenging course for the red race car, measuring 50x25
pixels. The 15-pixel-wide start line spans the track’s width at its midpoint, marking the
beginning of each race. Along the track, ten equidistant white dots act as checkpoints,
guiding the car’s path and adding strategic depth to the thrilling simulation of speed
and precision.

<div align="center">
  <img src="https://github.com/user-attachments/assets/6ad4f471-2f59-4814-93db-c8d43e54ccbe" alt="Track Image">
</div>

## Deep Q Network
The DQN design starts with an input layer handling a state space of 6, followed
by two dense layers using the Rectified Linear Unit (ReLU) activation function to
introduce non-linearity and mitigate the vanishing gradient problem. These layers
capture complex patterns in the data. The output layer, with three neurons and a
linear activation function, corresponds to the agent’s possible actions, producing Q-values representing predicted future rewards. The model includes a 10,000-unit replay
buffer, processing batches of 64 samples during training. Key hyper-parameters are
an initial epsilon of 1.0 for exploration, decaying to 0.01 with a factor of 0.995 per
episode, and a discount factor (gamma) of 0.99 to weigh future rewards. Each episode
can last up to 1,000 steps or ends if the agent (race car) leaves the track.

## Results and Analysis
The agent(race car) has been trained on two sets of rewards. After training the agent
for 10,000 episodes on both the sets of rewards, it was observed that the agent performed better on the second set of rewards. The graph depicts a plot for
the episodes (plotted on the x-axis) versus average distance (plotted on the y-axis)
travelled by the agent for both R1(-1 reward) and R2(+1 reward) sampled for every 500 episodes. R1 is plotted using a dashed red line and R2 using a solid blue line. It can be observed from this plot that R2 works better and the agent is able to learn and travel better distances
than R1.

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Reward Systems](#reward-systems)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Introduction

The goal of this project is to develop and train autonomous racing cars using Deep Q-Learning (DQN) and this is the Readme.md file.
