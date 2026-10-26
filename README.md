# Credit Card Classification using SVM

This project uses a Support Vector Machine (SVM) to classify credit card data. The goal is to train a linear classifier, check its accuracy, and see how changing the regularization parameter affects the model.

## What is SVM?

Support Vector Machine (SVM) is a supervised machine learning algorithm used for classification and regression.

For classification, the model tries to find a decision boundary that separates observations into different classes. A linear SVM uses a straight decision boundary to separate the classes.

## How It Works

The code follows these steps:

1. **Load the data:** Read the credit card dataset from a tab-separated text file using pandas.
2. **Separate predictors and response:** Use all columns except the last one as predictors (`X`) and the last column as the response (`y`).
3. **Standardize the predictors:** Use `StandardScaler` to put the predictor variables on a comparable scale.
4. **Train the model:** Create an SVM classifier with a linear kernel and train it on the data.
5. **Make predictions:** Use the trained model to classify the observations.
6. **Check accuracy:** Compare the predictions with the actual response values using `accuracy_score`.
7. **Test different C values:** Train models with different values of `C` and compare their accuracy.
8. **Inspect the model:** Examine the predicted class counts, coefficients, and intercept.

## The C Parameter

The `C` parameter controls the trade-off between allowing classification errors and keeping the decision boundary as simple as possible.

- **Smaller C:** Allows more classification errors in exchange for a wider margin.
- **Larger C:** Penalizes classification errors more strongly, potentially producing a narrower margin.

The code tests values of `C` from 1 to 19 and stores the resulting accuracy scores in a DataFrame.

## Understanding the Coefficients

The model coefficients represent the weights assigned to the predictor variables in the linear decision function.

The intercept is the constant term in that function.

The code stores the feature names and their corresponding coefficients in a DataFrame, making it easier to inspect how the model uses the predictors.

## Requirements

- Python 3
- pandas
- scikit-learn

Install the required libraries:

```bash
pip install pandas scikit-learn
```

The dataset file `credit_card_data-headers.txt` must also be available in the working directory.

## Running the Code

Save the code in a Python file or run it in a Jupyter Notebook. Make sure the dataset is in the correct location before running it.

## What I Learned

This project helped me practice building a classification model with scikit-learn, separating predictors from the response variable, standardizing data, evaluating classification accuracy, and understanding how the SVM regularization parameter affects a model.

It also helped me understand how to inspect the coefficients and intercept of a linear classifier.

## Note

The current code evaluates accuracy on the same data used to train the model. This shows how well the model fits the training data, but it does not tell us how well it will perform on new observations. A train-test split or cross-validation would provide a better evaluation of its generalization performance.
