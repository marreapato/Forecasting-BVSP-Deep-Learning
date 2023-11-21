# Brazilian Stock Market Index Forecasting with Deep Learning and XAI

Welcome to our project repository! This project was developed as part of the Master's degree program in Computer Science at the Federal University of Pernambuco. In this repository, we present our work on forecasting the Brazilian stock market index using Deep Learning techniques and eXplainable Artificial Intelligence (XAI) methods to interpret and explain the forecasts.

## Table of Contents

- [Introduction](#introduction)
- [Project Overview](#project-overview)
- [Installation](#installation)
- [Usage](#usage)
- [Data](#data)
- [Methods](#methods)
- [Results](#results)
- [Contributors](#contributors)
- [License](#license)

## Introduction

In the realm of financial markets, predicting stock market indices is a challenging and critical task. This project aims to leverage the power of Deep Learning and XAI techniques to make accurate forecasts of the Brazilian stock market index. Our focus is not only on making predictions but also on providing transparent and interpretable explanations for those predictions.

## Project Overview

In this repository, you will find:

- Python code for our Deep Learning models and XAI methods.
- Jupyter notebooks illustrating the entire data preprocessing, model training, and explanation generation pipeline.
- Data sources and data preprocessing scripts.
- Documentation and tutorials on how to use our code and replicate our experiments.

## Installation

To get started, you'll need to set up your environment and install the necessary dependencies. Here's how you can do it:

```bash
import yfinance as yf
import numpy as np
import pandas as pd
from sklearn.preprocessing import MinMaxScaler
from keras.models import Sequential
from keras.layers import Dense, LSTM, GRU# captum (biblioteca de interpretação pytorch)
import matplotlib.pyplot as plt
from sklearn.metrics import mean_squared_error

# Download data for the stock (I'm using the Bovespa index as an example)
data = yf.download('^BVSP', '2007-01-01', '2023-10-17')
data = data[['Close']]

```

## Usage

We've designed this project with ease of use in mind. You can find example notebooks and scripts in the `examples/` directory that demonstrate how to train models, make forecasts, and generate explanations.

For a quick start, you can run the following commands:

- To train a model: `python train_model.py`
- To make predictions: `python make_predictions.py`
- To generate explanations: `python generate_explanations.py`

## Data

Our project relies on historical financial data. We have used data from reputable sources, and you can find details in the `data/` directory.

We strongly encourage users to respect data licensing and usage restrictions when working with financial data.

## Methods

We have employed various Deep Learning techniques, including recurrent neural networks (RNNs), convolutional neural networks (CNNs), and hybrid models. Additionally, we have used XAI methods like SHAP (SHapley Additive exPlanations) to provide insights into model predictions.

## Results

Our results and findings are documented in the `results/` directory. We present evaluation metrics, visualizations, and interpretations of our models' predictions. We hope you find our results insightful and informative.

## Contributors

- [Lucas Rabelo](https://github.com/marreapato)
- [Eliaquim Moreira](https://github.com/marreapato)

We welcome contributions, feedback, and collaboration from the community. Feel free to open issues and pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Thank you for exploring our project! We hope our work inspires and assists you in your deep learning and financial forecasting endeavors. If you have any questions or suggestions, please don't hesitate to reach out. Happy forecasting! 📈✨
