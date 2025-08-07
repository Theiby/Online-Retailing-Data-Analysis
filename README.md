# E-Commerce Customer Segmentation and Sales Forecasting

This project provides an in-depth analysis of a transactional e-commerce dataset. The primary goal is to leverage data science techniques to understand customer behavior, segment customers into meaningful groups, and build machine learning models to predict future sales trends. This repository demonstrates an end-to-end data analysis pipeline, turning raw data into actionable business intelligence for targeted marketing and strategic planning.

## 📂 Project Goal and Scope

The core objectives of this project are:
1.  **Understand Customer Behavior:** To analyze the purchasing habits of customers, including their transaction frequency, recency, and monetary value.
2.  **Strategic Customer Segmentation:** To group customers into distinct, actionable segments that can be used to develop targeted marketing and retention campaigns.
3.  **Future Forecasting:** To build predictive models that forecast key business metrics like monthly revenue and active customer counts, enabling proactive decision-making.
4.  **Data-Driven Insights:** To extract valuable insights, such as identifying top products for loyal customers and analyzing the geographical distribution of sales.

## 💾 Dataset

The analysis was performed on the **"Online Retail"** dataset from the UCI Machine Learning Repository. This dataset contains international transaction records for a UK-based online retail company between 01/12/2010 and 09/12/2011.

## 🛠️ Methodology and Analysis Pipeline

The project follows several key steps, from initial data processing to predictive modeling.

### 1. Data Cleaning and Preprocessing
* Invalid entries, such as transactions with a negative `Quantity` (often representing returns) or a zero `UnitPrice`, were removed.
* Records with missing `CustomerID` were dropped as they could not be used for customer-level analysis.
* A `TotalPrice` feature was engineered by multiplying `Quantity` and `UnitPrice` for each transaction.

### 2. Exploratory Data Analysis (EDA)
To gain a high-level understanding of the business, key metrics were visualized, including:
* Monthly revenue trends to track performance over time.
* The geographical distribution of sales, highlighting the top 10 countries by quantity sold.

### 3. RFM Analysis for Customer Segmentation
The core of the customer segmentation was the **RFM (Recency, Frequency, Monetary)** model:
* **Recency:** The number of days since the customer's last purchase.
* **Frequency:** The total number of transactions made by the customer.
* **Monetary:** The total amount of money spent by the customer.

After calculating these values, customers were assigned a score from 1-4 for each RFM metric. Based on their combined RFM score, they were segmented into four primary groups:
* **Loyal Customers:** The most valuable group, characterized by high frequency, recent purchases, and high spending.
* **Potential Loyalists:** Frequent shoppers who may have spent less or not purchased as recently.
* **Promising:** New or recent customers who have not yet established a high frequency.
* **At-Risk:** Customers who have not made a purchase in a long time and are at risk of churning.

### 4. Machine Learning Models

#### a) Automated Customer Segmentation (Classification)
A **Random Forest Classifier** was trained to automatically assign customers to their respective segments based on their RFM values. This model achieved an **outstanding accuracy of 99.5%**, demonstrating its reliability in automating the segmentation process for new customers. The model also revealed the relative importance of the R, F, and M metrics in determining a customer's segment.

#### b) Revenue and Customer Forecasting (Regression)
To support future business planning, two separate regression models were developed:
1.  **Monthly Revenue Forecast:** A **Random Forest Regressor** was trained on historical monthly sales data to predict the total revenue for the upcoming month.
2.  **Active Customer Forecast:** Another regressor model was built to predict the number of unique active customers for the next month.

## 💡 Key Findings & Insights
* **High-Precision Automation:** The classification model can reliably automate customer segmentation, saving manual effort and enabling real-time targeting.
* **Loyal Customer Preferences:** A specific set of top-selling products was identified for the 'Loyal Customers' segment, which can be leveraged for targeted promotions, upselling, and stock management.
* **Geographical Loyalty:** The analysis revealed that countries like Belgium, Austria, and Switzerland have a higher percentage of loyal customers relative to their total customer base, suggesting strong market potential or effective engagement in these regions.

## 💻 Technology Stack
* **Language:** `Python`
* **Libraries:**


## 🚀 How to Run
The project is contained within a single Python script (`.py`) or a Jupyter Notebook (`.ipynb`).

1.  **Clone the repository:**
  ```bash
  git clone [https://your-repository-url.git](https://your-repository-url.git)
  ```
2.  **Install the necessary libraries:**
  ```bash
  pip install pandas numpy scikit-learn matplotlib openpyxl
  ```
3.  **Run the script:** The script fetches the data directly from the UCI repository URL, so no local data files are needed. Execute the script or run the notebook cells sequentially to reproduce the analysis and visualizations.

