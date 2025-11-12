# 🧠 Data-Driven Insights into SAT Performance Across NYC Schools  
*Turning public education data into actionable insights for smarter decisions.*

---

## 🎯 Problem Statement  

Across New York City, SAT performance disparities remain — often tied to socio-economic conditions, school resources, and access to test preparation.  
Yet, policymakers and educators still lack **clear, data-backed visibility** into where these gaps are most significant.  

This project explores one key question:  
> **How can data help us understand and reduce SAT performance disparities across NYC public schools?**

By analyzing borough-level SAT trends, participation rates, and score distributions, this work reveals insights that can shape **fairer educational interventions.**

---

## 💡 Objective  

This project goes beyond data crunching — it shows how **data storytelling** can directly support educational policy by:  

- Revealing **borough-level SAT disparities**  
- Identifying **top-performing and struggling schools**  
- Highlighting **where funding and support** would drive the most impact  
- Demonstrating how **data visualization clarifies complex education patterns**

---

## 📊 Dataset  

**Source:** NYC Department of Education (Public Data)  
**File:** `schools.csv`

**Key Columns:**  
- School Name  
- Borough  
- SAT Critical Reading / Math / Writing Scores  
- Total SAT Score  

---

## 🔍 Analytical Approach  

### 1️⃣ Data Cleaning  
- Handled missing values with median imputation  
- Corrected outliers and standardized borough categories  

### 2️⃣ Exploratory Data Analysis  
- Explored borough distribution of schools  
- Compared SAT performance across subjects and boroughs  
- Identified top-performing schools  

### 3️⃣ Insights Extraction  
- Measured average and variance per borough  
- Linked participation rates with total SAT scores  
- Found boroughs (like **The Bronx**) where **high variability** indicates unequal access to opportunity  

### 4️⃣ Visualization & Storytelling  
Created with **Python (Pandas, Matplotlib, Seaborn)** — focusing on clear, accessible visuals for both technical and non-technical audiences.

---

## 📸 Visual Highlights  

**School Distribution by Borough**  
![Borough Distribution]<img width="885" height="579" alt="image" src="https://github.com/user-attachments/assets/19b6d83b-4819-4ca4-beca-d3b962948352" />


**Top Schools by Math Performance (≥ 640)**  
![Top Math Schools]<img width="1034" height="1277" alt="image" src="https://github.com/user-attachments/assets/bdce2570-dd19-4237-abf2-fb11a6ad3dc4" />

**Top 10 Schools by Combined SAT Score**  
![Top 10 Schools]  <img width="1310" height="1195" alt="image" src="https://github.com/user-attachments/assets/1454b1f3-da33-40a7-b6a0-c8c9e52a79f0" />


**Borough-Level SAT Comparison**  
![Borough Comparison]<img width="879" height="574" alt="image" src="https://github.com/user-attachments/assets/873eaa9c-579a-4b88-8210-d1bc7ac84ccd" />


**Total SAT Scores Across Boroughs**  
  <img width="891" height="574" alt="image" src="https://github.com/user-attachments/assets/355791e6-4cb2-4909-b1d9-f72fbe2b1022" />


---

## 🚀 Key Findings  

| Focus Area | Insight | Implication |
|-------------|----------|-------------|
| **School Distribution** | Queens and Brooklyn host most schools. | Funding and resources should match population density. |
| **Math Performance** | Some schools average ≥ 640 in Math. | Benchmark for best-practice modeling. |
| **Top Performers** | Consistent excellence in top 10 schools. | Study success factors for replication. |
| **Score Variability** | Bronx shows widest score gaps. | Indicates uneven access to prep resources and support. |

---

## 📌 Recommendations  

- 🎯 **Target Interventions** — Prioritize boroughs with high score variability (e.g., The Bronx).  
- 🔁 **Replicate Success Models** — Scale programs from top-performing schools.  
- 👨‍👩‍👧 **Empower Families** — Use insights to guide parents in school selection.  
- 🧩 **Expand Research** — Merge socio-economic and resource data for deeper understanding.  

---

## 🛠️ Tools & Technologies  

- **Python:** Pandas, NumPy, Matplotlib, Seaborn  
- **Jupyter Notebook:** For EDA and narrative analysis  
- **ReportLab:** For stakeholder-ready reports  
- **GitHub:** Version control and portfolio presentation  

---

## 📈 Impact  

This project showcases how data analysis can:  
- Bridge the gap between **raw numbers and educational equity**  
- Support **evidence-based decision-making**  
- Illustrate how **data-driven storytelling** can inform and inspire change  

---

## 👤 Author  

**Ugochukwu Joshua Toluwaleke**  
*Data Analyst | Storytelling with Data | Excel | SQL | Python*  

🔗 [LinkedIn](www.linkedin.com/in/joshuaugochukwu) | [Portfolio](https://github.com/UCJPENIEL/UCJPENIEL)

---

## 📂 Repository Structure  

├── schools.csv # Dataset
├── NYC_SAT_Analysis.ipynb # EDA and visual storytelling
├── report.pdf # Executive summary
├── images/ # Data visualizations
│ ├── borough_distribution.png
│ ├── top_schools.png
│ ├── borough_comparison.png
│ └── variability.png
└── README.md # Project documentation

## 🧩 Why This Project Matters  

This isn’t just a data analysis project — it’s a **real-world problem-solving case study**.  
It demonstrates how analytical insight and storytelling can be powerful tools in driving fairness and performance improvement in education.  

By sharing this work, I hope to:  
- Encourage **data transparency** in public systems  
- Inspire **data-informed decisions** in education  
- Showcase **how data analysis tells meaningful stories**
