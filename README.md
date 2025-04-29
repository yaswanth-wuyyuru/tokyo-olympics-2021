# 🏅 Tokyo Olympics 2021 Analytics Pipeline on Azure

An end-to-end data engineering and analytics project built to analyze athlete performance, medal distribution, and sport-wise trends from the Tokyo Olympics 2021 dataset. This solution utilizes Microsoft Azure's modern data stack to ingest, transform, and visualize Olympic data, enabling insightful decision-making for sports federations, coaching teams, and performance analysts.

---

## 📈 Business Objective

The Tokyo Olympics host over 11,000 athletes across 33 sports and 339 events. This project aims to extract meaningful insights from Olympic data, helping stakeholders:

- Track medal distribution by country, gender, and sport
- Analyze athlete demographics and participation trends
- Identify sports and countries with high medal efficiency
- Discover patterns in performance across age groups, events, and countries

---

## 📊 Metrics & Dimensions

### 🔢 Key Metrics
- Total medals (Gold, Silver, Bronze)
- Medal count per country and sport
- Athlete participation volume per event
- Gender-wise medal share
- Average age of medalists
- Medal efficiency (Medals per athlete per country)

### 🔠 Dimensions
- Country (NOC)
- Sport / Event
- Athlete
- Gender
- Age Group
- Medal Type
- Date of Event

> *Supports slicing and dicing Olympic performance across key dimensions like gender, country, and sport to derive targeted performance insights.*

---

## 🔍 Key Insights

After performing transformation and analysis using PySpark in Azure Databricks, these were some notable insights:

- 🥇 **USA, China, and Japan** dominated the medal tally, but **Japan showed highest medal efficiency** in Judo and Skateboarding.
- 👧 **Athletes below 20 years old won over 10% of total medals**, especially in new-age sports like Skateboarding and Gymnastics.
- 🏃‍♀️ **Female athletes contributed significantly** in Swimming, Athletics, and Weightlifting with near-equal medal distribution in multiple countries.
- 🥉 **Countries with fewer athletes** (e.g., Bermuda, San Marino) showed high medal-per-athlete ratios, indicating strategic success.

---

## 💡 Recommendations

Based on the analytical findings:

- 🇯🇵 Invest further in high-efficiency sports (e.g., Judo for Japan, Wrestling for Russia).
- 🚺 Boost female participation in countries with gender gaps to improve medal counts.
- 🧒 Develop youth training programs in emerging sports like Skateboarding, Surfing, and Climbing.
- 📊 Use country-level medal efficiency KPIs to guide selection and delegation strategy in future Olympics.

---

## 🧠 Tools & Data Ecosystem

| Layer                     | Technology                  | Description                                                               |
|--------------------------|-----------------------------|---------------------------------------------------------------------------|
| **Data Ingestion**       | Azure Data Factory (or Mount via PySpark) | Accessed CSV files from Azure Data Lake Gen2 using OAuth authentication |
| **Data Storage**         | Azure Data Lake Storage Gen2 | Secure, scalable raw data storage (mounted to Databricks)                |
| **Data Processing**      | Azure Databricks + PySpark   | Cleaned and transformed Olympic data using PySpark DataFrames            |
| **Secrets Management**   | Azure Key Vault              | Secured OAuth credentials and secret keys                                |
| **Data Modeling**        | Azure Synapse Analytics      | Created analytical views for medal metrics and sport-wise aggregations   |
| **Visualization**        | Power BI                     | Built interactive dashboards for country-wise, gender-wise, and sport-wise performance |
| **Security**             | Azure RBAC                   | Applied role-based access control to all Azure services                  |

> 🔐 Secrets were managed via **Azure Key Vault**, and data access was securely controlled with **RBAC**.

---

## 🧪 Sample Analysis Code (PySpark in Azure Databricks)

```python
from pyspark.sql.types import *
from pyspark.sql.functions import col

# Mount Azure Data Lake Gen2
configs = {
  "fs.azure.account.auth.type": "OAuth",
  "fs.azure.account.oauth.provider.type": "org.apache.hadoop.fs.azurebfs.oauth2.ClientCredsTokenProvider",
  "fs.azure.account.oauth2.client.id": "<Client_ID>",
  "fs.azure.account.oauth2.client.secret": "<Secret_Key>",
  "fs.azure.account.oauth2.client.endpoint": "https://login.microsoftonline.com/<Tenant_ID>/oauth2/token"
}

dbutils.fs.mount(
  source = "abfss://<container>@<storage_account>.dfs.core.windows.net",
  mount_point = "/mnt/tokyoolympics2021",
  extra_configs = configs
)
📊 Dashboard Preview (Power BI)
Power BI dashboards showcase athlete participation trends, medal distributions, and high-performing nations across various Olympic sports.

🖼️ (Insert screenshot or link to dashboard demo if available)

🚀 How to Run This Project
Clone this Repository (contains PySpark notebooks and configs)

Mount your Azure Data Lake using Databricks and OAuth configs

Run Transformation Notebooks to clean and analyze CSV data

Create Synapse Views from transformed data

Connect Power BI to visualize trends and derive insights

Secure with Key Vault + RBAC for enterprise-ready deployment

📌 Future Enhancements
✅ Integrate historical Olympics data for time-series trend analysis

✅ Use Azure ML or Databricks MLlib to predict medal trends based on athlete demographics

✅ Build live dashboards using Azure Event Hub and Stream Analytics for real-time Olympic coverage

👨‍💻 Author
Yaswanth Sai Surya Teja Wuyyuru
AI Data Engineer | Cloud & Analytics Enthusiast
🔗 LinkedIn • 📘 Medium Blog
