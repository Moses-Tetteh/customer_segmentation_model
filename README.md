### Customer Segmentation using Clustering

In this project, we'll explore customer segmentation using various Python-based machine learning and data science libraries. The goal is to create customer groups based on their purchasing behaviors, which can be valuable for tailored marketing and business strategy.

We'll follow the steps below:

1. **Problem Definition**
2. **Data**
3. **Evaluation**
4. **Features**
5. **Modeling**
6. **Experimentation**


### 1. Problem Definition

In a statement:

> Given customer transaction data, can we segment customers into distinct groups based on their purchasing behavior?

### 2. Data

The data comes from the [Online Retail dataset](https://archive.ics.uci.edu/ml/datasets/online+retail) on the UCI Machine Learning Repository. This dataset contains information about customer transactions for a UK-based online retailer.

The data file path used in this project:
- `/kaggle/input/retail/Online Retail.xlsx`

### 3. Evaluation

We’ll use clustering evaluation metrics, primarily the **Silhouette Score**, to measure the effectiveness of our clusters. A high Silhouette Score (close to 1) will indicate that the clusters are well-separated and internally cohesive, achieving the project goal.

### 4. Features

Below is a dictionary of features that describe each customer’s behavior. These features were engineered from the raw data to represent customer purchasing patterns effectively:

| Feature       | Description                                                                                                                                          |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| `CustomerID`  | Unique identifier for each customer.                                                                                                                 |
| `Quantity`    | Total quantity of items purchased by the customer.                                                                                                   |
| `TotalPurchase` | Total spending by the customer (calculated as `Quantity * UnitPrice`).                                                                               |
| `InvoiceNo`   | Count of unique invoices for each customer, indicating the frequency of purchases.                                                                  |
| `Country`     | The country from which the customer made their purchase.                                                                                             |

### 5. Modeling

For modeling, we’ll use the **K-means clustering algorithm** due to its simplicity and interpretability in customer segmentation. The K-means algorithm will partition customers into groups where each group shares similar purchasing behavior.

#### Steps:
1. **Data Preparation**: We’ll start by cleaning the data, removing rows with missing `CustomerID` values or invalid `Quantity`.
2. **Feature Engineering**: We’ll create new features, such as `TotalAmount` and aggregate data by `CustomerID`.
3. **Scaling**: Numerical features will be standardized to ensure fair contribution to clustering.
4. **Elbow Method**: We’ll determine the optimal number of clusters by analyzing within-cluster sum of squares (WCSS).
5. **Clustering with K-means**: Using the chosen number of clusters, we’ll apply K-means clustering and label each customer with a cluster ID.
6. **Evaluation**: We’ll calculate the **Silhouette Score** to assess clustering quality.

