# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.
2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3. Import KMeans and use for loop to cluster the data.
4. Predict the cluster and plot data graphs.
5. Print the outputs and end the program
 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Divya S
RegisterNumber: 212221040042
*/

import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")

data.head()

data.info()
data.isnull()
data.isnull().sum()


data.info()
data.isnull()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss= []

for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km=KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="black",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="cyan",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="yellow",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="green",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
## data.head()
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/648b3837-2b59-40f4-9e74-1cd7be5909b6)

## data.isnull().sum():
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/4d77593a-f9d8-456a-9477-8ac7a667ff77)

## data.info()
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/5b6e5a09-9a67-4c19-9aa3-736db402cb9a)

## Elbow method graph
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/65416470-b77c-4138-8543-1e454b9295e1)

## KMeans clusters
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/8b7bebd1-9c52-4df2-8081-58aab8c10a32)

## y_pred
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/8ecd01fd-27b9-4d33-b93b-4522884a3236)

## Customers Segments Graph
![image](https://github.com/divz2711/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/121245222/c5b21a65-5ccd-4346-bf19-d994ae6aad90)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
