# Linear Regression from Scratch

A beginner machine learning project implementing linear regression
and gradient descent using NumPy.

The model predicts fictional game damage from character strength.
This project explores how predictions, errors, gradients, and
parameter updates fit together during training.

## Tools

- Python
- NumPy
- Matplotlib
- Jupyter Notebook

## Model

The model uses the equation:

    predicted_damage = weight * strength + bias

- **Weight:** how much predicted damage changes per strength point.
- **Bias:** predicted damage when strength is zero.

Training adjusts both parameters to reduce mean squared error (MSE).

## Data

An initial example demonstrates prediction error using the exact
rule `damage = 3 * strength + 2`.

The training experiment then uses noisy observations:

| Strength | Observed Damage |
|----------|-----------------|
| 1 | 6 |
| 2 | 7 |
| 3 | 12 |
| 4 | 13 |

The held-out test examples are:

| Strength | Observed Damage |
|----------|-----------------|
| 5 | 17 |
| 6 | 20 |
| 7 | 23 |

## Training

The training loop performs these steps:

1. Calculate predictions.
2. Calculate prediction errors.
3. Calculate gradients for weight and bias.
4. Update both parameters using the learning rate.
5. Repeat for 1,000 steps.

The experiment uses a learning rate of `0.01`, starting with
weight `2.0` and bias `1.0`.

The learned parameters are approximately:

- Weight: **2.6273**
- Bias: **2.9197**

A plot compares the fitted line with the noisy training observations.

## Baseline Comparison

The baseline ignores strength and always predicts the mean
training damage: **9.5**.

Both approaches are evaluated on the same examples. Lower MSE
indicates smaller average squared prediction errors.

| Evaluation | Trained Model MSE | Baseline MSE |
|------------|------------------:|-------------:|
| Training | 0.801 | 9.25 |
| Test | 1.826 | 116.25 |

The trained model outperformed the baseline on the three held-out
test examples.

## Limitations

- The dataset is tiny and fictional.
- Test strengths are outside the training range, so these
  predictions involve extrapolation.
- A straight line cannot perfectly match the noisy training data.
- The notebook demonstrates training and test evaluation; it does
  not implement a separate validation set or systematic tuning.
- These results do not establish real-world predictive performance.

## Learning Context
I assembled and ran the training loop, practiced the 
calculations, and interpreted the model's results.
