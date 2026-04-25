# LinkedIn SkillGap Data Pipeline

This project is a comprehensive data processing pipeline designed to analyze LinkedIn job posting data, extract technical skill requirements, and categorize them into various engineering domains. The ultimate goal is to build a structured knowledge base of skills to identify trends and gaps in the tech job market.

## Project Overview

The pipeline processes massive datasets containing millions of LinkedIn job postings to:
1.  **Filter** for technical roles (Software, Data, DevOps, Security, etc.).
2.  **Clean and Normalize** job titles and skill sets.
3.  **Categorize** skills into specific domains like Network Engineering, Data Science, and Backend Engineering.
4.  **Extract** the most frequent and relevant skills for each category.
5.  **Serialize** the processed data into a portable knowledge base.

## Dataset Description

The pipeline utilizes the following CSV datasets:
- `linkedin_job_postings.csv`: Core posting data (titles, companies, locations).
- `job_skills.csv`: Extracted skills associated with each job link.
- `job_summary.csv`: Detailed descriptions/summaries of the job postings.
- `job_listings.csv`: Additional listing metadata.

## Pipeline Workflow

The processing logic is contained within `skillsdata_pipeline.ipynb` and follows these steps:

1.  **Data Loading:** Initial exploration using sample chunks to understand schema and scale.
2.  **Data Exploration:** Analyzing dimensions, column types, and missing values across millions of records.
3.  **Cleaning & Preprocessing:**
    - Dropping records with missing skill data.
    - Case normalization (lowercasing).
    - Whitespace stripping and special character handling.
4.  **Technical Filtering:** Using a curated list of keywords to isolate tech-centric roles from the general job market.
5.  **Domain Categorization:** Mapping job titles to specific engineering categories (e.g., "Data Science & Analytics").
6.  **Knowledge Base Generation:** Aggregating skill frequencies per category.
7.  **Serialization:** Saving the final `cleaned_kb` as `knowledge_base.pkl` for downstream use.

## Requirements

- Python 3.x
- Pandas
- Jupyter Notebook / Google Colab

To install dependencies:
```bash
pip install pandas
```

## Key Insights

The pipeline identifies top skills across categories, such as:
- **Software Engineering:** Java, Python, AWS, SQL, Docker.
- **Data Engineering:** Python, SQL, Spark, Kafka, Snowflake.
- **Network Engineering:** DNS, Ansible, Python, BGP.
- **Backend Engineering:** AWS, Kubernetes, Node.js, Go.

## Output

The primary output of this pipeline is `knowledge_base.pkl`, a serialized dictionary containing refined skill frequency data categorized by industry domain.
