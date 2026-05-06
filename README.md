# Urban AQI Forecasting via Time Series Modeling & Transfer Learning

This project explores forecasting urban air quality (PM2.5) using classical time series models and deep learning approaches, with a focus on **transfer learning** to improve generalization across cities.

## Project Summary

We developed and evaluated forecasting models to predict PM2.5 levels using historical air quality and weather data from **Ahmedabad (source city)** and **Kolkata (target city)**. The goal was to build a model that could generalize across different urban environments using **transfer learning**.
Data sourced from [Kaggle: Air Quality Data in India](https://www.kaggle.com/datasets/rohanrao/air-quality-data-in-india)


## What I Did

- Collected and preprocessed 5 years of hourly AQI and meteorological data from both cities
- Built traditional time series models: **ARIMA** and **SARIMA**
- Designed a two-layer **LSTM neural network** to capture temporal and multivariate dependencies
- Applied **transfer learning**: fine-tuned the Ahmedabad-trained LSTM on Kolkata data
- Compared optimizers (**SGD** vs **Adam**) and evaluated all models using **RMSE**

## Models Used

| Model        | Description                                       | Key Metric (RMSE) |
|--------------|---------------------------------------------------|-------------------|
| ARIMA        | Baseline univariate time series model             | ~0.06             |
| SARIMA       | Adds seasonality handling to ARIMA                | 0.023 (Ahmedabad) |
| LSTM (SGD)   | 2-layer RNN with Stochastic Gradient Descent      | 0.0605            |
| LSTM (Adam)  | Improved convergence and accuracy                 | 0.0534            |
| Transfer LSTM| Fine-tuned LSTM on Kolkata data                   | **0.0678**        |

## Technologies

- **Python**, **Pandas**, **NumPy**
- **scikit-learn**, **statsmodels**
- **TensorFlow / Keras**
- **Matplotlib**, **Seaborn**

## Features

- Recursive feature selection and VIF-based dimensionality reduction
- Forecasts next 7 days (168 hours) of PM2.5 levels
- Fine-tuned model transfer to reduce training time on low-data cities
- Visual evaluation with forecast vs. actual plots

## Future Directions

- Scale to additional cities with limited historical data
- Integrate real-time weather and pollution APIs
- Explore hybrid models with Transformers and attention mechanisms

---

Project completed as part of APM 523: Optimization at Arizona State University_  
