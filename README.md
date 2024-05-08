# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot
2. Read the dataset and transform it
3. Import KMeans and fit the data in the model
4. Plot the Cluster graph

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: NITHISH KUMAR S
RegisterNumber: 212223240109 
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1) (1).csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []  #Within-Cluster sum of square. 
for i in range(1,11):
  kmeans=KMeans(n_clusters = i,init = "k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
## data.head() function
![Screenshot 2024-05-08 184254](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/dff8862d-22f4-4f6a-b26a-08ad7bfa5988)


## data.info()
![Screenshot 2024-05-08 184305](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/fe8d781f-5306-4b10-84df-f57c9c810ad2)


## data.isnull().sum() function
![Screenshot 2024-05-08 184318](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/c2faab73-5dd7-40be-9857-765740b68642)


## Elbow method Graph
![Screenshot 2024-05-08 184332](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/b8d4e1c6-3e7c-430a-bb6f-08444c8e1102)

## KMeans clusters
![Screenshot 2024-05-08 184345](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/a22877d2-582e-4296-a81a-058b95751827)
![Screenshot 2024-05-08 184355](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/c3e1f2b7-f591-4dea-84e9-edecdd7bdda5)



#### Customer segments Graph
![Screenshot 2024-05-08 184408](https://github.com/nithish467/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/150232274/3d85f283-5b20-4f05-9e11-b2a3af384114)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
