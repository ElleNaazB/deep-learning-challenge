# Goal and Overview

The goal of this project is to develop a tool for the nonprofit foundation Alphabet Soup that can predict the success of applicants it funds. By leveraging machine learning and neural networks, the project aims to create a binary classifier to assess the likelihood of applicant success based on features from a dataset containing over 34,000 organizations that have previously received funding. This project involves preprocessing the data, compiling, training, and evaluating the model, followed by attempts to optimize the model to achieve a predictive accuracy higher than 75%. 

## Data Preparation Steps

 **Target Variable :** This project aims to predict `IS_SUCCESSFUL`.

 **Featured Variables for this model :** All columns except `EIN`, `NAME`, which have been removed. The `SPECIAL_CONSIDERATIONS` column is also excluded in the attempts for optimization since it contains a few  'YES' values, thus not beneficial for the analysis.
 

# Neural Network Optimization Attempts

This document provides a detailed justification and reasoning for the different attempts made to optimize a neural network for a classification problem. The goal was to achieve an accuracy of at least 75%.

## First Attempt
- **Application Types' Cut Off**: 500
- **Classification's Cut Off**: 1000
- **First Layer Units**: 80 | Activation: ReLU
- **Second Layer Units**: 30 | Activation: ReLU
- **Third Layer Units**: 1 | Activation: Sigmoid
- **Accuracy**: 0.7261

### Reasoning
- The initial setup was based on a moderate configuration for the neural network. The cut-off values for `application_types` and `classification` were chosen to include a significant portion of the data while filtering out noise.
- The number of units in the layers was selected to provide sufficient capacity for learning complex patterns in the data.
- The ReLU activation function was used for the hidden layers to ensure non-linearity and efficient gradient propagation, while the sigmoid function was used in the output layer for binary classification.

### Outcome
- The model achieved an accuracy of approximately 72.61%, which was below the desired threshold of 75%.

## Second Attempt
- **Application Types' Cut Off**: 1200
- **Classification's Cut Off**: 100
- **First Layer Units**: 45 | Activation: ReLU
- **Second Layer Units**: 25 | Activation: ReLU
- **Third Layer Units**: 1 | Activation: Sigmoid
- **Accuracy**: 0.7227

### Reasoning
- In this attempt, the cut-off for `application_types` was increased significantly to include more data points, while the `classification` cut-off was reduced to focus on a narrower set of data.
- The number of units in the layers was reduced to potentially decrease the model complexity and overfitting.
- The same activation functions were used to maintain the non-linearity and classification capability.

### Outcome
- Despite the changes, the accuracy slightly decreased to approximately 72.27%. This suggested that the adjustments did not effectively improve the model's performance.

## Third Attempt
- **Application Types' Cut Off**: 100
- **Classification's Cut Off**: 200
- **First Layer Units**: 120 | Activation: ReLU
- **Second Layer Units**: 40 | Activation: Tanh
- **Third Layer Units**: 1 | Activation: Sigmoid
- **Accuracy**: 0.7254

### Reasoning
- For the third attempt, the cut-offs were set to different values to test another combination of data inclusion and exclusion.
- The number of units in the first layer was significantly increased to allow the network to learn more complex representations.
- The activation function for the second layer was changed to Tanh, which can sometimes offer better performance for certain datasets by centering the data and potentially smoothing the gradients.
- The sigmoid activation was retained for the output layer.

### Outcome
- The accuracy was 72.54%, showing no substantial improvement. The model did not meet the desired threshold of 75%, indicating that these specific changes were also ineffective.

## Conclusion
Despite multiple attempts to adjust the neural network's parameters and cut-off values, the model consistently achieved around 72% accuracy. This indicates that further optimization or a different approach may be necessary. Possible next steps include experimenting with different feature engineering techniques, trying other model architectures, or using advanced optimization algorithms to improve performance.



