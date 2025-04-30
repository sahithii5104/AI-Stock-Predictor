# AI-Stock-Predictor
Here is a sample **README.md** file for your AI Stock Predictor project, tailored for running in Jupyter/Colab and based on your workflow and outputs:

---

# AI Stock Price Predictor

This project uses an LSTM (Long Short-Term Memory) neural network to predict stock closing prices based on historical data. The model is implemented in Python using TensorFlow/Keras and runs in Jupyter Notebook or Google Colab. It fetches data automatically from Yahoo Finance, preprocesses it, trains an LSTM, and visualizes predictions against actual prices.

---

## 🚀 Features

- **Automatic Data Download:** Uses [yfinance](https://github.com/ranaroussi/yfinance) to fetch historical stock data.
- **Data Preprocessing:** Normalizes prices and creates time series sequences.
- **LSTM Neural Network:** Learns temporal dependencies in stock prices.
- **Visualization:** Plots actual, training, and testing predictions for easy comparison.
- **Customizable:** Easily change the stock ticker or model hyperparameters.

---

## 📊 Example Output

![Sample Outp 🛠️ Requirements

- Python 3.x
- numpy
- pandas
- matplotlib
- scikit-learn
- tensorflow
- yfinance

Install all dependencies in your notebook with:
```python
!pip install numpy pandas matplotlib scikit-learn tensorflow yfinance
```

---

## 💻 Usage

1. **Clone or Download the Repository**
   ```
   git clone https://github.com/yourusername/ai-stock-predictor.git
   cd ai-stock-predictor
   ```

2. **Open the Notebook**
   - Use Jupyter Notebook or Google Colab to open `AI_Stock_Predictor.ipynb`.

3. **Run the Notebook**
   - The notebook will:
     - Download historical data (default: Apple, `AAPL`)
     - Preprocess and normalize it
     - Train the LSTM model
     - Visualize predictions

4. **Customize**
   - Change the `ticker` variable to another stock (e.g., `'GOOG'`, `'TSLA'`).
   - Adjust model parameters like `SEQ_LENGTH`, LSTM units, epochs, etc.

---

## ⚡ How It Works

1. **Data Loading:**  
   Downloads historical closing prices for the selected stock.

2. **Preprocessing:**  
   - Normalizes prices to a 0-1 range.
   - Converts data into sequences (e.g., previous 60 days to predict next day).

3. **Model Training:**  
   - LSTM layers learn temporal patterns.
   - Dropout layers help prevent overfitting.

4. **Prediction & Visualization:**  
   - Model predicts prices on both training and test data.
   - Results are plotted for visual comparison.

---

## 🧩 Troubleshooting

- **ModuleNotFoundError:**  
  If you see `No module named 'yfinance'`, run `!pip install yfinance` in a notebook cell.

- **Shape Mismatch Error:**  
  Use this code for plotting to avoid broadcasting errors:
  ```python
  # Prepare empty arrays for plotting
  train_predict_plot = np.empty_like(scaled_data)
  train_predict_plot[:, :] = np.nan
  train_predict_plot[SEQ_LENGTH:train_size + SEQ_LENGTH, :] = train_predict

  test_predict_plot = np.empty_like(scaled_data)
  test_predict_plot[:, :] = np.nan
  test_predict_plot[train_size + SEQ_LENGTH:, :] = test_predict
  ```

---

## 📈 Model Evaluation

After training, evaluate the model with RMSE and MAPE:
```python
from sklearn.metrics import mean_squared_error, mean_absolute_percentage_error

train_rmse = np.sqrt(mean_squared_error(y_train_actual[0], train_predict.flatten()))
test_rmse = np.sqrt(mean_squared_error(y_test_actual[0], test_predict.flatten()))
test_mape = mean_absolute_percentage_error(y_test_actual[0], test_predict.flatten())

print(f"Train RMSE: {train_rmse:.2f}")
print(f"Test RMSE: {test_rmse:.2f}")
print(f"Test MAPE: {test_mape:.2%}")
```

---

## ⚠️ Disclaimer

This project is for educational and research purposes only. Stock price prediction is inherently uncertain and should not be used as financial advice.

---

## 🤝 Contributing

Pull requests and suggestions are welcome!

---

## 📧 Contact

For questions, open an issue or contact [mailto:sahithii5104@gmail.com).

---

**Happy Predicting!**

