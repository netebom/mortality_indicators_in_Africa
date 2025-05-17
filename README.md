# 🌍 Mortality and Immunization Trends in Africa

## 📌 Project Overview
This project explores mortality trends in Africa and their relationship with immunization coverage using public health datasets from the World Health Organization (WHO). It aims to uncover disparities in maternal, child, and youth mortality and propose data-driven policy interventions.

---

## 🎯 Objectives
- Analyze causes and rates of mortality across African regions
- Study immunization coverage and its correlation with survival rates
- Merge multiple WHO datasets into a unified analytical view
- Provide actionable public health insights and visualizations

---

## 📊 Datasets Used
- **Births Attended by Health Staff**
- **Infant, Child, and Youth Mortality Rates**
- **Maternal Mortality by Region**
- **Vaccination Coverage**
- **Cause of Death in Children Under 5**
- **Health Protection Coverage**

All datasets filtered to include only African countries using ISO codes.

---

## 🧰 Tools & Libraries
- **Python**: Pandas, NumPy
- **Visualization**: Matplotlib, Seaborn, Plotly Express, Plotly GraphObjects
- **Jupyter Notebook**

---

## 🧪 Key Steps
1. **Data Cleaning & Integration**:
   - Renamed columns, handled nulls, matched country names to ISO codes
   - Merged 8 datasets by `Entity`, `Code`, and `Year`
2. **Exploratory Data Analysis (EDA)**:
   - Trend lines for mortality over time
   - Bar plots and heatmaps for regional comparisons
3. **Visualization & Insight Generation**:
   - Identified countries with highest/lowest health coverage
   - Compared immunization and child survival rates across Africa

---

## 📈 Key Insights
- Higher immunization coverage is strongly associated with reduced child mortality
- Sub-Saharan Africa continues to face higher maternal death rates than North Africa
- Disparities exist even among neighboring countries with similar GDP levels

---

## 💡 Public Health Impact
This project provides evidence to support targeted immunization campaigns, resource allocation, and region-specific health interventions. It can assist NGOs, health ministries, and global health donors in prioritizing funding and policies.

---

## 📁 Repository Contents
- `mortality_rates_in_africa.ipynb` — Main analysis notebook
- `datasets/` — All WHO and mortality-related data (filtered to Africa)
- `charts/` — Visualizations and graphs (optional)
- `dashboard.pbix` — Power BI dashboard (if applicable)

---

## 📄 Author
**Etebom Ntuk**  
Data Analyst | [GitHub](https://github.com/netebom) | 📧 ntuketebom@gmail.com
