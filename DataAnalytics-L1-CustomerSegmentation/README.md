# Customer Segmentation Analysis Using RFM and K-Means Clustering

## Project Overview

This project performs customer segmentation on an e-commerce retail dataset using RFM (Recency, Frequency, Monetary) analysis and K-Means clustering.

The objective is to group customers based on their purchasing behaviour and identify meaningful customer segments that can support targeted marketing strategies.

## Dataset

The project uses the Online Retail dataset, which contains transactional data from an online retail business.

The dataset includes information such as:

- Invoice number
- Product description
- Quantity purchased
- Invoice date
- Unit price
- Customer ID
- Country

After data cleaning, the final dataset contained **392,692 valid transaction records** and **4,338 customers**.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Data Cleaning

The following data cleaning steps were performed:

- Checked dataset structure and data types
- Identified and handled missing CustomerID values
- Removed duplicate records
- Removed cancelled transactions
- Removed transactions with zero or negative quantities
- Removed transactions with zero or negative unit prices
- Created a `TotalPrice` feature using Quantity × UnitPrice

## Descriptive Statistics

Key customer purchasing metrics were calculated:

- **Average Purchase Value:** 479.56
- **Average Purchase Frequency:** 4.27 orders per customer
- **Average Historical Customer Lifetime Value:** 2,048.69

## RFM Analysis

Three behavioural features were selected for customer segmentation:

- **Recency:** Number of days since the customer's most recent purchase
- **Frequency:** Number of unique purchases made by the customer
- **Monetary:** Total amount spent by the customer

Because Frequency and Monetary contained highly skewed values and outliers, log transformation was applied before standardisation.

The RFM features were then standardized using `StandardScaler`.

## K-Means Clustering

The Elbow Method was used to determine an appropriate number of clusters.

Based on the elbow curve, **K = 3** was selected.

![Elbow Method](Elbow%20Method%20for%20Optimal%20K.png)

## Customer Segments

The K-Means model identified three customer segments:

| Customer Segment | Avg Recency | Avg Frequency | Avg Monetary | Customers |
|---|---:|---:|---:|---:|
| High-Value / Loyal | 17.06 | 13.35 | 7,898.46 | 769 |
| Inactive / Low-Value | 167.36 | 1.35 | 361.00 | 1,872 |
| Regular / Potential Loyal | 44.20 | 3.38 | 1,259.58 | 1,697 |

### High-Value / Loyal Customers

These customers purchase frequently, have purchased recently, and generate the highest monetary value.

### Inactive / Low-Value Customers

These customers have not purchased recently, purchase infrequently, and generate relatively low monetary value.

### Regular / Potential Loyal Customers

These customers show moderate purchasing frequency, recency, and spending and have the potential to become loyal customers.

## Customer Segment Distribution

![Customer Segment Distribution](Number%20of%20Customers%20by%20Segment.png)

## Cluster Visualizations

### Frequency vs Monetary

![Frequency vs Monetary](Customer%20Segments_%20Frequency%20Vs%20Monetary.png)

### Recency vs Monetary

![Recency vs Monetary](Customer%20Segments_Recency%20Vs%20Monetary.png)

## Marketing Recommendations

### High-Value / Loyal Customers

- Provide VIP rewards and loyalty benefits
- Offer exclusive discounts and early access to new products
- Use personalized product recommendations
- Focus on customer retention

### Regular / Potential Loyal Customers

- Encourage repeat purchases through loyalty programs
- Use targeted promotions and personalized recommendations
- Apply cross-selling and upselling strategies
- Offer purchase milestone rewards

### Inactive / Low-Value Customers

- Use re-engagement campaigns
- Provide limited-time discounts or coupons
- Send personalized promotional messages
- Offer incentives to encourage customers to return

## Conclusion

RFM analysis combined with K-Means clustering successfully identified three meaningful customer segments.

The results can help the business differentiate between high-value loyal customers, regular customers with growth potential, and inactive customers who may require re-engagement.

These customer segments can support more targeted marketing campaigns, customer retention strategies, and personalized promotions.
