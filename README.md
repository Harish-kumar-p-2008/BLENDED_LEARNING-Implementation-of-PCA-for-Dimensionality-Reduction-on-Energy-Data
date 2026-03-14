# BLENDED LEARNING
# Implementation of Principal Component Analysis (PCA) for Dimensionality Reduction on Energy Data

## AIM:
To implement Principal Component Analysis (PCA) to reduce the dimensionality of the energy data.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import Libraries: Bring in the necessary libraries such as NumPy, Pandas, Matplotlib, and Scikit-learn.
2. Load the Dataset: Load the dataset that contains multiple features which may have high dimensionality.
3. Data Preprocessing: Check for missing values, clean the dataset if necessary, and normalize or standardize the data to ensure all features are on the same scale.
4. Define Features: Separate the dataset into feature variables (X) that will be used for dimensionality reduction.
5. Standardize the Data: Apply feature scaling using standardization so that each feature has a mean of 0 and standard deviation of 1.
6. Apply PCA Model: Initialize the Principal Component Analysis (PCA) model and specify the number of principal components to retain.
7. Fit the Model: Fit the PCA model to the standardized dataset to identify the directions of maximum variance.
8. Transform the Data: Reduce the dimensionality of the dataset by transforming the original features into principal components.
9. Analyze Variance: Examine the explained variance ratio to understand how much information is retained by the selected components.
10. Visualize the Reduced Data: Plot the transformed data to visualize the dataset in fewer dimensions.
## Program:
```
/*
Program to implement Principal Component Analysis (PCA) for dimensionality reduction on the energy data.
Developed by: Harish Kumar P
RegisterNumber:  25006070

import pandas as pd
from sklearn.preprocessing import StandardScaler
from sklearn.decomposition import PCA
import matplotlib.pyplot as plt
import seaborn as sns

data=pd.read_csv("HeightsWeights.csv")

print("First 5 rows of the dataset:")
print(data.head())

x = data[['Height(Inches)','Weight(Pounds)']]

plt.figure(figsize=(6,5))
sns.scatterplot(x='Height(Inches)',y='Weight(Pounds)',data=data)
plt.title("Original Data Distribution")
plt.show()

scaler = StandardScaler()
x_scaled =  scaler.fit_transform(x)

pca = PCA(n_components=2)
x_pca = pca.fit_transform(x_scaled)

print("Explained Variance Ratio:",pca.explained_variance_ratio_)

pca_df = pd.DataFrame(x_pca,columns=['PC1','PC2'])

plt.figure(figsize=(6,5))
sns.scatterplot(x='PC1',y='PC2',data=pca_df)
plt.title("PCA Projection of Height and Weight")
plt.xlabel("Principal Component 1")
plt.ylabel("Principal Component 2")
plt.show()

*/
```

## Output:
![alt text](<Screenshot 2026-03-14 093739.png>)
![alt text](<Screenshot 2026-03-14 093749.png>)
![alt text](<Screenshot 2026-03-14 093757.png>)
![alt text](<Screenshot 2026-03-14 093805.png>)


## Result:
Thus, Principal Component Analysis (PCA) was successfully implemented to reduce the dimensionality of the energy dataset.
