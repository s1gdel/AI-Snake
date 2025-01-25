This project implements an AI agent that learns to play the classic Snake game using Deep Q-Learning, a reinforcement learning technique. The agent is trained to maximize its score by learning to navigate the snake to collect food while avoiding collisions with the walls and its own body.

Project Structure
The project consists of the following files:

agent.py: Contains the Agent class, which handles the state management, action selection, and training of the neural network.

game.py: Implements the Snake game logic using the Pygame library.

model.py: Defines the neural network model (Linear_QNet) and the training logic (QTrainer).

plot.py: Provides a utility function to plot the training progress, showing the scores and mean scores over time.

Requirements
To run this project, you need the following Python packages:

torch: For building and training the neural network.

pygame: For rendering the Snake game.

numpy: For numerical operations.

matplotlib: For plotting the training progress.

You can install the required packages using pip:

bash
Copy
pip install torch pygame numpy matplotlib
How to Run
Clone the repository or download the project files.

Navigate to the project directory.

Run the agent.py script to start the training process:

bash
Copy
python agent.py
Training Process
The training process involves the following steps:

Initialization: The game and the agent are initialized.

State Observation: The agent observes the current state of the game, which includes the snake's direction, the position of the food, and potential dangers (collisions).

Action Selection: The agent selects an action (move straight, turn left, or turn right) based on the current state. Initially, the agent explores the environment by taking random actions, but over time, it relies more on the learned policy.

Game Step: The selected action is executed in the game, and the new state, reward, and game-over status are observed.

Training: The agent uses the observed state, action, reward, and next state to train the neural network. Both short-term memory (immediate experience) and long-term memory (past experiences stored in a replay buffer) are used for training.

Plotting: The training progress is plotted in real-time, showing the scores and mean scores over the number of games played.

Key Parameters
MAX_MEMORY: The maximum size of the replay buffer (100,000 experiences).

BATCH_SIZE: The number of experiences sampled from the replay buffer for training (1,000).

LR: The learning rate for the neural network (0.001).

GAMMA: The discount factor for future rewards (0.9).

Model Architecture
The neural network used in this project is a simple feedforward network with one hidden layer:

Input Layer: 11 neurons (representing the state of the game).

Hidden Layer: 256 neurons with ReLU activation.

Output Layer: 3 neurons (representing the possible actions: straight, right, left).

Saving the Model
The trained model is saved in the ./model directory as model.pth. You can modify the file_name parameter in the save method of the Linear_QNet class to save different versions of the model.

Plotting
The training progress is plotted using matplotlib. The plot shows the scores achieved in each game and the mean score over all games. This helps in visualizing the learning progress of the agent.

Customization
You can customize the following aspects of the project:

Game Parameters: Modify the game's width, height, block size, and speed in the SnakeGameAI class in game.py.

Neural Network Architecture: Change the number of layers, neurons, or activation functions in the Linear_QNet class in model.py.

Training Parameters: Adjust the learning rate, discount factor, batch size, and memory size in agent.py.

Conclusion
This project demonstrates how to use Deep Q-Learning to train an AI agent to play the Snake game. By experimenting with different parameters and network architectures, you can further improve the agent's performance. Enjoy training your own Snake AI!
