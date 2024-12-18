# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
 1.Import pandas and matplotlib.pyplot
 2.Read the dataset and transform it
 3.Import KMeans and fit the data in the model
 4.Plot the Cluster graph
```
## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Chandru M
RegisterNumber: 24900224

```
```python
 import pandas as pd
 import matplotlib.pyplot as plt
 data = pd.read_csv("Mall_Customers.csv")
 data.head()
 data.info()
 data.isnull().sum()


 from sklearn.cluster import KMeans
 wcss = []
 for i in range(1,11):
     kmeans = KMeans(n_clusters = i,init = "k-means++")
     kmeans.fit(data.iloc[:,3:])
     wcss.append(kmeans.inertia_)


 plt.plot(range(1,11),wcss)
 plt.xlabel("No. of Clusters")
 plt.ylabel("wcss")
 plt.title("Elbow Method")


 km = KMeans(n_clusters = 5)
 km.fit(data.iloc[:,3:])
 KMeans(n_clusters=5)
 y_pred = km.predict(data.iloc[:,3:])
 y_pred


 data["cluster"] = y_pred
 df0 = data[data["cluster"]==0]
 df1 = data[data["cluster"]==1]
 df2 = data[data["cluster"]==2]
 df3 = data[data["cluster"]==3]
 df4 = data[data["cluster"]==4]
 plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster")
 plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster")
 plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster")
 plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster")
 plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster")
 plt.legend()
 plt.title("Customer Segments")
```

## Output:

<img width="791" alt="image" src="https://github.com/user-attachments/assets/4cf32ae0-6bac-40fc-bc3f-6c5d13d1d7a7" />

<img width="593" alt="image" src="https://github.com/user-attachments/assets/4ed5985a-c40a-4ce2-bf15-5fb731b6b312" />

<img width="748" alt="image" src="https://github.com/user-attachments/assets/72ecc143-d105-4ddb-b7db-07a5628c2678" />

<img width="681" alt="image" src="https://github.com/user-attachments/assets/0059b55f-69c8-4dc7-ba00-fc05aa97c23f" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
