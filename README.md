Reinforcement Learning with the Taxi Problem
This repository demonstrates the application of Reinforcement Learning (RL) to solve the classic "Taxi Problem" using Q-learning. The objective is to train an AI agent to pick up passengers from specific locations and drop them off at their desired destinations while navigating obstacles.


Project Description
1. Introduction to the Taxi Problem
The Taxi Problem is a classic RL task where an agent (taxi) operates in a grid environment with specific goals:

Pick up passengers at designated pickup locations.
Drop them off at their target destinations.
Navigate the grid while avoiding obstacles and minimizing time.
The environment is a 5x5 grid with:

Pickup locations: R (red), G (green), B (blue), Y (yellow).
Dropoff locations: Same as pickup locations.
Obstacles: Walls that the taxi cannot cross.
2. Environment Setup
We use the Gym library to create and interact with the Taxi-v3 environment. 

The grid consists of 25 locations, with different states representing the taxi's position, passenger's location, and destination.

3. State and Action Space
The state space is defined by:

Taxi position: 25 possible locations.
Passenger location: 5 possibilities (at a pickup/dropoff location or inside the taxi).
Destination: 4 possibilities.
This results in a total of 500 possible states. The action space includes:

Moving South, East, North, or West.
Picking up a passenger.
Dropping off a passenger.
4. Rewards and Penalties
Rewards and penalties are defined as follows:

Successful Drop-off: +20 points.
Each Time Step with Passenger: -1 point.
Illegal Pickup/Drop-off: -10 points.
Crossing Walls: Not allowed.
5. Initial Setup
We define an initial state for the taxi with a specific pickup and drop-off location

6. Q-Learning Algorithm
Q-learning is used to train the agent. We initialize the Q-table and define the parameters for learning:

Learning Rate (α): 0.1
Discount Factor (γ): 0.6
Exploration Rate (ε): 0.1
Epochs: 10,000

7. Evaluating the Model
After training, the Q-table is used to make decisions. We simulate 10 trips and visualize the taxi’s actions in the environment.

8. Results and Analysis
The Q-learning algorithm effectively learns the optimal policy for the taxi, minimizing the time to pick up and drop off passengers while avoiding penalties. The Q-values for different actions help determine the best actions to take in various states.

Key Points
Environment: The Taxi-v3 environment provides a 5x5 grid with pickup and drop-off tasks.
State and Action Space: Defined by the taxi’s location, passenger status, and destination.
Rewards and Penalties: Structured to encourage successful drop-offs and penalize illegal actions and time taken.
Training: Uses Q-learning to update Q-values based on actions and rewards.
Evaluation: Simulates trips to visualize the agent's performance and policy.
Requirements
gym
numpy
How to Run
Install the Gym library: pip install gym
Load the Taxi-v3 environment and run the Q-learning algorithm.
Evaluate the model by simulating trips and observing the agent's performance.

