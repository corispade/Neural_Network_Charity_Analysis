# Neural Network Charity Analysis

# Overview

Alphabet Soup is a philanthropic organization dedicated to helping organizations protect the environment, improve wellbeing, and unify the world. They have raised money over the past 20 years to invest in life saving technologies and organized reforestation groups around the world. We will help to analyze the impact of each donation and vet potential recipients by designing and training a deep learning neural network to evaluate input data and prodce a clear decision making result to determine which organizations should receive donations. 

## Process:

### Deliverable 1: Preprocessing the data
Review code [here](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity.ipynb) for Deliverable 1 and 2
* Read in the data and determine target and feature variables for the model
* Drop unnecessary columns
* Determine number of unique values and bin columns that have more than 10 unique values
* Encode categorical variables using "one-hot encoding" and create new dataframe
* Merge dataframes and drop original categorical columns
* Split preprocessed data to features and target arrays
* Split preprocessed data to training and testing data sets
* Standardize numerical variables using the "StandardScaler" and scale data

### Deliverable 2: Compile, Train and Evaulate the Model
* Create neural network and assign number input features and nodes for each layer using Tensorflow Keras
* Create first and second hidden layers with activation functions
* Create output layer with activation function
* Check structure of the model
* Compile and train the model
* Save model weights every 5 epochs
* Evaluate model using test data to determine loss and accuracy
* Save and export results to HDF5 file

### Deliverable 3: Optimize the Model
Review code [here](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/AlphabetSoupCharity_Optimization.ipynb) for Deliverable 3
* Adjust input data to ensure there are no variables or outliers causing confusion in the model
* Add more neurons to a hidden layer
* Add more hidden layers
* Use different activation functions for the hidden layers


## Resources:
Data Source: [charity_data.csv](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Resources/charity_data.csv)

Software: Python 3.7.6, Conda 4.10.1

Environment: Jupyter Notebook

Dependencies: Pandas, Scikit-Learn, Tensorflow


# Results:

### Data Preprocessing
* Our target variable is the IS_SUCCESSFUL column. We are using our machine learning model to accurately predict if the charitable donation is used effectively.

* We used the following columns as our features for our model: APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, INCOME_AMT, SPECIAL_CONSIDERATIONS, and ASK_AMT

* We dropped the EIN and NAME columns as these were not needed for our model.

### Compiling, Training, and Evaluating the Model
Base Model: We used 2 hidden layers with 80 neurons in the first layer and 30 neurons in the second layer. Our hidden layers used the Relu activation function and our output layer used the Sigmoid activation function.

![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Base_Model.png)

Our target model performance accuracy is 75%. Using the above neural network model, our model had a 72.5% accuracy.

![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Base_Acc.png)

To increase the model performance we binned ASK_AMT to reduce noise and then ran 4 different tests:
Test 1: Additional neurons added to the hidden layers - Resulted in 72.5% accuracy

![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Model_1.png)
![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Test_1.png)

Test 2: Additional hidden layers added - Resulted in 72.6% accuracy

![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Model_2.png)
![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Test_2.png)

Test 3: Activation function of hidden layers changed - Resulted in 72.7% accuracy

![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Model_3.png)
![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Test_3.png)

Test 4: Additional hidden layers added and activation function of hidden layers changed  - Resulted in 72.6% accuracy

![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Model_4.png)
![image](https://github.com/corispade/Neural_Network_Charity_Analysis/blob/main/Images/Test_4.png)


# Summary:
After attempting to optimize this neural network model and running many different iterations, I was unable to achieve our target accuracy of 75%. By changing the activtion function of the hiddel layers, I reached a 72.7% accuracy. 

To improve accuracy and attempt to achieve our 75% target accuracy, I would suggest to attempt a Random Forest Classifier. This is a powerful model that combines multiple smaller models into a more robust and accurate model. Since our data does not contain images, we can easily preprocess our tabular data to work for this model. 