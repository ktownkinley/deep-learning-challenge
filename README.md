# NN Model Report

## Overview

The purpose of this analysis was to find a model that would give a 75% or higher accuracy predicting the success of charities based on a wide range of input data. The goal was to find an ideal set of input data (dropping columns that are deemed not valuable to the output) as well as finding the best set of parameters for the model to achieve the 75% or higher accuracy of the model.

## Results

- Data preprocessing
  - The "IS_SUCCESSFUL" column in the data was the target for the model
  - After dropping the "EIN" and "NAME" columns, the rest of the columns present in the data were the features of the model
  - The "EIN" and "NAME" columns were removed from the data as they are unique to each row of data and have no predictive correlation with the target

- Compiling, training and evaluating the model
  - The model with the best results used an input layer with 275 neurons, 4 hidden layers with layer_0: 30 neurons, layer_1: 50 neurons, layer_2: 95 neurons, layer_3: 100 neurons, and the "relu" activation function. The results were the best when using the Keras Tuner with quite a large set of parameters. The relu function was tested alongside the tanh function and was found to be the better option on 8 of the top 10 trials.
  - I was unable to achieve the target model performance of >75% accuracy. I believe the proper parameters were not found, but the largest reason for the inaccuracy was due to the input data not being cleaned in the proper configuration.
  - I attempted to drop different columns and also attempted to consolidate the columns with the most unique values into different numbers of buckets. I also tried adjusting the number of hidden layers, the number of neurons in each layer and using a different activation function.

- Summary
  - The overall result of each model was within 2% of each other. Each model that was attempted had various input/parameter differences but the accuracy delta was extremely small. 
  - The type of model used, namely the Sequential Model, could be swapped out for the general Keras Model, and a model that incorporates multi-input networks could be utilized.