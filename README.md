# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
Step 1: Start.

Step 2: Import the necessary packages using import statement.

Step 3: Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

Step 4: Import KMeans and use for loop to cluster the data.

Step 5: Predict the cluster and plot data graphs.

Step 6: Print the outputs and end the program

Step 7: END
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SHARAN G
RegisterNumber: 212223230203
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers.csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()



```

## Output:
![Screenshot 2024-10-04 105759](https://github.com/user-attachments/assets/84b93112-4eb5-4731-985b-c0bd1e504d53)

![Screenshot 2024-10-04 105805](https://github.com/user-attachments/assets/380904a1-5d73-4e9c-aec1-1873cf73b27d)

![Screenshot 2024-10-04 105811](https://github.com/user-attachments/assets/3b2cae30-515c-40a8-a2c3-ffe560611c28)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
