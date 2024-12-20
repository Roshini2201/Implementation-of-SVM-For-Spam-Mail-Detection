# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages.
2. Read the given csv file and display the few contents of the data.
3. Assign the features for x and y respectively.
4. Split the x and y sets into train and test sets.
5. Convert the Alphabetical data to numeric using CountVectorizer
6. Predict the number of spam in the data using SVC (C-Support Vector Classification) method of SVM (Support vector machine) in sklearn library.
7. Find the accuracy of the model.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: ROSHINI S
RegisterNumber:212223240142 
*/
import pandas as pd
data = pd.read_csv("C:/Users/ANANDAN S/Documents/ML labs/spam.csv",encoding = 'Windows-1252')
data.head()
data.info()
data.isnull().sum()
x= data["v1"].values
y= data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 0)
from sklearn.feature_extraction.text import CountVectorizer
#CountVectorizer is a method to convert text into numerical data.the text is transformed to a sparse matrix
cv = CountVectorizer()
x_train = cv.fit_transform(x_train)
x_test = cv.transform(x_test)
from sklearn.svm import SVC
svc = SVC()
svc.fit(x_train, y_train)
y_pred = svc.predict(x_test)
y_pred
from sklearn.metrics import accuracy_score,confusion_matrix,classification_report
acc = accuracy_score(y_test,y_pred)
acc
con = confusion_matrix(y_test,y_pred)
print(con)
cl = classification_report(y_test,y_pred)
print(cl)
```

## Output:
data.head()

![380595188-d4d9e774-6657-4d59-97c0-6f49c25dcab5](https://github.com/user-attachments/assets/38585738-40ca-49b5-888e-6db45cbfcd17)

data.info()

![380595229-5d3917c4-4f1e-4246-ba20-9aab720bd25f](https://github.com/user-attachments/assets/452f1fe3-249e-4f32-9e85-adc9a3ef9418)

data.isnull.sum()

![380595315-2dc990f7-ff05-4a0f-a458-38ed2947a720](https://github.com/user-attachments/assets/f16a75bc-3134-4bde-81ba-d4ff51c9dd6b)

y_prediction value

![380595377-70876684-9870-4814-bbb1-e8d66f8decfc](https://github.com/user-attachments/assets/992d6ca4-706e-4e3e-8668-db6c3139f5a2)

Accuracy value

![380595407-18b26772-021b-414a-aa64-3fd069e1c39c](https://github.com/user-attachments/assets/69d2e226-d797-4a6b-8566-dfad1daf0001)


## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
