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

<img width="704" alt="image" src="https://github.com/user-attachments/assets/e00940fe-e36a-4dc9-968c-c985301855d8" />

<img width="674" alt="image" src="https://github.com/user-attachments/assets/8236b364-8540-4a54-819d-00607fa04a15" />

<img width="462" alt="image" src="https://github.com/user-attachments/assets/b5312de3-111d-4303-bc33-9f2ab1e0b696" />

<img width="695" alt="image" src="https://github.com/user-attachments/assets/55e28d40-6d09-4a47-8ad6-c30c3d6ca41a" />

<img width="668" alt="image" src="https://github.com/user-attachments/assets/c276ecca-26ee-4f6e-88f2-77436797b9b0" />


<img width="452" alt="image" src="https://github.com/user-attachments/assets/7487dafc-7f5f-452f-8471-3cceff26beeb" />


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
