
# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load and preprocess data: Import data, inspect it, and handle missing values if any.

2. Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

3. Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

 
4. Assign cluster labels to each data point.

5. Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: CH.V.DINESH KUMAR
RegisterNumber:  212224040055

```
```
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
```
```
data.head()
```
```
data.info()
```
```
data.isnull().sum()
```
```
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++",n_init=10)
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
```
```
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
```
```
km = KMeans(n_clusters=5, n_init=10)
km.fit(data.iloc[:, 3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
```
```
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster1")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster2")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster4")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster5")
plt.legend()
plt.title("Customer Segments")
```
## Output:

![alt text](<Screenshot 2025-10-25 132906.png>)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
![alt text](<Screenshot 2025-10-25 132915.png>)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![alt text](<Screenshot 2025-10-25 132922.png>)


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![alt text](<Screenshot 2025-10-25 132933.png>)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![alt text](<Screenshot 2025-10-25 132940.png>)

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

![alt text](<Screenshot 2025-10-25 132951.png>)







## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
