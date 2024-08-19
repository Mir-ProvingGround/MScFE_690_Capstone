# MScFE_690_Capstone
Student Group 6400

## Project Title: Distributed Stacking and Centralized Ensemble for Trading Strategies Using Deep and Reinforcement Learning Algorithms

### 1)	Project Overview ###
This project aims to enhance stock price prediction and trading decision processes by leveraging advanced machine learning techniques, specifically Convolutional Neural Networks (CNNs) and Long Short-Term Memory networks (LSTMs). The project integrates these models into a distributed stacking framework and uses a centralized ensemble approach, optimized with Reinforcement Learning (RL) agents. The solution addresses the challenge of reducing model execution times while maintaining high prediction accuracy.

### 2)	Solution Architecture ###
Components and Workflows:

#### a)	Data Acquisition and Preparation: ####
-	Objective: To gather and preprocess historical stock price data from Microsoft (NYSE: MSFT) for training and validation.
-	Tools: Python, Keras, Keras-RL, and TCP/IP Protocol for network programming.
-	Data: Daily stock prices, technical indicators (e.g., Heiken Ashi, Moving Averages).

#### b)	Prediction Stacking: ####
-	Objective: To generate multiple predictions using CNN and LSTM models by varying hyperparameters such as learning rates.
-	Scripts: 
  •	`CNNs.ipynb`: Produces 50 predictions with learning rates ranging from 0.0001 to 0.005.
  •	`LSTMs.ipynb`: Produces 50 predictions using LSTM models.
  •	`CNNs_LSTMs.ipynb`: Combines CNN and LSTM predictions (25 predictions each).
-	Outcome: Stacked predictions are prepared for the ensemble process.

#### c)	Distributed Stacking: ####
-	Objective: To distribute the stacking process across multiple processors or computers to reduce execution time.
-	Scripts: 
  •	`distCNNs.ipynb`, `distLSTMs.ipynb`, `distCNNs_LSTMs.ipynb`.
-	Utilizes socket programming for communication and multithreading to manage task distribution.
-	Method: Offline (manual merging of predictions) or online (automated merging via network).

#### d)	Ensemble Process: ####
-	Objective: To combine stacked predictions using RL agents and majority voting to make final trading decisions.
-	Tools: Deep Q-Network (DQN) with ADADELTA optimizer.
-	Outcome: Final decisions to hold, long, or short a stock, aiming for maximum profitability.

#### e)	Performance Metrics: ####
-	Processing Time: Measures the time taken from data retrieval to the final trading decision, with a focus on reducing stacking execution time.
-	Accuracy: Evaluates the precision of trading decisions and win/loss rates across different models.

### 3)	Benefits and Expected Outcomes ###
-	Improved Execution Efficiency: Distributed stacking significantly reduces processing time, with initial results showing up to a 21% reduction in execution time when using LSTM stacking with two threads.
-	Enhanced Prediction Accuracy: By leveraging both CNN and LSTM models, the solution aims to produce more accurate predictions, leading to better trading decisions and higher profitability.
-	Scalability: The distributed stacking method allows for the processing load to be shared across multiple machines, making the solution scalable and adaptable to larger datasets and more complex models.
### 4)	Conclusion ###
The proposed solution integrates cutting-edge machine learning techniques within a distributed and scalable framework. It addresses the challenges of execution time and prediction accuracy in stock market trading strategies, with the potential for significant improvements in performance. The approach is expected to provide valuable insights and robust trading strategies for financial markets.
