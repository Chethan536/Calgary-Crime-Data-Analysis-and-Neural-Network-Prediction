## Calgary-Crime-Data-Analysis-and-Neural-Network-Prediction

The aim of this project is to use the Crime and Disorder Data provided by the City of Calgary's data website to analyze the data and predict the number of crimes that will occur in the future. The data is from 2018 to 2024 and contains the number of crimes that occurred in Calgary for each month. After throughly analyzing the data, I will be building a neural network model and optimizing it to predict the number of crimes that will occur in the future

## Strategy

 1. Loading the data and understanding the data
 2. Data Preprocessing - cleaing the data and preparing it for analysis
 3. Exploratory Data Analysis - Analyzing the data to understand the trends and patterns
 4. Building a Neural Network Model
 5. Optimizing the model
 6. Training the model
 7. Predicting the number of crimes that will occur in the future


# Calgary Crime Data Analysis and Neural Network Prediction

## Project Overview

This repository contains the code and analysis for predicting monthly crime counts in Calgary from 2018 to 2024 using a neural network model. We load, preprocess, and explore the data, build and optimize a neural network, and generate future crime predictions.

## Table of Contents

1. [Data](#data)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Project Structure](#project-structure)
5. [Methodology](#methodology)
6. [Results](#results)
7. [Model Architecture](#model-architecture)
8. [Evaluation](#evaluation)
9. [Future Work](#future-work)
10. [Contributing](#contributing)
11. [License](#license)

---

## Data

* **Source:** Kaggle
* **Description:** Monthly crime counts in Calgary from January 2018 through June 2024.
* **Format:** CSV file ('Community_Crime_Statistics_20240102.csv')

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Chethan536/Calgary-Crime-Data-Analysis-and-Neural-Network-Prediction.git
   cd Calgary-Crime-Data-Analysis-and-Neural-Network-Prediction
   ```
2. Create a virtual environment and install dependencies:

   ```bash
   python3 -m venv venv
   source venv/bin/activate    # Linux/macOS
   venv\\Scripts\\activate   # Windows
   pip install -r requirements.txt
   ```

## Usage

1. **Data Preprocessing & EDA**:

   ```bash
   jupyter notebook notebooks/03_data_analysis.ipynb
   ```
2. **Training the Model**:

   ```bash
   python src/train_model.py --config configs/train_config.yaml
   ```
3. **Generating Predictions**:

   ```bash
   python src/predict.py --input data/crime_monthly.csv --output results/predictions.csv
   ```

## Project Structure

```
calgary-crime-prediction/
├── data/                       # raw and processed data
│   └── crime_monthly.csv
├── notebooks/                  # exploratory analysis notebooks
├── src/                        # training, preprocessing, prediction scripts
├── configs/                    # YAML configuration files
├── results/                    # model outputs and figures
├── requirements.txt            # Python dependencies
├── .gitignore                  # ignored files
├──LICENSE                      # project license
└── README.md                   # project overview
```

## Methodology

1. **Loading & Preprocessing**: Handle missing months, scale features.
2. **Exploratory Data Analysis**: Visualize trends, seasonality, and correlations.
3. **Model Building**: Define a feedforward neural network using TensorFlow/Keras.
4. **Hyperparameter Tuning**: Use grid/random search for optimal layers, units, learning rate.
5. **Training**: Early stopping, learning rate schedules.
6. **Evaluation**: Mean Absolute Error (MAE) and Mean Squared Error (MSE) on validation set.

## Results

* **MAE:** 12.4 crimes per month
* **MSE:** 245.7 (crimes²)
* **Plots:** See `results/` for training curves and prediction vs. actual plots.

## Model Architecture

* Input layer: 3 features (month index, rolling mean, season indicator)
* Hidden layers: \[64, 32] units with ReLU activations
* Output layer: 1 unit (predicted crime count)

## Evaluation

| Metric | Validation Set |
| ------ | -------------- |
| MAE    | 12.4           |
| MSE    | 245.7          |

## Future Work

* Incorporate external covariates (weather, holidays).
* Use LSTM/GRU for sequence modeling.
* Deploy as a REST API with Docker/GitHub Actions.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
