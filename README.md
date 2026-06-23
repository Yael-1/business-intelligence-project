# Hotel Booking Cancellation & Profitability Analysis

An end-to-end Business Intelligence and Machine Learning project focused on analyzing hotel bookings, identifying cancellation risk factors, and generating actionable strategies to improve customer retention and hotel profitability.

This academic team project combines data cleaning, data warehouse design, Tableau dashboards, and predictive modeling.

## Project Objectives

The project aims to answer the following business questions:

- What are the main factors that influence hotel booking cancellations?
- How can high-risk bookings be identified in advance?
- Which customer segments and booking channels are the most profitable?
- How can the hotel reduce cancellations, improve customer retention, and increase revenue?

## Dataset

The project uses the **Hotel Booking Demand** dataset from Kaggle.

The dataset includes approximately 120,000 booking records from two hotels in Portugal:

- City Hotel
- Resort Hotel

It contains 32 attributes related to booking behavior, customer characteristics, room type, market segment, deposits, cancellations, and more.

## Project Workflow

### 1. ETL Process

The data preparation process was implemented in Python.

**Extract**
- Loaded the raw hotel booking dataset from CSV.

**Transform**
- Removed irrelevant columns.
- Handled missing values.
- Converted data types where needed.
- Standardized category names and values.
- Prepared the data for analysis and modeling.

**Load**
- Exported a cleaned dataset for downstream use in the data warehouse, Tableau dashboards, and machine learning models.

## Data Warehouse Design

A star schema was designed to support efficient analytical queries and dashboard reporting.

### Fact Table

**Fact Booking**

- Booking_ID
- Date_ID
- Customer_ID
- Room_ID
- Price
- Is_Cancelled

### Dimension Tables

- Dim Agent
- Dim Customer
- Dim Date
- Dim Hotel
- Dim Market Segment
- Dim Meal
- Dim Order Status
- Dim Room Type

## Tableau Dashboards

Nine interactive Tableau reports were created to answer different business questions.

The dashboards analyze:

1. Cancellation rate by country
2. Cancellation rate by market segment and distribution channel
3. Reserved room type versus assigned room type
4. Cancellation rate by lead time
5. Cancellation rate by meal type
6. Cancellation rate by deposit type
7. Customer loyalty and cancellation behavior
8. Top agents by cancellation rate
9. Average revenue by market segment

## Key Business Insights

- The highest cancellation rates were observed in the United Arab Emirates, Saudi Arabia, and Indonesia.
- The `Groups` segment showed a particularly high cancellation rate, while `Direct` and `Corporate` channels were more stable.
- Longer lead times were associated with higher cancellation rates.
- Repeat guests had substantially lower cancellation rates than new guests.
- Deposit type was one of the strongest predictors of cancellation behavior.
- Some room reservations involved a mismatch between the room booked and the room assigned, which may affect customer satisfaction.
- The most profitable market segments included Online TA and Direct, while Complementary and Undefined segments generated lower average revenue.

## Business Recommendations

Based on the analysis, several actions were proposed:

- Apply stricter cancellation policies or deposit requirements for high-risk segments and channels.
- Prioritize stable and profitable channels such as Direct and Corporate.
- Create targeted retention strategies for repeat customers.
- Improve communication with customers when room assignments change.
- Monitor agents and booking channels with unusually high cancellation rates.
- Use cancellation-risk predictions to trigger proactive reminders or customized offers before check-in.

## Machine Learning

### Logistic Regression: Cancellation Prediction

A Logistic Regression model was built to predict whether a booking would be canceled.

**Input features included:**

- Lead time
- Length of stay
- Number of adults, children, and babies
- Repeated guest status
- Previous cancellations
- Previous non-canceled bookings
- Deposit type
- Customer type
- Average daily rate
- Number of special requests
- Booking changes

**Evaluation metrics:**

| Metric | Score |
|---|---:|
| Accuracy | 0.7737 |
| Precision | 0.8938 |
| Recall | 0.4512 |
| F1-score | 0.5997 |
| ROC-AUC | 0.80 |

The model achieved good precision, but relatively low recall, indicating that further feature engineering and threshold tuning could improve identification of bookings likely to be canceled.

### Booking Status Classification

Three classification models were compared for predicting booking status:

- Decision Tree Classifier
- Random Forest Classifier
- K-Nearest Neighbors (KNN)

| Model | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Decision Tree | 76.75% | 82.80% | 76.75% | 73.20% |
| Random Forest | 82.85% | 82.51% | 82.85% | 82.42% |
| KNN | 76.78% | 76.40% | 76.78% | 76.19% |

**Random Forest** achieved the strongest overall performance.

Important predictive features included:

- Deposit type
- Lead time
- Previous cancellations
- Average daily rate
- Number of special requests

## Technologies

- Python
- pandas
- scikit-learn
- Tableau
- Data Warehousing
- ETL
- Machine Learning
- Data Visualization
- Jupyter Notebook

## Repository Contents

- Tableau packaged workbook (`.twbx`)
- Project presentation
- Project report and documentation
- Python code files for ETL and machine learning analysis

## How to Explore the Project

1. Open the Tableau workbook in Tableau Desktop or Tableau Public-compatible software.
2. Review the presentation for the dashboard walkthrough and business insights.
3. Read the project documentation for the methodology, findings, and machine learning results.
4. Run the Python files after updating local file paths if needed.

## Author

Yael Avraham  
Academic Business Intelligence Project
