# Stock Trading with Deep Reinforcement Learning

This project demonstrates the use of **Deep Reinforcement Learning (DRL)** to develop an agent for stock trading. The agent uses a **Proximal Policy Optimization (PPO)** algorithm from the **stable-baselines3** library to make trading decisions (Buy, Sell, Hold) based on historical stock data. The model is trained and evaluated using stock market data from publicly available datasets, and its performance is compared to a baseline Buy-and-Hold strategy.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Installation Instructions](#installation-instructions)
3. [Usage](#usage)
4. [Model Details](#model-details)
5. [Evaluation](#evaluation)
6. [Results](#results)
7. [License](#license)

---

## Project Overview

The goal of this project is to build a stock trading agent using **Deep Reinforcement Learning**. The model learns the best trading strategy based on historical stock price data, and its performance is evaluated by comparing it with a **Buy-and-Hold strategy**. 

The key components of the project include:
- **Data Preprocessing**: The dataset is cleaned and technical indicators (e.g., RSI, MACD) are added to the stock data.
- **Gym Environment**: A custom stock trading environment is built using the `gym` library.
- **DRL Model**: The stock trading agent is trained using the **Proximal Policy Optimization (PPO)** algorithm.
- **Evaluation and Visualization**: The model's performance is evaluated, and the results are compared to a baseline Buy-and-Hold strategy.
- **Model Deployment**: The trained model can be saved for future use or deployment.

---

## Installation Instructions

To get started, you'll need to install the required dependencies.

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/DeepRL-Stock-Trading.git
   cd DeepRL-Stock-Trading
   ```

2. Create a virtual environment (optional but recommended):
   ```bash
   python -m venv env
   source env/bin/activate  # On Windows use: .\env\Scripts\activate
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

Alternatively, you can install the necessary packages individually:
```bash
pip install pandas numpy matplotlib gym stable-baselines3 ta shimmy
```

---

## Usage

1. **Data Preprocessing**: The stock dataset (e.g., "ADANIPORTS.csv") should be placed in the project directory. The dataset should include columns such as `Date`, `Open`, `High`, `Low`, `Close`, and `Volume`. The dataset is preprocessed to include technical indicators like **RSI** and **MACD**.

2. **Training the Agent**:
   - The DRL agent is trained using the **Proximal Policy Optimization (PPO)** algorithm. 
   - The training process is started by running the following command:
     ```bash
     python train.py
     ```

3. **Evaluating the Model**:
   - After training, the model can be evaluated using the following command:
     ```bash
     python evaluate.py
     ```

   This will generate a plot of the portfolio value over time during the evaluation phase.

4. **Comparing with Baseline**:
   - The performance of the DRL agent is compared to a **Buy-and-Hold strategy**. This allows for assessing whether the DRL agent is outperforming a simple strategy of holding onto a stock throughout the entire period.

5. **Model Saving and Loading**:
   - The trained model can be saved and loaded for future use:
     ```bash
     model.save("ppo_stock_trading_final")
     ```

   - To load the model later:
     ```bash
     model = PPO.load("ppo_stock_trading_final")
     ```

---

## Model Details

- **Algorithm**: Proximal Policy Optimization (PPO)
- **Framework**: stable-baselines3, which is built on top of **PyTorch**
- **Action Space**: Discrete actions representing Buy, Sell, and Hold operations.
- **Observation Space**: The model receives observations consisting of stock data (Open, High, Low, Close, Volume, RSI, MACD) along with the current balance and number of shares held.

The PPO algorithm is used due to its stability and efficiency in solving reinforcement learning tasks, especially in environments with continuous state spaces like stock trading.

---

## Evaluation

### Performance Metrics:
- **Total Portfolio Value**: The agent's total portfolio value (balance + value of held stocks) over time.
- **Comparison with Buy-and-Hold Strategy**: The portfolio value of the DRL agent is compared to a Buy-and-Hold strategy, where the agent simply buys the stock at the beginning and holds it until the end of the time period.

### Results:
- The model's performance will be plotted, showing how the portfolio value evolves over time.
- The Buy-and-Hold strategy will be plotted as a reference to compare the agent's performance.

Example output:
- The DRL agent's portfolio value may outperform the Buy-and-Hold strategy, indicating that the agent has learned a profitable strategy.

---

## Results

Upon evaluation, you will see visualizations such as:
- A plot showing the DRL agent's portfolio value over time.
- A comparison between the DRL agent and a Buy-and-Hold strategy.
- The final portfolio value and comparison metrics.

These results can be used to assess whether the agent is successfully learning an effective trading strategy.

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- The **stable-baselines3** library for providing reinforcement learning algorithms.
- **gym** for creating the custom trading environment.
- **pandas** and **matplotlib** for data handling and visualization.
- **ta (Technical Analysis Library)** for generating technical indicators such as RSI and MACD.
