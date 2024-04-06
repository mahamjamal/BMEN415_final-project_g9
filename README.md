# BMEN 415 Final Project 

## Image classifcation using CNN from tensorflow

### Confusion Matrix
![confusion-matrix](image.png)

### Metrics 
![alt text](image-1.png)

### *Evaluation*
To carry out the image classification, a Convolution Neural Network was used, using TensorFlow’s sequential model framework. The original dataset consisted of three classes: malignant, benign and normal breast tissue. In the interest of time and simplification, we dropped the benign class to adopt a binary classification problem. Following this, the dataset had an imbalance which risked creating a model with bias towards the malignant breast tissue. To avoid this, 200 images were randomly selected from each class for training, and 100 from each for testing. This was the largest amount of data we were able to retain while maintaining balance and achieving an 80/20 split for training and testing. After setting up a sequential model, a CustomKerasClassifer was also instantiated in order to aid with a thorough grid search to find the best hyperparamters to optimize performance. In hindsight, conducting a grid search was computationally expensive, taking approximately an hour to run, so it may have been more beneficial to opt for a different technique, like Bayesian Optimization. Despite the computational demands the best hyperparamters were as follows:

- Optimizer: adam
- Epochs: 20
- Batch size: 64

The resulting model achieved a training accuracy of 79.8% and a testing accuracy of 78%. The slight discrepancy aligns with the bias-variance tradeoff, suggesting a modest degree of overfitting to the training data. Nonetheless, the minimal difference indicates the model generalizes well to new data. Furthermore, inspecting the F1 score reveals the model’s differential performance in identifying normal versus malignant breast tissue. Focusing on the testing scores, being 0.80 for normal tissue and 0.75 for malignant tissue, reveal a better identification of true negatives and positives for normal tissue.
