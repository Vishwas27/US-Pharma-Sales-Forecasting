# 💊 US Pharma Sales Forecasting Challenge

## 📘 Overview

In the pharmaceutical industry, accurate sales forecasting is essential for optimizing production, supply chain management, and strategic decision-making. This project focuses on the **US Pharma Sales Prediction Challenge**, where we predicted the sales of two medicinal products over the next three months. Our data included daily sales figures from the past four years. We used **advanced machine learning models** and **time series forecasting techniques** to capture seasonality, regional trends, and the impact of sales representatives (reps) working across different regions of the US.

The sales dynamics were influenced by various factors such as:

- **Seasonality**: Different times of the year had varying sales patterns, which depended on the type of medicine.
- **Regional trends**: Sales varied across different regions due to factors such as local religious practices and holiday schedules, requiring us to tailor our approach based on each region's data.
- **Sales representatives' activity**: The number of sales calls made by reps also played a significant role in determining sales figures.

The ultimate goal was to create a model that could accurately forecast sales, considering all of these variables. We used **Mean Absolute Percentage Error (MAPE)** as the evaluation metric to assess the model's performance.

---

## 🚀 Solution Approach

We employed a combination of **LSTM RNN models** and traditional time series forecasting techniques like **ARIMA** and **Facebook Prophet** to compare results and ensure accuracy.

### 1️⃣ Data Preprocessing
The raw sales data was preprocessed to handle missing values and normalize features such as:
- **Daily sales data**: The core of our time series, representing the number of units sold each day.
- **Sales calls data**: We included data on the number of sales calls made by the reps in each region, as this has a direct impact on the sales performance.
- **Regional segmentation**: Sales were analyzed region-wise to account for differences in trends due to regional characteristics like religious practices and holidays.

### 2️⃣ LSTM RNN Model

We used **LSTM (Long Short-Term Memory)** Recurrent Neural Networks, a powerful model designed for sequence prediction tasks. Our LSTM model was customized to predict future sales based on:
- **Daily sales sequences** from the last four years.
- **Calls made by reps** in the corresponding regions.
- **Time-dependent variables** such as the day of the week, month, and special holiday indicators for each region.

#### Model Architecture:
- **Input Layer**: Sequential sales data with additional features like sales calls.
- **LSTM layers**: Captured long-term dependencies in the data.
- **Dense layer**: Outputted the final prediction for the next three months of sales.

We trained the model on the last four years of data and evaluated its performance using **MAPE**.

### 3️⃣ ARIMA and Facebook Prophet Models

To ensure robust forecasting, we also deployed:
- **ARIMA**: A traditional statistical model for time series forecasting, which captured linear trends and seasonality in the sales data.
- **Facebook Prophet**: A model designed for forecasting at a daily level, capable of handling seasonality and trend shifts in time series data.

These models served as benchmarks to compare against our LSTM RNN results, providing additional insights into how well deep learning models performed relative to simpler time series approaches.

---

## 🔢 Evaluation

The models were evaluated using **Mean Absolute Percentage Error (MAPE)**, a widely accepted metric for time series forecasting. We forecasted the sales for the next three months based on the past four years of data.

---

## 🛠️ Tools and Libraries Used

- **Python**: The primary programming language for model development.
- **TensorFlow**: For implementing the LSTM RNN model.
- **Facebook Prophet**: For traditional time series forecasting.
- **ARIMA**: Another time series model for benchmarking.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical computations.
- **Matplotlib**: For visualizing the results and trends.
  
---

## 📊 Results

After testing on historical sales data and running predictions, we compared the accuracy of all models:

- **LSTM RNN**: Captured complex sales trends and performed well on the test set.
- **ARIMA**: Gave decent predictions but struggled with nonlinear patterns.
- **Facebook Prophet**: Was effective in handling seasonality but slightly less accurate than LSTM RNN in our case.

The **LSTM model** outperformed the traditional models in terms of overall MAPE, providing the most accurate forecasts for the next three months of sales. The use of sales calls as an additional feature in the LSTM model further improved its predictive capability.

---

## 📈 Conclusion

Our final model used **LSTM RNN** as the main approach to capture the long-term dependencies in the sales data while taking into account seasonality and regional trends. We also explored and compared the results with traditional models like **ARIMA** and **Facebook Prophet**. The **LSTM model** consistently gave us better results in terms of accuracy, demonstrating its ability to handle the complex nature of pharmaceutical sales forecasting.

This solution can help pharmaceutical companies plan for future sales with better accuracy, ultimately leading to improved resource allocation, inventory management, and production planning.
