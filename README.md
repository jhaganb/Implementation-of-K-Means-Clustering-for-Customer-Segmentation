# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries,read the data set.find the number of null data.
2. Find the number of null data.
3. Import sklearn library.
4. Find y predict and plot the graph.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Jhagan B
RegisterNumber:  212220040066
*/

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range (1,11):
    kmeans=KMeans(n_clusters = i,init="k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow matter")

km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segmets")

```

## Output:

data.head():

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/d6eb13bf-b0f4-4dea-8a05-2c10e33e80e6)

data.info():

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/1b32c2cf-5990-4c3f-89a8-2c8cd8f2010e)

data.isnull().sum():

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/f27f0518-607f-46af-b3b0-4edba828b451)

Elbow method graph:

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/c5c0d2c5-52c8-479f-808c-ef7215e0d826)

KMeans clusters:

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/49947ea6-0df7-4210-863d-1df0edf0e09c)

Array value of Y:

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/c383ed7a-54f5-4fac-a06b-27a5de25d47b)

Customers Segments graph:

![image](https://github.com/jhaganb/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/63654882/36d1bcd0-31ca-4e82-ba48-8a0572d4ef23)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
