# CS-370_Emerging_Trends
Introduction to AI/ML Modeling.

# CS 370 Emerging Trends - Project Two Reflection

## Project Summary

This project involved implementing a deep Q-learning algorithm to train an intelligent agent (a "pirate") to navigate a maze and find a treasure. This project was implemented using several components:

* **Environment (`TreasureMaze.py`):** A Python class defining the 8x8 maze, agent movement rules, state representation, rewards, and game status logic.
* **Experience Replay (`GameExperience.py`):** A Python class to store the agent's experiences (state, action, reward, next state) and provide batches for training.
* **Neural Network Model (`build_model`):** A function within the Jupyter Notebook that defined the structure of the deep neural network using Keras, including dense layers and PReLU activations, compiled with an Adam optimizer and MSE loss.
* **Helper Functions:** Functions within the notebook like `play_game` (to test the trained model), `completion_check` (to validate if the model can win from all free cells), `show` (to visualize the maze), and `format_time` were also provided.

My primary task was to **implement the core deep Q-learning training algorithm within the `qtrain` function**. This involved translating the provided pseudocode into Python code, handling the main training loop across epochs, managing the agent's interaction with the environment within each epoch, implementing the epsilon-greedy strategy for action selection (balancing exploration and exploitation), storing experiences in the replay buffer, sampling data from the buffer, training the neural network model (`model.fit`), evaluating loss (`model.evaluate`), and checking for the win condition (achieving a 100% win rate over a history window and passing the `completion_check`). The implementation successfully trained the agent, achieving a sustained 100% win rate and passing the validation checks.

## Connection to Computer Science

**What do computer scientists do and why does it matter?**

Computer scientists design, develop, and analyze computational systems to solve complex problems. This project demonstrates this by applying AI algorithms (reinforcement learning, neural networks) to solve a pathfinding problem. Computer science matters because it drives innovation across virtually all fields – from automation and data analysis to communication, entertainment (like game AI), scientific discovery, and creating tools that enhance human capabilities. Developing intelligent agents that can learn and adapt, like the pirate agent, is a key area with significant real-world implications in robotics, autonomous systems, and personalized applications.

**How do I approach a problem as a computer scientist?**

This project demonstrated a typical computer science problem-solving approach:

1.  **Understand the Problem:** Define the goal (find the treasure in the maze), constraints (grid world, valid moves, obstacles), and success criteria (maximize reward, achieve 100% win rate).
2.  **Model the Problem:** Represent the environment (maze matrix) and agent state numerically so a computational algorithm can process it. Define the interactions (actions, rewards, state transitions).
3.  **Select/Design an Algorithm:** Choose an appropriate algorithm based on the problem type. Here, deep Q-learning was suitable because the state space is relatively large (requiring function approximation via a neural network) and the agent needs to learn a policy through trial-and-error based on rewards.
4.  **Implement the Solution:** Write code (Python, Keras, NumPy) to implement the environment interaction, the neural network, the experience replay, and the learning algorithm itself.
5.  **Test and Iterate:** Train the agent, monitor its performance (loss, win rate), debug issues (like the initial `UnboundLocalError`), evaluate the results against the success criteria (`completion_check`, `play_game`), and potentially refine the algorithm or parameters if needed .

**What are my ethical responsibilities to the end user and the organization?**

As computer scientists developing AI systems, we have significant ethical responsibilities:

* **To the End User:**
    * **Reliability & Safety:** Ensure the AI agent performs its intended function reliably and doesn't cause harm (e.g., in a game, this means performing reasonably well; in safety-critical applications, the stakes are much higher). The agent shouldn't get stuck in infinite loops or behave unpredictably in ways that frustrate the user experience.
    * **Transparency/Explainability (Optional but Recommended):** While not implemented here, striving to make AI decisions understandable helps build trust and allows users to identify potential issues.
    * **Fairness:** Ensure the AI does not exhibit unfair bias, although bias was less relevant in this specific maze-solving context than in applications involving human data.

* **To the Organization:**
    * **Resource Management:** Be mindful of computational resources. Training deep learning models can be time-consuming and energy-intensive (this model took hours).
    * **Data Privacy & Security:** If the AI uses sensitive data (not the case here, but common in many AI applications), ensure it's handled securely and privacy is protected according to regulations and best practices.
    * **Integrity & Honesty:** Accurately represent the capabilities and limitations of the AI system. Ensure the development process follows ethical guidelines and organizational standards.
    * **Considering Impact:** Reflect on the broader consequences of the technology being developed, including potential misuse or unintended societal effects.
