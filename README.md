# Energy Forecasting using LSTM vs Transformer

This project compares **Recurrent Neural Networks (LSTM)** and **Transformer models** for time series forecasting on electricity load data.

---

## Objective

To evaluate how well LSTM and Transformer architectures perform on:
- Forecast accuracy
- Training efficiency
- Model complexity
- Stability across runs

---

## Dataset

- Time series electricity load data
- Univariate forecasting
- Temporal split: **90% train / 10% test (no shuffling)**

---

## Models Implemented

### LSTM (RNN)
- 2 stacked LSTM layers
- 64 hidden units
- Dense output layer
- Sequential processing

### Transformer
- Positional encoding (sinusoidal)
- Multi-head self-attention (4 heads)
- 2 encoder layers
- Feed-forward network (d_ff = 256)
- Global average pooling

---

## Results Comparison

| Metric            | LSTM (RNN) | Transformer |
|------------------|-----------|------------|
| MAE              | 223.13    | 740.30     |
| RMSE             | 302.22    | 1014.72    |
| MAPE (%)         | 0.77%     | 2.62%      |
| R² Score         | 0.9966    | 0.9612     |
| Training Time (s)| 548.83    | 1589.66    |
| Parameters       | 49,985    | 100,161    |

---

## Key Insights

### 1. LSTM Performance Advantage in This Setup
- Lower MAE and RMSE compared to Transformer
- Better percentage error (MAPE)
- Higher R² score indicating stronger fit

In this setup, LSTM proved more effective for modeling the dataset.

---

### 2. Transformer Performance Limitations
- Higher error metrics compared to LSTM
- More sensitive to training conditions
- Performance likely impacted by:
  - Limited dataset size
  - Minimal hyperparameter tuning

Transformer models may require further tuning and larger datasets to perform optimally.

---

###  3. Computational Cost vs Benefit
- Transformer has ~2x parameters
- ~3x training time

Increased complexity did not yield proportional performance gains in this case.

---

### 4. Architectural Differences
- LSTM: Sequential memory-based learning → stable for structured temporal data
- Transformer: Parallel attention → powerful but often data-dependent

---

### 5. Convergence Behavior
- Both models converged during training
- LSTM showed:
  - Faster convergence
  - More stable training patterns

---

## Key Learning

> Model performance depends heavily on data characteristics and setup.  
> For structured, univariate time series, LSTMs can be highly effective, while Transformers may require careful tuning and larger datasets to fully leverage their potential.

---

## Tech Stack

- Python
- TensorFlow / Keras
- NumPy, Pandas
- Matplotlib

---

## Visualizations

- Training loss curves
- Actual vs predicted comparison
- Residual analysis
- Attention weight heatmap (Transformer)

---

## Future Improvements

- Hyperparameter tuning (learning rate, heads, layers)
- Add dropout / regularization to Transformer
- Try hybrid models (LSTM + Attention)
- Use larger or multivariate datasets

---

---

## Conclusion

This project highlights an important practical insight:

- Model performance depends heavily on data characteristics and problem setup  
- Simpler architectures like LSTM can perform very well on structured time series  
- More complex models like Transformers may require careful tuning and sufficient data to deliver their full potential  

---
