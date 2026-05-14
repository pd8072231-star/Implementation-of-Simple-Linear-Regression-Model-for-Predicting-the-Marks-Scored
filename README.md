# Implementation-of-Simple-Linear-Regression-Model-for-Predicting-the-Marks-Scored

## AIM:
To write a program to predict the marks scored by a student using the simple linear regression model.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import required libraries and create dataset using pandas DataFrame. 

2.Split data into input (Hours_Studied) and output (Marks_Scored), then divide into training and testing sets. 

3.Train the Linear Regression model using training data and predict results for test data. 

4.Evaluate model performance using MSE and R² score, then visualize results using a scatter plot and regression line

## Program:
```
/*
Program to implement the simple linear regression model for predicting the marks scored.
Developed by: P.Dharshini
RegisterNumber:  212225040071

# Import required libraries
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score


# Step 1: Create the dataset
# ------------------------------
data = {
    'Hours_Studied': [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
    'Marks_Scored':  [35, 40, 50, 55, 60, 65, 70, 75, 80, 85]
}

df = pd.DataFrame(data)
print("Dataset:")
print(df)

# Step 2: Split into X and Y
# ------------------------------
X = df[['Hours_Studied']]   # Feature (2D)
y = df['Marks_Scored']      # Target (1D)


# Step 3: Split data for training & testing
# ------------------------------
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Step 4: Create and train the model
# ------------------------------
model = LinearRegression()
model.fit(X_train, y_train)


# Step 5: Make predictions
# ------------------------------
y_pred = model.predict(X_test)


# Step 6: Evaluate the model
# ------------------------------
print("\nModel Evaluation:")
print("Slope (m):", model.coef_[0])
print("Intercept (c):", model.intercept_)
print("Mean Squared Error:", mean_squared_error(y_test, y_pred))
print("R² Score:", r2_score(y_test, y_pred))

# Step 7: Visualize results
# ------------------------------
plt.scatter(X, y, color='blue', label='Actual Data')
plt.plot(X, model.predict(X), color='red', label='Regression Line')
plt.xlabel('Hours Studied')
plt.ylabel('Marks Scored')
plt.title('Simple Linear Regression: Hours vs Marks')
plt.legend()
plt.show()

# Step 8: Predict for new data
# ------------------------------
hours = float(input("\nEnter number of study hours: "))
predicted_marks = model.predict([[hours]])
print(f"Predicted Marks for studying {hours} hours = {predicted_marks[0]:.2f}")

*/
```

## Output:
![simple linear regression model for predicting the marks scored](sam.png)
<img width="1918" height="1079" alt="image" src="https://github.com/user-attachments/assets/914ebded-03b1-4fde-93db-54eab4286f62" />
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b43ec3d8-8393-424f-8176-41296d1aec15" />




## Result:
Thus the program to implement the simple linear regression model for predicting the marks scored is written and verified using python programming.
