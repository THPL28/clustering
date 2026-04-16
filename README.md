# 🚀 Clustering with K-Means (Google Colab)

This project demonstrates, in practice, how to apply **clustering using K-Means**, exploring how data can be grouped based on similarity — without labeled data.

The goal is to move from a simple example to a solid foundation that can be extended to real-world data problems.

---

## 📌 Objective

- Understand how **K-Means** works  
- Visualize how data points are grouped  
- Explore how to choose the optimal number of clusters  
- Build a foundation for real-world applications and embeddings  

---

## 🧠 Concepts Covered

- Clustering (unsupervised learning)  
- Data similarity  
- Centroids  
- Inertia  
- Elbow Method  

---

## ⚙️ Technologies Used

- Python  
- NumPy  
- Matplotlib  
- Scikit-learn  
- Google Colab  

---

## 📊 Project Pipeline

1. Generate synthetic data  
2. Apply K-Means clustering  
3. Extract clusters and centroids  
4. Visualize results  
5. Evaluate using the Elbow Method  

---

## 📦 Implementation

### 1. Import libraries

    import numpy as np
    import matplotlib.pyplot as plt
    from sklearn.cluster import KMeans
    from sklearn.datasets import make_blobs

---

### 2. Generate synthetic data

    X, y = make_blobs(n_samples=300, centers=4, cluster_std=1.2, random_state=42)

📌 Simulates structured data with 4 clusters

---

### 3. Train the model

    kmeans = KMeans(n_clusters=4, random_state=42)
    kmeans.fit(X)

📌 The model groups data based on distance to centroids

---

### 4. Extract results

    labels = kmeans.labels_
    centroids = kmeans.cluster_centers_

- `labels`: cluster assigned to each data point  
- `centroids`: center of each cluster  

---

### 5. Visualization

    plt.scatter(X[:, 0], X[:, 1], c=labels)
    plt.scatter(centroids[:, 0], centroids[:, 1], marker='X', s=200)
    plt.title("K-Means Clustering")
    plt.show()

📌 Visual representation of clusters and centroids

---

### 6. Elbow Method

    inertia = []
    for k in range(1, 10):
        kmeans = KMeans(n_clusters=k)
        kmeans.fit(X)
        inertia.append(kmeans.inertia_)

    plt.plot(range(1, 10), inertia)
    plt.title("Elbow Method")
    plt.show()

📌 Helps identify the optimal number of clusters

---

## 📈 Results

- Clear separation of clusters  
- Visualization of centroids  
- Identification of optimal K using inertia  

---

## 💡 Insights

- Choosing the right number of clusters is critical  
- K-Means performs best with well-defined, spherical clusters  
- Data representation is often more important than the algorithm itself  

> In many cases, **better representations lead to better models**

---

## 🚀 Next Steps

- Apply clustering to real-world datasets  
- Experiment with other algorithms:
  - DBSCAN  
  - Hierarchical Clustering  
- Apply dimensionality reduction (PCA)  
- Use **embeddings with neural networks (Autoencoders)**  

---

## 📚 Reference

Based on concepts from Google Developers Machine Learning (DNN-based clustering)

---

## 👨‍💻 Author

Tiago Henrique Pereira Looze  
📧 tiago.looze@gmail.com  
🔗 https://github.com/THPL28  
🔗 https://www.linkedin.com/in/tiago-looze-b1a0001b7/

---

## ⭐ Contribution

If you found this project helpful, consider giving it a star ⭐
