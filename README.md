## Udacity Deep Reinforcement Learning Nanodegree Project 2: Continuous Control
This repository contains my codes, report and other files for Udacity Deep Reinforcement Learning Nanodegree Project 2: Continuous Control.
Project's goal
In this environment, a double-jointed arm can move to target locations. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of the agent is to maintain its position at the target location for as many time steps as possible.
 
Environment details
The environment is based on Unity ML-agents. Unity ML-Agents is an open-source Unity plugin that enables games and simulations to serve as environments for training intelligent agents.
Note: The Unity ML-Agent team frequently releases updated versions of their environment. We are using the v0.4 interface. The project environment provided by Udacity is similar to, but not identical to the Reacher environment on the Unity ML-Agents GitHub page.
The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.
•	Set-up: Double-jointed arm which can move to target locations.
•	Goal: The agents must move it's hand to the goal location, and keep it there.
•	Agents: The environment contains 10 agent with same Behavior Parameters. (The provided Udacity agent versions are Single Agent or 20 Agents.)
•	Agent Reward Function (independent):
o	+0.1 Each step agent's hand is in goal location.
•	Behavior Parameters:
o	Vector Observation space: 26 variables corresponding to position, rotation, velocity, and angular velocities of the two arm Rigidbodies.
o	Vector Action space: (Continuous) Size of 4, corresponding to torque applicable to two joints.
o	Visual Observations: None.
•	Benchmark Mean Reward: 30
For this project, Udacity provides two separate versions of the Unity environment:
•	The first version contains a single agent.
•	The second version contains 20 identical agents, each with its own copy of the environment.
The second version is useful for algorithms like PPO, A3C, and D4PG that use multiple (non-interacting, parallel) copies of the same agent to distribute the task of gathering experience.
Solving the environment
Depending on the chosen environment, there are 2 options to solve the environment:
Option 1: Solve the First Version
The task is episodic, and in order to solve the environment, the agent must get an average score of +30 over 100 consecutive episodes.
Option 2: Solve the Second Version
The barrier for solving the second version of the environment is slightly different, to take into account the presence of many agents. In particular, the agents must get an average score of +30 (over 100 consecutive episodes, and over all agents). Specifically: - After each episode, the rewards that each agent received (without discounting) are added up , to get a score for each agent. This yields 20 (potentially different) scores. The average of these 20 scores is then used. - This yields an average score for each episode (where the average is over all 20 agents). The environment is considered solved, when the average (over 100 episodes) of those average scores is at least +30.
In my implementation I have chosen to solve the Second version of the environment (20 Agents) using DDPG algorithm.
Getting started
Installation requirements
•	To begin with, you need to configure a Python 3.6 / PyTorch 0.4.0 environment with the requirements described in Udacity repository
•	Then you need to clone this project and have it accessible in your Python environment
•	For this project, you will not need to install Unity. This is because we have already built the environment for you, and you can download it from one of the links below. You need to only select the environment that matches your operating system:
o	Version 1: One (1) Agent
	Linux: click here
	Mac OSX: click here
	Windows (32-bit): click here
	Windows (64-bit): click here
o	Version 2: Twenty (20) Agents
	Linux: click here
	Mac OSX: click here
	Windows (32-bit): click here
	Windows (64-bit): click here
(For Windows users) Check out this link if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.
(For AWS) If you'd like to train the agent on AWS (and have not enabled a virtual screen), then please use this link (version 1) or this link (version 2) to obtain the "headless" version of the environment. You will not be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (To watch the agent, you should follow the instructions to enable a virtual screen, and then download the environment for the Linux operating system above.)
•	Finally, you can unzip the environment archive in the project's environment directory and set the path to the UnityEnvironment in the code.
Instructions
Training an agent
You can either run Continuous_Control.ipynb in the Udacity Online Workspace for "Project2: Continuous Control" step by step or build your own local environment and set the path to the UnityEnvironment in the code.
Note: The Workspace does not allow you to see the simulator of the environment; so, if you want to watch the agent while it is training, you should train locally.

