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

This environment comes in two seperate variations, including **1 Agent** and **20 Agents**. In order to fulfil this commission only one of them has to be solved. Both of them are allready placed in the *Environment_1_Agent* and *Environment_20_Agents* folders in this repository.  

### Solving the environment

There are two options to solve the episodic task in the Unity ML-Agents Reacher Environment.

#### Option 1

Environment 1: One agent. The agent has to get an average score of +30 over 100 consecutive episodes.

#### Option 2

Environment 2: Twenty agents. The average score over all 20 agents has to be +30 over 100 consecutive episodes.

In this repository an solution for option 2 of the environment is published. 

**Annotation:** The agent is trained with twenty copys of himself, nevertheless his networks can be used to perform in option 1 of the environment.

## Getting started

Before running the code in the jupyter-notebook make sure to install the necessary libraries. If you'd like to install them on your own machine please follow the instructions below. These instructions imply that your machine already satisfy conditions to run all, not explicitly for this project necessary, requirements like for example jupyter notebooks or python3-code.

To use this repositotry on your own machine please set up a python-environment. In order to do so please follow the instructions in this repository: https://github.com/udacity/deep-reinforcement-learning#dependencies. 

## Use the Code

In order to use the code in this repository make sure your machine satisfy  all requirements in the "Getting started"- paragraph above. Now you are free to clone this repository and use it on your own computer(!No GPU-support needed!). After cloning, you have to open a terminal and navigate to the folder representing the repository these folder should be placed in your python-environment. Please open a jupyter notebook using the *jupyter notebook* command. The Notebook will open in your browser. Thereafter you have to open the *Continuous_Control_Training.ipynd*-file and restart the kernel by clicking on the "restart"-button. A dialogue will open, please click on the "restart and run all cells"-button. Finally the agents train. If you like to whach them while training please change the ```no_graphics = True``` parameter to ```no_graphics = False```. If you prefer watching an already trained agent, please open the *Continuous_Control_Trained_Agent_Test.ipynd*-file.

**For additional information please read the "Report.md"-file**
