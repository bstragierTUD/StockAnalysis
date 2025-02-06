# Nvidia Stock Analysis

## Motivation

Recently, I lost money on Nvidia stock due to the sudden release of DeepSeek, which outperformed many already available large language models (LLMs). This event caused a shock in the AI world and led to a sudden decline in Nvidia's stock price.

This was non-ideal for my portfolio, and as a result, I would like to begin building models to attempt to model the stock market. Given the complexity of financial markets, this is a challenging task, so I decided to start simple.

In this study, my goal is to determine whether a model can reliably predict whether the opening price of Nvidia stock tomorrow will be higher or lower than today's closing price.

## Random Forest Attempt

Random forests seemed like a natural choice. They are well-known for handling non-linear data relatively well and require minimal data preprocessing, such as standardization or Principal Component Analysis (PCA).

That being said, my attempt to predict whether tomorrow's opening stock price would be higher or lower than today's closing price using a random forest model largely failed. Initially, I used the following features:

- Today's closing price
- Today's opening price
- Today's high price
- Today's low price
- The volume of stocks traded

However, this proved to be ineffective, with a test accuracy below 50% and a precision score of just 43%. In this case, precision is more valuable to consider than recall because we are more concerned with minimizing false positives (incorrectly predicting an increase when there is actually a decrease), rather than maximizing the identification of all positive cases. High precision ensures that when the model does predict an increase, it is more likely to be correct, making it more actionable for trading decisions.

To improve the model, I incorporated additional features using feature engineering:

- Daily percentage returns
- A moving average over closing prices to smooth out noise

This approach led to slightly improved performance, with a precision score of 52% and an accuracy of 49%. However, the overall performance remained poor. Both architectures suffered from overfitting, and adjusting the number of trees either led to further overfitting or worse performance.

As a result, I decided to explore more complex architectures.

## Neural Network

TODO
