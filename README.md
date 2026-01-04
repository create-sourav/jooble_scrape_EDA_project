# India Data Jobs Market Analysis (Scraped from Jooble API)

## 📌 Project Overview
This project analyzes the **real-time data jobs market in India** using job listings scraped from the Jooble API.  
The goal was to understand **hiring trends, role demand, required skills, and company activity** across data-related roles such as:

- Data Analyst  
- Business Analyst  
- Data Engineer  
- Data Scientist  

Rather than just scraping jobs, this project focuses on **cleaning, classifying, storing, and analyzing structured job data** in a reproducible and transparent way.

---

## 🔗 Data Source
Jobs are collected using the official Jooble Jobs API.  
Queries were run for India across the following search roles:

- `"data analyst"`
- `"business analyst"`
- `"data engineer"`
- `"data scientist"`

All results are stored, cleaned, and analyzed programmatically.

---

## 🧹 Data Cleaning & Processing
The raw job data contained noise such as duplicates, missing fields, and unrelated postings.

Key processing steps included:

✔ Removing duplicate postings using the job `link` field  
✔ Cleaning HTML descriptions  
✔ Extracting and normalizing experience values  
✔ Parsing timestamps for time-series analysis  
✔ Creating structured columns for analysis

> **Important note:**  
> Some fields like *salary* and *state* are not consistently provided by the API.  
> Rather than guessing or fabricating values, these were left as `Unknown` where not available.

---

## 🧠 Skill Extraction (TF-IDF Auto-Discovery)
Instead of manually listing all possible skills, TF-IDF was applied on job descriptions to automatically surface recurring technical terms related to:

- SQL / Databases  
- Python & Analytics tools  
- Visualization platforms  
- Data engineering technologies  
- ML/AI frameworks  

This created an intelligent **`skills_auto`** field that highlights what companies actually ask for in practice.

---

## 🎯 Core vs Non-Core Job Classification
Job boards contain noise — many results were unrelated roles (HR, Sales, Customer Support, etc.).

To maintain analytical integrity, jobs were classified into:

### ✅ Core Data Roles
- Data Analyst
- Business Analyst
- Data Engineer
- Data Scientist

### ❌ Non-Core / Misclassified Roles
(e.g., Digital Marketing Analyst, Telecaller, Sales Executive, etc.)

This separation allowed deeper and more meaningful insights.

---

## 📊 Key Insights (Summary)
- **Data Analyst roles consistently dominate** demand vs Business Analyst  
- A surprisingly large portion of scraped postings were **non-core roles**, highlighting job board noise  
- SQL, Python, Excel, and BI tools continue to be foundational skills  
- Several companies repeatedly appear as active recruiters, indicating stronger hiring pipelines  
- Business Analyst roles frequently overlap with operations/sales unless filtered carefully  

---

## 🗄️ Storage & Querying (SQLite)
All cleaned data is stored in SQLite, enabling powerful and reproducible EDA using SQL:

- Trend analysis by month  
- Top hiring companies  
- Role comparison  
- Skill demand distribution  
- Core vs non-core segmentation  

This design also supports **future incremental updates**.

---

## ⚠️ Limitations (Intentional & Documented)
To preserve accuracy:

- Salary information was not analyzed due to inconsistent availability  
- State/City data was only used when explicitly provided  
- No synthetic or assumed values were generated  

This maintains integrity of insights.

---

## 🚀 Future Enhancements
Planned improvements include:

- Integrating additional APIs (Adzuna, Naukri, Indeed) for richer geo and salary coverage  
- Live dashboard views in Power BI or Streamlit  
- Automated weekly job-market tracking  
- Deep NLP classification for better job labeling  

---

## ✅ Conclusion
This project goes beyond basic scraping by demonstrating:

✔ Real-world data collection  
✔ Responsible cleaning and validation  
✔ Skill intelligence extraction  
✔ Meaningful hiring insights  
✔ Reproducible SQL-driven analytics  

It showcases applied data analytics on a problem that directly reflects **market reality and hiring trends in India**.
