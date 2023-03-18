#DataEngineering 
# Objectives
- Business Objective
- Data Exploration
- Insight Visualization
- Kesimpulan dan Saran

# Syllabus
- TSQL Best Practices
- Business Acumen
- Data Modelling
- Tableau
- Ms. SQL Server
- SSIS Concept

# ETL
- Extract from CSV file to table in SQL server database

# Data Modelling
**Table: Clients**

-   ClientID (Primary Key)
-   Clientnum
-   Customer_age
-   Gender
-   Dependent count
-   Educationid
-   Maritalid
-   Income_category

**Table: CardDetails**

-   CardID (Primary Key)
-   ClientID (Foreign Key referencing Clients table)
-   Card_categoryid
-   Month_on_book
-   Credit limit
-   Total Revolving Balance on the Credit Card
-   Avg_open_to_buy
-   Avg_utilization_ratio

**Table: Transactions**

-   TransactionID (Primary Key)
-   CardID (Foreign Key referencing CardDetails table)
-   Total_trans_amt
-   Total_trans_ct

**Table: CustomerActivity**

-   CustomerActivityID (Primary Key)
-   ClientID (Foreign Key referencing Clients table)
-   Idstatus
-   Relationship_in_count
-   Months_inactive_in_12_month
-   Contacts_Count_12_mon

# Business Goals
1.  Segmentation Analysis Dengan melakukan analisis segmentasi, bank dapat membagi pelanggannya ke dalam kelompok yang berbeda berdasarkan karakteristik mereka, seperti usia, jenis kelamin, pendidikan, penghasilan, jenis kartu kredit, dll. Hal ini dapat membantu bank memahami pelanggan mereka dengan lebih baik dan mengembangkan strategi pemasaran yang lebih efektif.
    
2.  Customer Churn Analysis Dengan melihat data tentang pelanggan yang tidak aktif selama 12 bulan terakhir, bank dapat melakukan analisis churn dan mengidentifikasi faktor-faktor yang menyebabkan pelanggan berhenti menggunakan layanan bank. Hal ini dapat membantu bank mengembangkan strategi retensi yang lebih efektif untuk menjaga pelanggan tetap menggunakan layanan mereka.
    
3.  Credit Risk Analysis Dengan melihat data tentang limit kredit, saldo bergulir, dan rasio penggunaan kartu kredit, bank dapat melakukan analisis risiko kredit dan mengidentifikasi pelanggan yang berisiko tinggi. Hal ini dapat membantu bank mengambil tindakan pencegahan yang tepat dan mengurangi risiko kredit mereka.