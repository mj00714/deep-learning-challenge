# deep-learning-challenge

### Overview
For this exercise, I set out to use machine learning and a neural network to predict the success of venture funding. 

I was provided a large csv file as the basis of the analysis. These are the steps for the analysis:

### Data Processing
- Drop irrelevant columns (EIN and Name) from the dataset
- Analyze and prepare the Application_type column, bucketing less frequent values into an 'other' value (in this case, the cutoff threshold was 500 results)
- Perform the same analysis for the Classification column (the cutoff threshold for this column was 1800)
- Use the Pandas 'get_dummies' method to convert the remaining columns to numerical values
- Split the data into features and target arrays (y= 'Is_Successful', X= features)
- Utilize the StandardScalar to normalize the data

#### Data Processing Questions
- What variable is the target for the model: The 'IS_SUCCESSFUL' column is the target variable
- What variables are the features for the model: All remaining columns (except the drop columns 'EIN' and 'Name') are the features
- What variables should be removed from the input data: EIN and Name

### Compiling, Training and Evaluating the Model
- Define the model and create two hidden layers and an output layer
- Compile the model using the parameters from previous examples
- Train the model using 100 epochs
- Perform an evaluation of the model with the test data
- Export the data into an h5 file

#### Compiling, Training, Evaluating, Optimization Questions:
- How many neurons, layers and activation functions did you select for your neural network model? Why? A: For the first portion of the analysis, I selected two hidden layers and an output layer for my neurons. I selected the relu activation function for the hidden layers and the sigmoid function for the output layer. I did this because the relu function is useful for modeling positive, non-linear data and the sigmoid function does well with normalized data that is binary (like our target). This is a good starting point to see how the model performs and leaves room for optimization.
- Were you able to achieve the target model performance? No. I had one attempt that was slightly over 74% but I could not reach 75%. 
- What steps did you take in attempts to increase the model's performance?
  - When I optimized my model through my three attempts, I tried all of the functions we reviewed. I landed on the tanh function because it provided the highest accuracy after numerous tests. I also increased the hidden layers to 4, total, and changed the neurons to 16, 8, 4 and 2, respectively. This helped to narrow the results better than other configurations.
  - I also changed the buckets for the 'Application_Type' and 'Classification' columns, both increasing and decreasing the thresholds for both columns. 
  - During my final optimization effort, I also excluded results in the 'Ask_AMT' column because there were outliers. I eliminated the top 5% of the data and it helped the accuracy of the results. 

### Results
I was able to achieve an accuracy of 73.36% with a loss measure of 55.97% for my initial attempt and an accuracy measure of 73.89% with 54.69% loss on my final attempt. 

### Summary

