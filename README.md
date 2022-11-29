# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: M.Vidya Neela
RegisterNumber:  212221230120
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers (1).csv")

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

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="yellow",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="pink",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![204126162-7b8625f4-e206-420f-9b43-5905fd72d92a](https://user-images.githubusercontent.com/94169318/204434460-22833bd1-bcd9-4de8-b624-0aeb610892bf.png)

![204126168-b167d6b3-5afd-4e49-bf7b-b90cf2778a55](https://user-images.githubusercontent.com/94169318/204434485-172d2301-5708-497f-9b59-737c13af16c8.png)

![204126180-1bb7ad03-f643-403d-b740-7b376d10a15c](https://user-images.githubusercontent.com/94169318/204434509-540ef27e-71e7-43d4-8042-1fc276442385.png)

![204126184-5bed5151-ed37-4391-afc3-88a934c19798](https://user-images.githubusercontent.com/94169318/204434533-f9b4caa7-61f4-42be-92b0-60c17116f1a7.png)

![204126190-48813510-962a-42b4-b3f6-7caf58521a99](https://user-images.githubusercontent.com/94169318/204434560-6cacb8c6-2e75-4a1d-8817-86d2da07900b.png)

![204126193-8ed2a635-7eaa-4d9b-9e34-31eab77c1686](https://user-images.githubusercontent.com/94169318/204434582-71fa6fc7-35ac-4701-b932-180c5e5e8cb4.png)

![image](https://user-images.githubusercontent.com/94169318/204435172-8c41a97e-0779-4516-8bbb-1b9388daaed9.png)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
