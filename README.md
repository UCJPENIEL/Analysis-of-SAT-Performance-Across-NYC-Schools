# Analysis-of-SAT-Performance-Across-NYC-Schools
# 🗽 NYC Public Schools SAT Analysis  

An in-depth analysis of SAT performance across New York City public schools.  
This project explores borough-level trends, identifies top-performing schools, and highlights performance variability to guide policymakers, educators, and parents.  

---

## 🎯 Project Objective  
To uncover meaningful insights from NYC SAT score data by:  
- Analyzing borough-level SAT distribution and variability.  
- Identifying top schools in math and overall combined scores.  
- Highlighting disparities in performance to support data-driven decision making.  

---

## 📊 Dataset  
- **Source**: NYC Department of Education (public dataset).  
- **File**: `schools.csv`  
- **Key Columns**:  
  - School Name  
  - Borough  
  - SAT Critical Reading, Math, Writing Scores  
  - Total SAT Score  

---

## 🔍 Methodology  
1. **Data Cleaning**  
   - Handled missing values with median imputation.  
   - Ensured consistency in data types and score ranges.  

2. **Exploratory Data Analysis (EDA)**  
   - Borough distribution of schools.  
   - Score distributions across subjects.  
   - Top-performing schools by subject and total SAT score.  

3. **Statistical Insights**  
   - Computed borough-level means and standard deviations.  
   - Identified boroughs with the highest variability (Bronx stood out).  

---

## 📸 Visualizations  

Here are some highlights from the analysis:  

- **School Distribution by Borough**  
  ![Borough Distribution]<img width="885" height="579" alt="image" src="https://github.com/user-attachments/assets/19b6d83b-4819-4ca4-beca-d3b962948352" />


- **Schools with Best Math Scores (>= 640)**
   <img width="1034" height="1277" alt="image" src="https://github.com/user-attachments/assets/bdce2570-dd19-4237-abf2-fb11a6ad3dc4" />
 

- **Top 10 Schools by Combined SAT Score**  
  <img width="1310" height="1195" alt="image" src="https://github.com/user-attachments/assets/1454b1f3-da33-40a7-b6a0-c8c9e52a79f0" />

 

- **Borough-Level SAT Performance Comparison**  
  <img width="879" height="574" alt="image" src="https://github.com/user-attachments/assets/873eaa9c-579a-4b88-8210-d1bc7ac84ccd" />
 

- **Total SAT Scores Across Boroughs**  
  <img width="891" height="574" alt="image" src="https://github.com/user-attachments/assets/355791e6-4cb2-4909-b1d9-f72fbe2b1022" />



> ℹ️ *All visuals are generated using Python (Pandas, Matplotlib, Seaborn).*  


---

## 🚀 Key Findings  
- Borough distribution reveals uneven school concentration, with Queens and Brooklyn leading.  
- Several schools achieved **Math SAT averages ≥ 640**, reflecting strong STEM emphasis.  
- The **Top 10 schools by combined SAT** are clear benchmarks of excellence.  
- The **Bronx shows the largest performance variability**, highlighting both top achievers and struggling schools.  

---

## 📌 Recommendations  
- **Targeted support** for underperforming schools in high-variability boroughs (e.g., Bronx).  
- **Scale successful practices** from high-achieving math schools to others.  
- **Parent/student guidance**: data-driven insights to help families in school selection.  
- **Further research**: incorporate socioeconomic and resource allocation data.  

---

## 🛠️ Tools & Technologies  
- **Python** (Pandas, NumPy, Matplotlib, Seaborn)  
- **Jupyter Notebook**  
- **ReportLab** (for PDF reporting)  
- **GitHub** (for version control and portfolio presentation)  

---

## 👤 Author  
**UGOCHUKWU JOSHUA TOLUWALEKE**  
- Data Analyst | Storytelling with Data | Python Enthusiast  
- www.linkedin.com/in/joshuaugochukwu(#) | [Portfolio](#)  

---


## 📂 Repository Structure  
├── schools.csv # Dataset
├── NYC_SAT_Analysis.ipynb # Jupyter Notebook (code + visuals + narrative)
├── report.pdf # Stakeholder-ready report
├── images/ # Project visuals (for README display)
│ ├── borough_distribution.png
│ ├── top_schools.png
│ ├── borough_comparison.png
│ └── variability.png
└── README.md # Project documentation
