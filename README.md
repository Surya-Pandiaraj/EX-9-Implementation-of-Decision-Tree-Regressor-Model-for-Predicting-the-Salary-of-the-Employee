### NAME: SURYA P <br>
### REG NO: 212224230280

# EX 9 : IMPLEMENTATION OF DECISION TREE REGRESSOR MODEL FOR PREDICTING THE SALARY OF THE EMPLOYEE

## AIM :
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the
Employee.

## EQUIPMENTS REQUIRED :
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook


## ALGORITHM :

1.Import pandas

2.Import Decision tree classifier

3.Fit the data in the model

4.Find the accuracy score

## PROGRAM :

```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee
Developed by: SURYA P
RegisterNumber:  212224230280
*/

import pandas as pd
data=pd.read_csv("C:\\Users\\admin\\Downloads\\Salary.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
data.head()
x=data[["Position","Level"]]
x.head()
y=data[["Salary"]]
from sklearn.model_selection import train_test_split
x_train, x_test, y_train, y_test=train_test_split(x,y,test_size=0.2,random_state=2)
from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)
from sklearn import metrics
mse=metrics.mean_squared_error(y_test, y_pred)
mse
r2=metrics.r2_score(y_test,y_pred)
r2
dt.predict([[5,6]])
```

## OUTPUT :

![image](https://github.com/user-attachments/assets/445aff9e-85e7-4f2c-9791-2126286544c6)

![image](https://github.com/user-attachments/assets/63b9acd0-1e23-4516-b0cd-cf640f72ee8a)

![image](https://github.com/user-attachments/assets/62acc1a3-cf7c-4412-b95b-878929c0b9a4)

## RESULT :
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
