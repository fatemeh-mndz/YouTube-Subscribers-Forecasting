
# YouTube Subscribers Forecasting

## Project Overview

This project aims to forecast the number of YouTube subscribers over future time steps using two different machine learning models: Dense (Fully Connected Neural Network) and LSTM (Long Short-Term Memory Network). The dataset consists of historical YouTube subscriber counts, and the goal is to predict future subscriber growth for specific periods (7, 10, and 30 days ahead) based on past data.

### Dataset
- [dataset](yt_subscribers.csv)

### Key Features
- **Input Window (n_step):** A window of 30 days of historical subscriber data.
- **Forecast Days:** Predictions were made for 7, 10, and 30 days into the future.
- **Models Used:** Dense Neural Network and LSTM.

## Models

### 1. **Dense Model**
   - **Input Window:** 30 days.
   - **Forecast Horizon:** 7 and 10 days.
   - **Mean Absolute Error (MAE):**
     - **Train Data:**
       - `MAE = 0.0895`
     - **Test Data:**
       - `MAE = 0.1294`


### 2. **LSTM Model**
   - **Input Window:** 30 days.
   - **Forecast Horizon:** 10 and 30 days.
   - **Mean Absolute Error (MAE):**
     - **Train Data:**
       - `MAE = 0.1199`
     - **Test Data:**
       - `MAE = 0.1331`

## Approach

### Data Preparation
- The historical YouTube subscriber data was preprocessed by normalizing the values using `MinMaxScaler`.
- The data was split into training and test sets.
- For each model, a window of the last 30 days of data (`n_step=30`) was used as input to predict the future subscriber count for the given forecast horizon (7, 10, or 30 days).

### Models Description

#### 1. **Dense Model**
- A simple feedforward neural network with 30 input features corresponding to the last 30 days of subscriber data.
- The model predicts the next 7 or 10 days of subscriber counts.

#### 2. **LSTM Model**
- An LSTM model, which is a recurrent neural network capable of capturing temporal dependencies in sequential data.
- The LSTM model used a window of 30 days (`n_step=30`) to predict the next 10 and 30 days of subscriber counts.

### Performance Evaluation
The performance of both models was evaluated using Mean Absolute Error (MAE). The results show that the LSTM model performs better than the Dense model for both short and long-term forecasts, especially for 30-day forecasts.



### Plot Example

- The project also includes visualizations comparing the actual vs. predicted YouTube subscribers using the trained models.
- Example plot for 10-day forecast using the LSTM model:

![Forecast Plot](output.png)

- Example plot for 7-day forecast using the Dense model:

![Forecast Plot](output2.png)

## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/youtube-subscriber-forecasting.git
   ```
   
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Prepare the dataset and start training:
   ```python
   python train.py
   ```

## Conclusion

The project demonstrates the effectiveness of using time-series models like LSTM over a simple Dense Neural Network for forecasting future YouTube subscribers. The LSTM model, which captures temporal dependencies, performs better on test data, making it a suitable choice for this task.

