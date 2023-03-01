# Neural Network Charity Analysis

## Analysis Overview
The purpose of this project is to use deep-learning neural networks with the TensorFlow platform in Python, to analyze and classify the success of charitable donations.\
We use the following methods for the analysis:
- preprocessing the data for the neural network model,
- compile, train and evaluate the model,
- optimize the model.

## Resources
- Data Source: [charity_data.csv](https://github.com/Hanzian/Neural_Network_Charity_Analysis/blob/main/charity_data.csv)
- Software: Python 3.9.12, Anaconda Navigator 1.11.0, Conda 23.1.0, Jupyter Notebook 6.5.2

## Results

### Data Preprocessing
- The columns `EIN` and `NAME` are identification information and have been removed from the input data.
- The column `IS_SUCCESSFUL` contains binary data refering to weither or not the charity donation was used effectively. This variable is then considered as the target for our deep learning neural network.
- The following columns `APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT` are the features for our model.\
Encoding of the categorical variables, spliting into training and testing datasets and standardization have been applied to the features.

### Compiling, Training, and Evaluating the Model
- This deep-learning neural network model is made of two hidden layers with 80 and 30 neurons respectively.\
The input data has 43 features and 25,724 samples.\
The output layer is made of a unique neuron as it is a binary classification.\
To speed up the training process, we are using the activation function `ReLU` for the hidden layers. As our output is a binary classification, `Sigmoid` is used on the output layer.\
For the compilation, the optimizer is `adam` and the loss function is `binary_crossentropy`.

![](https://github.com/Hanzian/Neural_Network_Charity_Analysis/blob/main/Images/Screenshot%202023-03-01%20at%2011.10.34%20AM.png)

- The model accuracy is under 75%. This is not a satisfying performance to help predict the outcome of the charity donations.

![Accuracy](https://github.com/Hanzian/Neural_Network_Charity_Analysis/blob/main/Images/Accuracy.png)


### Optimization
To increase the performance of the model, we applied bucketing to the feature and organized the different values by intervals.\
We increased the number of neurons on one of the hidden layers, then we used a model with three hidden layers.\

![](https://github.com/Hanzian/Neural_Network_Charity_Analysis/blob/main/Images/Optimization.png)

![](https://github.com/Hanzian/Neural_Network_Charity_Analysis/blob/main/Images/Optimization%20Accuracy%20.png)

## Summary
The deep learning neural network model did not reach the target of 75% accuracy. Considering that this target level is pretty average we could say that the model is not outperforming.\
Since we are in a binary classification situation, we could use a supervised machine learning model such as the Random Forest Classifier to combine a multitude of decision trees to generate a classified output and evaluate its performance against our deep learning model.
