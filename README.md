# Neural_Network_Charity_Analysis

## Overview
The purpose of this analysis is to use Neural Network models to predict whether applicants will be successful if they are funded by Alphabet Soup.

## Data Preprocessing
1) The target for the model is "IS_SUCCESSFUL" i.e. whether the applicants will be successful or not.
2) The "EIN" and "Name" of the applicants are neither features nor targets and are dropped during preprocessing.
3) The features of the three optimization models used are as follows:

### Optimization #1 and #2:
The target column is dropped, so are the "Status" and "Special Considerations" columns.

![opt#1_features](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%231_features.png)

### Optimization #3:
In addition to the columns dropped in Optimizations #1 and #2, the "Affiliation" column is dropped as well.

![opt#3_features](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%233_features.png)

## Compiling, Training and Evaluating the Model
1) In trying to optimize the model, a variety of number of neurons, layers and activation functions are tested. They are listed below:

### Optimization #1:
- Two hidden layers are used with 100 and 40 neurons respectively
- The ReLu activation function is used for the two hidden layers
- The sigmoid activation function is used for the output layer

![opt#1 model](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%231_model.png)

### Optimization #2:
- Two hidden layers are used with 160 and 50 neurons respectively
- The ReLu activation function is used for the two hidden layers
- The sigmoid activation function is used for the output layer

![opt#2 model](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%232_model.png)

### Optimization #3:
- Three hidden layers are used with 80, 30, and 10 neurons respectively
- The ReLu activation function is used for the hidden layers
- The tanh activation function is used for the output layer

![opt#3 model](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%233_model.png)

2) The target model accuracy of 75% was not achieved despite the changes described above and in addition to the following changes made to the original model:

### Optimization #1:
- Reducing the number of bins of the application types by increasing the count from < 200 to < 1000
- Reducing the number of bins of the classification types by increasing the count from < 1500 to < 2000

### Optimization #2:
- Reducing the number of bins of the application types by increasing the count from < 200 to < 10000
- Reducing the number of bins of the classification types by increasing the count from < 1500 to < 5000
- Increasing the number of epochs during training to 250

### Optimization #3:
- Reducing the number of bins of the application types by increasing the count from < 200 to < 10000
- Reducing the number of bins of the classification types by increasing the count from < 1500 to < 5000

## Summary
Using the original model, an accuracy of 72.5% was achieved

![origmodel results](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Origmodel_results.png)

Optimization #1 had the next highest accuracy rate of 72.4% followed by Optimization #2 (70.8%) and Optimization #3 (61.7%)

![opt#1 model results](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%231_results.png)

![opt#2 model results](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%232_results.png)

![opt#3 model results](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%233_results.png)

### Recommendation
It does not appear that adding more layers, neurons and epochs improve the accuracy. The next iteration recommended is as follows:
- Use the bins in Optimization #2 for Application Types and Classification as the numbers in one category in each of the Application Types and Classification are very large compared to the rest of the bins. This will hopefully get rid of the outliers.
- Keep to two hidden layers with 80 and 30 neurons respectively as increasing the layers and number of neurons do not appear to have a positive impact on the accuracy rate.
- Keep to the sigmoid activation function for the output layer as this is the function most ideal for binary classification, which is what we are trying to predict.

Alternatively, the SVM model can be trialed to determine if a comparable or better accuracy rate can be achieved. SVM is designed to classify data into two classes. Since we are trying to determine whether an applicant is successful or not, the SVM model might be ideal.

 

