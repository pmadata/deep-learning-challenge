# deep-learning-challenge

## AlphabetSoupCharity Neural Network Model
## Introduction
This repository contains code for building and training neural network models to predict the success of charity organizations based on certain features. The dataset used for this task is charity_data.csv, and the goal is to predict whether a charity organization will be successful (1) or not (0).

## Dataset
The dataset consists of various features including APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, and others. The target variable is IS_SUCCESSFUL, indicating the success (1) or failure (0) of the charity organization.

## Preprocessing
The preprocessing steps applied to the dataset include:

Dropping unnecessary columns (EIN, NAME).
Binning values in the APPLICATION_TYPE column to reduce the number of unique categories.
Binning values in the CLASSIFICATION column based on a cutoff value.
Converting categorical data to numeric using one-hot encoding.
Scaling the data using StandardScaler.

Defined target for this model : "IS_SUCCESSFUL"
Defined features for this model: STATUS,	ASK_AMT, APPLICATION_TYPE_Other 1,	APPLICATION_TYPE_Other 2,	APPLICATION_TYPE_T19,	APPLICATION_TYPE_T3,	APPLICATION_TYPE_T4,	APPLICATION_TYPE_T5,	APPLICATION_TYPE_T6,...	INCOME_AMT_1-9999,	INCOME_AMT_10000-24999,	INCOME_AMT_100000-499999,	INCOME_AMT_10M-50M,	INCOME_AMT_1M-5M,	INCOME_AMT_25000-99999,	INCOME_AMT_50M+,	INCOME_AMT_5M-10M,	SPECIAL_CONSIDERATIONS_N,	SPECIAL_CONSIDERATIONS_Y;

## Model Architecture
### Initial Model
The initial neural network model architecture consists of an input layer, two hidden layers with 16 units each, and an output layer with a single neuron using the sigmoid activation function.
The optimizer used is Adam, and the loss function is binary cross-entropy.

### Model Optimization
2 main optimizations with 3 aditional sub-optimization steps were explored:
1) No changes and run for 100 epochs initial model;
2) Drop Additional Columns to mantain only 2 initial features: (STATUS, SPECIAL_CONSIDERATIONS_N, SPECIAL_CONSIDERATIONS_Y, ASK_AMT) were dropped, 
    2.1) Run for 25 Epochs.
    2.2) Run for 100
    2.3) Run for 150 Epochs

### Model Evaluation
Model performance was evaluated using the test data after each training session.
Evaluation metrics used are loss and accuracy.

## Results and Analysis
Initial Model Performance at 50 epochs:
Loss: [0.558]
Accuracy: [0.724]

Option 1 (Run 100 Epochs):
Loss: [0.559]
Accuracy: [0.725]

Option 2.1 (Drop Additional Columns, Run for 25 Epochs):
Loss: [0.060]
Accuracy: [0.723]

Option 2.2 (Drop Additional Columns, Run for 100 Epochs):
Loss: [Loss 0.559]
Accuracy: [0.724]

Option 2.3 (Drop Additional Columns, Run for 150 Epochs):
Loss: [Loss 0.558]
Accuracy: [0.726]

## Analysis
The initial model achieved 72.4% accuracy on the test data.
Option 1 showed 72.5% accuracy after training for 100 epochs, indicating no substantial improvement compared to the initial model.
The same goes for Option 2, where improve could only be seen slighly from 72.4% to 72.6% when running 150 epochs.

### Conclusion
In conclusion, the neural network models show not optimal performance on predicting success based on the selected features and optimization strategies. Further tuning and experimentation might be necessary to achieve the desired level of accuracy. Potentially selecting different features or adjusting further binning strategy. A potential alternative for this model would have been to use random forest as it would work well with both numberical and categorical data without the need for extensive preprocessing.  