# 🧠 Ethical Beauty Reviews: A Data Pipeline and Analytics Project

---

## 📦 Tech Stack

- **Languages & Tools**
  - Python
  - SQL
  - dbt
- **Infrastructure**
  - AWS RDS PostgreSQL
- **Automation & CI/CD**
  - GitHub Actions
- **Visualization**
  - Looker Studio

---

## 🎯 Project Objective

**Who are we helping?**  
Beauty brands, marketers, and analysts who want to understand customer engagement based on ethical brand attributes.

**What problem are we solving?**  
Companies want to know whether values like "vegan" or "black-owned" influence review quality and volume.

**How are we solving it?**  
By building a reproducible ETL pipeline that collects, processes, and analyzes reviews and brand metadata. Results are visualized in dashboards using Looker Studio.

---

## 💼 Job Description

The selected position is a **Data Analyst role at a major beauty-focused eCommerce platform**. The role requires SQL, dashboarding, automation, and pipeline skills.

**How this project aligns**:  
The project simulates real-world analytics tasks — including web scraping, API ingestion, SQL queries, RDS storage, GitHub automation, and BI dashboards.

📄 [Job_Description.pdf](proposal/Job_Description.pdf)

---

## 🔍 Data

### Sources

- API: Ethical product data (e.g., vegan, black-owned flags)
- Web scrape: Ulta customer reviews

---

## 📓 Notebooks & Scripts

| File                                  | Purpose                                             |
| ------------------------------------- | --------------------------------------------------- |
| `All_Product_API_Data_Cleaning.ipynb` | Cleans product-level ethical attribute data         |
| `Ulta_API_Data_Cleaning.ipynb`        | Cleans scraped customer reviews                     |
| `RDS_Setup_and_Load_Data.ipynb`       | Uploads cleaned data to AWS RDS                     |
| `All_Web_SQL_Analysis.ipynb`          | Performs SQL analysis on all product data           |
| `Ulta_Web_Scrape_SQL_Analysis.ipynb`  | Review-based SQL analysis                           |
| `retrieve_avg_review_votes.py`        | Joins and exports vegan vs non-vegan review metrics |

---

## 🚀 GitHub Actions Workflow

This project uses [GitHub Actions](https://github.com/features/actions) to automate the entire data pipeline.

### Workflow: `full_pipeline.yml`

**Runs:**

1. Data cleaning notebooks
2. RDS loading notebook
3. Data retrieval SQL notebooks

```yaml
on:
  workflow_dispatch:
```

You can manually trigger the pipeline from the **Actions** tab in GitHub.

---

## 🛠 How to Run Locally

### 1. Create and activate virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 2. Install requirements

```bash
pip install -r requirements.txt
```

### 3. Run notebooks in order

```bash
jupyter nbconvert --to notebook --execute notebook/Data-Cleaning/All_Product_API_Data_Cleaning.ipynb
jupyter nbconvert --to notebook --execute notebook/Data-Cleaning/Ulta_API_Data_Cleaning.ipynb
jupyter nbconvert --to notebook --execute notebook/Data-Loading/RDS_Setup_and_Load_Data.ipynb
jupyter nbconvert --to notebook --execute notebook/Data-Retrieval/All_Web_SQL_Analysis.ipynb
jupyter nbconvert --to notebook --execute notebook/Data-Retrieval/Ulta_Web_Scrape_SQL_Analysis.ipynb
```

---

## 🔮 Future Improvements

- Add NLP sentiment analysis on `review_text` using HuggingFace or TextBlob
- Expand data sources to include Sephora or Amazon Beauty reviews
- Integrate Looker Studio API to automate dashboard refreshes

---
