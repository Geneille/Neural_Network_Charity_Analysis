# Neural_Network_Charity_Analysis

## Overview and Objectives

Neural networks (also known as artificial neural networks, or ANN) are a set of algorithms that are modeled after the human brain. They are an advanced form of machine learning that recognizes patterns and features in input data and provides a clear quantitative output. The main objective of this project was to create a binary classifier that is capable of predicting whether applicants will be successful if funded by the investment company Alphabet Soup.

The dataset is a CSV file containing more than 34,000 organizations that have received funding from Alphabet Soup over the years. Within this dataset are a number of columns that capture metadata about each organization.

## Results

#### Data Preprocessing

1. What variable(s) are considered the target(s) for your model?
* For this model, the target variable is 'IS_SUCCESSFUL' field.

2. What variable(s) are considered to be the features for your model?

* The features  used for the model include: organization, status, income_amt, special_considerations, ask_amt, application_type, affilitation, classification.

3. What variable(s) are neither targets nor features, and should be removed from the input data?
* The variable(s) removed from input data was 'name' and 'EIN'.
* Additionally,  Ask_amt was later deleted to determine if it had any impact on model performance. That is, in an effort to improve model accuracy the ask_amt was removed from the feature list in an attempt to optimize the model.

#### Compiling, Training, and Evaluating the Model

1. How many neurons, layers, and activation functions did you select for your neural network model, and why?
* Initially, the number of input features and hidden nodes used was:

   - number_input_features = 43 (number of trained scaled features) 
   - hidden_nodes_layer1 = 20
   - hidden_nodes_layer2 = 10

There is no specifics/agreement among data scientist as to how much nodes should be placed in a hidden layer. However, a quick review of the literature suggest that a good starting point would be to use half of input feature for the first layer, and half of the first layer in the second layer. 

2. Were you able to achieve the target model performance? What steps did you take to try and increase model performance?

The target model performance was an accuracy score of 75%. Below is a summary of the accuracy scores from the inital model and the steps taken to optimize the model.

* Initial model configuration:
    - number_input_features = 43
    - hidden_nodes_layer1 = 20
    - hidden_nodes_layer2 = 10
    - First hidden layer activation function: relu
    - Second hidden layer activation function: relu
    - Output layer activation function: sigmoid

    The model performancece is displayed in figure 1 below. As can be observed the accuracy score achieved was 72.9%.
    
    Figure 1.
    
    <img width="427" alt="figure 1" src="https://user-images.githubusercontent.com/92636438/159158095-0b0f250b-83db-4d2f-bc74-b621255a6268.png">


* First optimization attempt - ASK_AMT was removed as a feature. Model configuration:
    - number_input_features = 42
    - hidden_nodes_layer1 = 20
    - hidden_nodes_layer2 = 10
    - First hidden layer activation function: relu
    - Second hidden layer activation function: relu
    - Output layer activation function: sigmoid

    The model performancece is displayed in figure 2 below. As can be observed the accuracy score achieved was also 72.9%.
    
    Figure 2.
    
    <img width="426" alt="2" src="https://user-images.githubusercontent.com/92636438/159158129-945ed940-9d5d-4e6a-8034-753594bddbe5.png">


* Second optimization attempt - ASK_AMT was removed as a feature & activation function changed. Model configuration:
    - number_input_features = 42
    - hidden_nodes_layer1 = 20
    - hidden_nodes_layer2 = 10
    - First hidden layer activation function: relu
    - Second hidden layer activation function: sigmoid
    - Output layer activation function: sigmoid

    The model performancece is displayed in figure 3 below. As can be observed the accuracy score achieved was 73.1%.
    
    Figure 3.
    
    <img width="426" alt="3" src="https://user-images.githubusercontent.com/92636438/159158159-b610bc07-ad15-4acd-811d-6603c67efa89.png">


* Third optimization attempt - ASK_AMT was removed as a feature, activation function changed and number of nodes changed. Model configuration:
    - number_input_features = 42
    - hidden_nodes_layer1 = 80
    - hidden_nodes_layer2 = 40
    - First hidden layer activation function: relu
    - Second hidden layer activation function: sigmoid
    - Output layer activation function: sigmoid

    The model performancece is displayed in figure 4 below. As can be observed the accuracy score achieved was 72.5%.
    
    Figure 4.
    
    <img width="442" alt="4" src="https://user-images.githubusercontent.com/92636438/159158179-610b781d-087c-4020-ab6e-7bddf50e513a.png">


## Summary 

The target performance of the model was not achieved in any of the attempts made to optimize the model. Another action that could have been taken would have been to try another hidden layer. However, literature review suggest that two hidden layers with more nodes usually work better and less demanding processing wise than three layers.

Structurally, random forest models are very similar to their neural network counterparts, and this model could have been used in place of the deep neural network. It is likely that this model may perform better than the neural network because they are a type of ensemble learning model that combines multiple smaller models into a more robust and accurate model. Random forest models use a number of weak learner algorithms (decision trees) and combine their output to make a final classification (or regression) decision. Additionally, they can easily handle outliers and nonlinear data.
