# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: Sai Eswar Kandukuri
RegisterNumber:  212221240020
*/
import pandas as pd
data = pd.read_csv("Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
y=data["Salary"]
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 2)
from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)
y_pred = dt.predict(x_test)
from sklearn import metrics
mse = metrics.mean_squared_error(y_test,y_pred)
mse
r2 = metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## Output:
<img width="430" alt="5_1" src="https://user-images.githubusercontent.com/93427011/169465366-42b87d3e-34ea-4310-a8ee-1a30ecd7cacf.png">
<br>
<img width="430" alt="5_2" src="https://user-images.githubusercontent.com/93427011/169465394-4375ec42-bd80-4146-b877-365a089ad408.png">
<br>
<img width="760" alt="5_3" src="https://user-images.githubusercontent.com/93427011/169465431-95547e3d-3d63-4e06-afcb-b3065e566324.png">
<br>
<img width="320" alt="5_4" src="https://user-images.githubusercontent.com/93427011/169465455-2f21768f-e6aa-464e-bfa3-58261502e1db.png">
<br>

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
