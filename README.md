# Deep-Reinforcement-Learning-for-Lunar-Lander
This repository contains the code for a deep reinforcement learning project that tackles the Lunar Lander environment from OpenAI Gym. The goal is to train agents to control the lunar module so that it lands safely on the landing pad (located at (0,0)) by implementing DRL methods from scratch. The project includes implementations of both the policy gradient and actor-critic methods.

Overview
Task:
Enable the Lunar Lander to achieve a safe landing between the yellow flags by maximizing the total reward. Two DRL methods are implemented:

Policy Gradient
Actor-Critic
Environment:
The Lunar Lander environment simulates the landing of a spacecraft on the surface of the moon with the following details:

State: An 8-dimensional vector representing:
Lander’s x and y coordinates
Linear velocities in x and y directions
Lander's angle and angular velocity
Two booleans indicating whether each leg is in contact with the ground
Actions: 4 discrete actions:
0: No action
1: Fire left engine (accelerate right)
2: Fire main engine (accelerate downward)
3: Fire right engine (accelerate left)
Reward Structure:
Approaching the landing pad and coming to rest yields roughly 100-140 points.
Moving away from the pad penalizes the agent.
Crashing incurs an additional -100 points.
Successfully coming to rest awards an extra +100 points.
Each leg with ground contact provides +10 points.
Firing the main engine costs -0.3 points per frame, and the side engines cost -0.03 points per frame.
The environment is considered solved when the total reward reaches 200 points.

![image](https://github.com/user-attachments/assets/8c47b38b-8841-4a39-a8ea-d5176299b15d)


Methods
Policy Gradient
Implementation:
A neural network is trained using the policy gradient method, where the network directly maps states to action probabilities. The implementation is based on the sample code and is run for a specified number of epochs (e.g., 100 epochs) with initial results showing an average total reward of approximately -176.83 over 5 test runs.

Tuning:
The learning rate, number of epochs, and other hyperparameters are tuned until the total reward converges. Additionally, modifications such as switching to an accumulative decaying reward structure have been explored.

Actor-Critic
Implementation:
The actor-critic method builds upon the policy gradient approach by integrating a value function estimator. This helps reduce the variance of the gradient estimates and stabilizes training.

Advanced Tuning:
Further modifications to the reward mechanism and hyperparameter adjustments have been applied to improve the overall performance of the agent.

Training and Evaluation
Training Details:

The agent is trained in the Lunar Lander environment using gradient descent updates on the policy network (and value network for actor-critic).
Hyperparameters such as learning rate, number of epochs, and network architectures are tuned based on the total reward performance.
Evaluation:
The trained agent is evaluated over 5 test runs. The average total reward across these runs is used as the primary performance metric—the higher the reward, the better the agent's performance.

Code Structure
Implementation:

The repository includes all necessary code for setting up the Lunar Lander environment, implementing the policy gradient and actor-critic methods, and conducting training loops.
The code covers environment interaction, neural network definition, gradient descent updates, hyperparameter tuning, and evaluation routines.
Dependencies:
Utilizes libraries such as gym for the environment simulation, numpy for numerical computations, and torch for building and training neural networks.

Conclusion
This project demonstrates the implementation of deep reinforcement learning techniques—specifically policy gradient and actor-critic methods—from scratch to solve the Lunar Lander environment. By carefully tuning hyperparameters and experimenting with different reward structures, the agent learns to navigate the challenges of landing safely. All code, experiments, and evaluation results are provided in this repository, highlighting the process of developing DRL agents for complex control tasks.
