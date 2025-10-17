
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

<img width="570" height="237" alt="398593633-70e1aca3-4a71-4696-b2b9-928d77b0a83e" src="https://github.com/user-attachments/assets/28ae307b-2167-4d69-ac23-923115e33ba6" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<img width="566" height="280" alt="398593649-7caea61e-f3c1-47c5-b8fe-2bc2e909dfe9" src="https://github.com/user-attachments/assets/29ef4330-082f-447f-990e-31f6f8635c56" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------


<img width="279" height="174" alt="398593664-8334f36d-3acc-4643-8a5f-cabdcb3a59f2" src="https://github.com/user-attachments/assets/107d7e5b-2da0-4464-a05c-8109fd15d73c" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="732" height="761" alt="398593695-63016bcc-0be2-4f62-bbab-a741adb491e1" src="https://github.com/user-attachments/assets/c1aa8aec-a7a6-4e73-b552-773d92c0ee56" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="732" height="402" alt="398593725-6e28ea51-13fb-4803-a47a-31437f95b6f6" src="https://github.com/user-attachments/assets/1ea0e058-73d5-464d-b316-07162f74896c" />

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<img width="866" height="777" alt="398593754-3e4f7550-b44f-4de9-b739-505a989a2293" src="https://github.com/user-attachments/assets/e3f9790d-60c2-4931-8c13-3382d241d0d3" />







## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
