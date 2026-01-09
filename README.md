## Key EDA Observations

- Customer behavior is highly skewed across Recency, Frequency, and Monetary Value
- A small number of customers contribute disproportionately to total revenue
- Recency shows a long tail, indicating inactive customers
- Strong relationship between Frequency and Monetary Value
- Presence of extreme values suggests natural candidates for anomaly detection

These observations justify:

- Feature scaling before K-Means
- Using clustering to discover customer segments
- Applying anomaly detection to identify unusual customer behavior

## Clustering Approach

Algorithm: K-Means
Preprocessing: StandardScaler
Cluster selection: Elbow Method
Optimal K: 4
Identified Customer Segments

| Cluster                         | Description                        |
| ------------------------------- | ---------------------------------- |
| Regular Active Customers        | Recently active, average spend     |
| Loyal High-Value Customers      | Frequent buyers with high spend    |
| Inactive / Churn-Risk Customers | Low engagement, long recency       |
| VIP / Wholesale Customers       | Extremely high value and frequency |

Each cluster represents a distinct behavioral segment, discovered without labels.

🚨 Anomaly Detection

After clustering:

Computed distance of each customer to their assigned cluster centroid

Used 95th percentile threshold to flag anomalies

Anomalies are cluster-relative, not global

Key Insight

Large clusters produce more anomalies numerically

VIP / Wholesale anomalies are fewer but far more impactful

Anomaly ≠ fraud — often indicates rare, high-value behavior

📈 Business Insights

VIP / Wholesale Customers

Small in number, massive revenue impact

Require white-glove service and relationship management

Loyal High-Value Customers

Ideal targets for loyalty programs and upselling

Regular Active Customers

Largest base

Strong candidates for promotions and conversion to high-value segment

Inactive / Churn-Risk Customers

Best candidates for reactivation campaigns or cost-benefit review

🛠️ Tools & Technologies

Python

Pandas, NumPy

Scikit-Learn

Matplotlib, Seaborn

Joblib

🏁 Key Takeaways

Unsupervised learning is most powerful when combined with strong feature engineering

Clustering reveals structure, anomaly detection reveals risk and opportunity

Interpreting results in business context is more important than model complexity

👤 Author
Arun Kumar
Machine Learning Practitioner | .NET & Python Developer
🔗 LinkedIn: https://www.linkedin.com/in/arunkumardeveloper/
