# Project2_Continuous_Control
The second project in the udacity deep-reinforcement-learning nanodegree

Note: This repository is created for Linux ubuntu 21.04. It's only guaranteed to work on this version. Nonetheless it should work on other Linux versions as well.

## The Task
This GitHub repository is designed to solve the Unity ML-Agents Reacher Environment.

## The environment
![Unity ML-Agents Reacher Environment](Reacher.gif)

The agent in this repository is designed to move a double-jointed arm to a stiring target location. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. The goal of the agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector including four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Variations

This environment comes in two seperate variations. Including **1 Agent** and **20 Agents**. In order to fulfil this commission only one of them has to be solved.  

### Solving the environment

There are two options to solve the episodic task in the Unity ML-Agents Reacher Environment.

#### Option 1

Environment 1: One agent. The agent has to get an average score of +30 over 100 consecutive episodes.

#### Option 2

Environment 2: Twenty agents. The average score over all 20 agents has to be +30 over 100 consecutive episodes.
