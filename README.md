# Goal and Overview

The goal of this project is to develop a tool for the nonprofit foundation Alphabet Soup that can predict the success of applicants it funds. By leveraging machine learning and neural networks, the project aims to create a binary classifier to assess the likelihood of applicant success based on features from a dataset containing over 34,000 organizations that have previously received funding. This project involves preprocessing the data, compiling, training, and evaluating the model, followed by attempts to optimize the model to achieve a predictive accuracy higher than 75%. 

## Data Preparation Steps

 **Droping Unnecessary Columns** Remove columns that are not beneficial for the analysis.
 
**Counting Unique Values** For columns with more than 10 unique values (specifically, `APPLICATION_TYPE` and `CLASSIFICATION`), count the number of occurrences for each unique value.

**Bin Rare Values**  Combining rare values into a new category called "Other".And use a cutoff of 600 for `APPLICATION_TYPE` and 300 for `CLASSIFICATION`.

**Converting Categorical to Numeric** Using `pd.get_dummies()` to convert categorical columns into numeric format.

**Spliting Data** Separating the target variable (`IS_SUCCESSFUL`) from the feature variables.

**Train-Test Split**  Dividing the data into training and testing sets using `train_test_split`.

**Scale Data** Using `StandardScaler` to scale the features in the training and testing sets.



### First Attempt:
- Application Types Cut-off: 500
  
Application types with fewer than 500 occurrences were grouped into an "Other" category to reduce the number of unique application types.

- Classification Cut-off: 1000
  
Classifications with fewer than 1000 occurrences were grouped into an "Other" category to reduce the number of unique classifications.

### Neural Network Architecture

The neural network model was configured with the following layers:

- First Layer:
Units: 80
Activation Function: ReLU (Rectified Linear Unit)
- Second Layer:
Units: 30
Activation Function: ReLU
- Third Layer:
Units: 1
Activation Function: Sigmoid

The model was trained with a batch size of 32 and for 100 epochs, using a validation split of 20% of the training data.

### Performance
Accuracy: 0.7261 (72.61%)

The current model achieved an accuracy of approximately 72.61%. However, the target accuracy was set at 75%. Therefore, further improvements and iterations are necessary to reach the desired performance.

## Second Attempt:
### Data Preprocessing
- **Application Types Cut-off**: 1200
- **Classification Cut-off**: 100
### Neural Network Architecture
1. **First Layer**:
   - **Units**: 45
   - **Activation**: ReLU
2. **Second Layer**:
   - **Units**: 25
   - **Activation**: ReLU
3. **Third Layer**:
   - **Units**: 1
   - **Activation**: Sigmoid
### Performance
- **Accuracy**: 0.7227 (72.27%)
## Third Attempt:
### Data Preprocessing
- **Application Types Cut-off**: 100
- **Classification Cut-off**: 200
### Neural Network Architecture
1. **First Layer**:
   - **Units**: 120
   - **Activation**: ReLU
2. **Second Layer**:
   - **Units**: 40
   - **Activation**: Tanh
3. **Third Layer**:
   - **Units**: 1
   - **Activation**: Sigmoid
### Performance
- **Accuracy**: 0.7254 (72.54%)


After three attempts, the model did not reach a predictive accuracy higher than 72.8%. Hyperparameter tuning had little effect. Perhasp other methods of preprocessing, feature engineering, or advanced model architectures are needed to improve performance.


