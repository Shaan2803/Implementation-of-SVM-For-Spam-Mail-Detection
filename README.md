# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.import neccessary libraries required.

2.Load the dataset using pd.read_csv.

3.Use CountVectorizer to convert text data into a matrix of token counts.

4.Create an SVM model with a linear kernel.

5.print the accuracy and classification report. 

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: Abijith Shaan S
RegisterNumber: 212223080002
*/
import chardet 
file="spam.csv"
with open(file, "rb") as rawdata:
  result=chardet.detect(rawdata.read(100000))
result
import pandas as pd
data=pd.read_csv("spam.csv",encoding="Windows-1252")
data.head()
data.info()
data.isnull().sum()
x=data["v1"].values
y=data["v2"].values
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()
x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)
from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred
from sklearn import metrics
accuracy=metric.accuracy_score(y_test,y_pred)
accuracy
```

## Output:
data.head():

![image](https://github.com/Shaan2803/Implementation-of-SVM-For-Spam-Mail-Detection/assets/160568486/c917be23-dada-4842-9a4d-6a6d6e4c85b7)

data.info():

![image](https://github.com/Shaan2803/Implementation-of-SVM-For-Spam-Mail-Detection/assets/160568486/cf2e3413-c7d4-417b-911c-c58f04241542)

data.isnull().sum():

![image](https://github.com/Shaan2803/Implementation-of-SVM-For-Spam-Mail-Detection/assets/160568486/20cec855-35e6-4b52-b1cb-ff852133fb00)

accuracy:

![image](https://github.com/Shaan2803/Implementation-of-SVM-For-Spam-Mail-Detection/assets/160568486/487f6c0a-17b0-4d3d-9a29-3a504fdbba0b)









## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
