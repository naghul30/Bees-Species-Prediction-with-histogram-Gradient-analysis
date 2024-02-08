# Bees-Species-Prediction-with-Histogram analysis
## Naive Bees - Predict Species from Images

Can a machine distinguish between a honey bee and a bumble bee? Being able to identify bee species from images, while challenging, would allow researchers to more quickly and effectively collect field data. In this Project, we will use the Python image library Pillow to load and manipulate image data and then try few models to predict the species. We'll do common transformations of images and build them into a pipeline.

## Code and Resources Used 
**Python Version:** 3.10
**Packages:** pandas, numpy, sklearn, matplotlib, pickle  


## Project walk-through
1. Import Python libraries
2. Display image of each bee type
3. Image manipulation with rgb2gray
4. Histogram of oriented gradients
5. Create image features and flatten into a single row
6. Loop over images to preprocess
7. Scale features
8. Split into train and test sets
9. Perform PCA
10. Train and score various models
11. ROC curve + AUC

## Model Building 

First, I split the data into train and tests sets with a test size of 30%.   

I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is relatively easy to interpret and outliers aren’t particularly bad in for this type of model.   

I tried three different models:
*	**Logistic Regression Classifier** – Baseline for the model
*	**Logistic Regression with Liblinear solver** – Because of the sparse data from the many categorical variables, I thought `liblinear` solver should be tried upon
*   **Decision Tree**
*	**Random Forest** – Again, with the sparsity associated with the data, I thought that this would be a good fit. 
*   **Support Vector Classifier**

## Model performance
The LRegression with liblinear and SVM model far outperformed the other approaches on the test sets. 
*	**Logistic Regression Classifier** – Accuracy - 0.69
*	**Logistic Regression with Liblinear solver** – 0.72
*   **Decision Tree** - Accuracy = 0.54
*	**Random Forest** – Accuracy - 0.62
*   **Support Vector Classifier** – Accuracy - 0.64

## Future works - Trying out Neural Net models and Productionization 
In future, one can further improve the prediction by trying out a neural network model and hypertune its parameters. Also, to ensure smooth interface a flask API endpoint can be hosted on a local webserver. This endpoint would accept a list of images of bees and returns its species.


