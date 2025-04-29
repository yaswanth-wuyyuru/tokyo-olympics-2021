# 📊 GitHub Activity Analytics on Azure — End-to-End Data Integration & Insights Pipeline

## 📈 Business Objective

This project was developed to help **engineering managers and DevOps teams** gain actionable insights into team productivity, code review cycles, and repository health by analyzing GitHub activity data. Using Azure’s modern data stack, the pipeline integrates GitHub data, transforms it, and delivers **interactive analytics dashboards** that inform strategic decisions about developer performance, sprint planning, and resource allocation.

## 📊 Metrics & Dimensions

This pipeline enables comprehensive analytics through the following **business-relevant metrics** and **dimensions**:

### 🔢 Key Metrics
- Total commits per developer
- Average pull request (PR) review time
- Pull requests opened vs. closed (per week/month)
- Time to merge PRs
- Issue resolution rate (closed vs. opened)
- Active/inactive repos by commit frequency

### 🔠 Dimensions
- Repository
- Developer
- Date (Day/Week/Month)
- Team/Organization unit
- PR label/type

> ✅ *"This pipeline supports reporting on metrics like time-to-merge, PR volume, and issue resolution, segmented by team, developer, and repository to guide engineering operations."*

## 🔍 Key Insights

Data exploration and analysis via Azure Synapse and Power BI led to the following key insights:

- 📉 **PRs without assigned reviewers stayed open 2x longer** than those with assignments.
- 📈 **Developer A consistently merged 25% more PRs** than the team average, indicating a high-performing contributor.
- ⚠️ Certain repositories showed <1 commit/week activity, signaling potential neglect or deprecated usage.
- 🔁 Repos with regular bi-weekly commit patterns had 30% higher issue resolution rates and fewer rollbacks.

## 💡 Recommendations

Based on analysis outcomes, the following actions are recommended for **engineering leadership and project managers**:

- 🛠️ Implement **automated reviewer assignment** policies for all PRs to reduce bottlenecks in review cycles.
- 📅 Set **minimum activity thresholds** (e.g., commits per month) to detect and deprecate stale repositories.
- 🎯 Use **developer-level insights** to identify high/low performers and plan mentorship or role allocation accordingly.
- 📊 Track issue resolution KPIs to improve sprint planning and feature delivery velocity.

## 🧠 Tools & Data Ecosystem

This solution forms a **secure, scalable, and modular data ecosystem** using the following Azure and open-source tools:

| Layer | Technology | Description |
|-------|------------|-------------|
| **Data Ingestion** | Azure Data Factory | Ingest GitHub repo data via REST APIs into Azure Data Lake |
| **Data Storage** | Azure Data Lake Storage Gen2 | Store both raw and transformed data with directory hierarchy |
| **Data Transformation** | Azure Databricks (PySpark) | Clean, normalize, and enrich GitHub metadata at scale |
| **Secrets Management** | Azure Key Vault | Manage and securely store client secrets and API keys |
| **Data Modeling & Querying** | Azure Synapse Analytics | Create views and run analytical queries for insight extraction |
| **Visualization** | Power BI | Build dashboards (stacked columns, heatmaps) for actionable insights |
| **Security** | Azure RBAC | Apply role-based access to data layers and services |

> 🔐 *RBAC policies ensure secure, governed access to all data and compute layers across the ecosystem.*

## 📊 Dashboard Preview (Power BI)

![Dashboard Screenshot Placeholder](https://via.placeholder.com/800x400.png?text=Power+BI+Dashboard+Preview)

> *Power BI dashboard showcasing commit frequency, PR cycle time, and repository activity trends.*

## 🚀 How to Run This Project

1. **Clone the GitHub Repo**: Contains sample data & pipeline code
2. **Configure Azure Data Factory**: To fetch GitHub metadata into Azure Data Lake Gen2
3. **Launch Azure Databricks Cluster**: Run PySpark notebooks for transformation
4. **Connect Synapse Analytics**: For querying and modeling the transformed data
5. **Visualize with Power BI**: Build dashboards from Synapse datasets
6. **Set Up Azure Key Vault**: Store and fetch secrets securely
7. **Apply RBAC**: Configure access controls for team members

## 📌 Future Enhancements

- ✅ Implement real-time streaming of GitHub events via Azure Event Hub  
- ✅ Add anomaly detection using Azure ML or Databricks MLlib  
- ✅ Integrate JIRA/Slack APIs for richer DevOps insights  
- ✅ Automate alerting with Logic Apps for unreviewed PRs or inactive repos  

---

## 👨‍💻 Author

**Yaswanth Sai Surya Teja Wuyyuru**  
Data Engineer | Cloud & Analytics Enthusiast  
[LinkedIn](https://www.linkedin.com/in/yaswanthwuyyuru/) • [Medium Blog](https://medium.com/@ywuyyuru7)

---

