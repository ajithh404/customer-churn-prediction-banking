# Bank Customer Churn Prediction

This project involves building an Artificial Neural Network (ANN) to predict whether a customer will leave a bank, based on customer attributes provided in a dataset.

---

## Dataset

The dataset, `Churn_Modeling.csv`, contains records of 10,000 bank customers with the following columns:

- RowNumber  
- CustomerId  
- Surname  
- CreditScore  
- Geography  
- Gender  
- Age  
- Tenure  
- Balance  
- NumOfProducts  
- HasCrCard  
- IsActiveMember  
- EstimatedSalary  
- Exited  

**Objective:** Use all features to predict whether a customer will exit the bank (`Exited` column).

---

## Data Preprocessing

- Removing unnecessary features  
- Label Encoding  
- One Hot Encoding  
- Train-Test Split  
- Standard Scaler  

---

## Simple ANN Model using Keras

A simple ANN with 4 layers has been built as follows:

- One input layer with 11 input features and 6 output nodes  
- One hidden layer with 6 output nodes  
- A final output layer with 1 node  

---

## Activation Functions

- **1st layer:** Relu  
- **2nd layer:** Relu  
- **3rd layer:** Sigmoid  

---

## Hyperparameters

- **optimizer:** `adam`  
- **loss:** `binary_crossentropy`  
- **metrics:** `accuracy`  
- **batch_size:** 10  
- **epochs:** 100  

---

## Accuracy (Subject to change)

- **Training Set Accuracy:** 0.8610  
- **Testing Set Accuracy:** 0.86  

---

## Improving the ANN

To further improve the model performance and reduce variability:

### k-Fold Cross-Validation  
- Split the training set into 10 parts (folds)  
- Train on 9 folds and validate on the 10th, rotating through all folds to reduce fluctuation in accuracy across different runs

### Dropout Regularization  
- Applied the Dropout technique to reduce overfitting on the training data  
- After applying Dropout, the model achieved an accuracy of **0.8321**, indicating reduced overfitting

### GridSearchCV for Hyperparameter Tuning  
- Used `GridSearchCV` to automate the search for the best hyperparameters  
- The following parameters were tested:

#### batch_size
- 25  
- 32  

#### epochs
- 100  
- 500  

#### optimizer
- `adam`  
- `rmsprop`  

---

## Best Results Found

**best_parameters:**  
- batch_size: 25  
- epochs: 500  
- optimizer: rmsprop  

**accuracy:**  
- 0.8545  

---

## Tech Stack
- Python  
- Keras (TensorFlow backend)  
- Scikit-learn  
- Pandas  
- NumPy  

---

## Notes
- The project focuses on reducing overfitting and improving stability through cross-validation and dropout.  
- GridSearchCV helped in identifying a more optimized configuration of hyperparameters.
