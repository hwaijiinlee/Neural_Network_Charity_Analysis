# Neural_Network_Charity_Analysis

## Overview
The purpose of this analysis is to use Neural Network models to predict whether applicants will be successful if they are funded by Alphabet Soup.

## Data Preprocessing
1) The target for the model is "IS_SUCCESSFUL" i.e. whether the applicants will be successful or not.
2) The EIN and Name of the applicants are neither features nor targets and are dropped during preprocessing.
3) The features of the three optimization models used are as follows:

### Optimization #1 and #2:
The target column is dropped, so are the "Status" and "Special Considerations" columns.

[!opt#1_features](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%231_features.png)

### Optimization #3:
In addition to the columns dropped in Optimizations #1 and #2, the "Affiliation" column is dropped as well.

[!opt#3_features](https://github.com/hwaijiinlee/Neural_Network_Charity_Analysis/blob/main/Resources/Opt%233_features.png)


 

