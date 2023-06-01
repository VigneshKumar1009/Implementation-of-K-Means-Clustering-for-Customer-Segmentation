# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Vigneshkumar V
RegisterNumber:212220220054  
*/
```
import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

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

plt.title("Customer Segment")
## Output:
1.DATA.HEAD():

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/99788249-edf9-4f94-baf8-f198fc45894a)

2.DATA.INF0():

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/4fb25ce1-1083-4bd3-9846-948dbfb77777)

3.DATA.ISNULL().SUM():

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/05e28d25-47f6-4a7d-bdd5-dd2981609770)

4.PLOT USING ELBOW METHOD:

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/79e6eba5-b273-4347-a2c3-1cb871d08992)

5.K-MEANS CLUSTERING:

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/412ded1b-f253-44d9-8e88-06391e4150d9)

6.Y_PRED ARRAY:

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/2b477b8e-cbfb-4241-8092-b998899d8ee5)

7.CUSTOMER SEGMENT:

![image](https://github.com/VigneshKumar1009/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/113573894/30391c46-aaa4-4c6a-829c-2e91eaad54b7)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
