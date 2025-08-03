# SCT DS Task 2 - Titanic Dataset Exploratory Data Analysis

## 🚢 Project Overview
Comprehensive Exploratory Data Analysis (EDA) on the legendary Titanic dataset, uncovering patterns, relationships, and insights from passenger data. This project demonstrates advanced data cleaning techniques, statistical analysis, and visualization skills as part of the **SkillCraft Technology Internship Program**.

## 🎯 Objectives
- Perform thorough data cleaning and preprocessing
- Explore relationships between variables through statistical analysis
- Create meaningful visualizations to identify patterns and trends
- Handle missing data effectively using appropriate imputation techniques
- Generate actionable insights from passenger demographics and fare structures

## 🛠️ Technologies Used
- **Python 3.x** - Core programming language
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **Seaborn** - Statistical data visualization
- **Matplotlib** - Plotting and visualization
- **Jupyter Notebook** - Interactive development environment

## 📊 Dataset Information
- **Source**: Titanic dataset (test.csv)
- **Records**: 418 passengers
- **Features**: 11 columns including demographics, ticket info, and fare data
- **Missing Data**: Age (86 missing), Cabin (327 missing), Fare (1 missing)

## 🔍 Key Analyses Performed

### Data Cleaning & Preprocessing
- **Missing Value Treatment**: 
  - Age: Filled with median (practical approach for age data)
  - Fare: Single missing value filled with median
  - Cabin: Dropped due to 78% missing data
- **Data Type Optimization**: Converted IDs and tickets to string format
- **Duplicate Detection**: Verified no duplicate records

### Statistical Analysis
- **Fare Analysis by Class**:
  - 1st Class: $87.51 average
  - 2nd Class: $21.18 average  
  - 3rd Class: $13.30 average
- **Port-based Fare Patterns**:
  - Port C: $66.26 average (premium passengers)
  - Port S: $28.18 average
  - Port Q: $10.96 average (budget travelers)

### Visualization Insights
1. **Age Distribution**: Right-skewed with median around 28 years
2. **Fare by Gender**: Males generally paid higher fares
3. **Class Demographics**: Clear socioeconomic stratification
4. **Port Analysis**: Distinct passenger profiles by embarkation point

## 📈 Key Visualizations Created

### Distribution Analysis
- **Age Histogram with KDE**: Shows passenger age distribution patterns
- **Fare Boxplots**: Reveals fare disparities across different segments

### Relationship Analysis  
- **Correlation Heatmap**: Identifies numerical variable relationships
- **Class vs Fare**: Demonstrates clear economic stratification
- **Age vs Class Violin Plots**: Shows age distribution patterns across classes

### Categorical Analysis
- **Embarkation Port Analysis**: Passenger volume and class distribution
- **Gender Distribution**: Demographics across passenger classes

## 🎨 Visualization Gallery

### Statistical Distributions
```python
# Age distribution with density curve
sns.histplot(df["Age"], kde=True, color="orange")

# Fare analysis by gender
sns.boxplot(x="Sex", y="Fare", data=df, color="green")
```

### Relationship Analysis
```python
# Numerical correlations
sns.heatmap(numerical_df.corr(), annot=True, cmap="coolwarm")

# Class-based fare analysis
sns.boxplot(x="Pclass", y="Fare", data=df)
```

### Advanced Visualizations
```python
# Age distribution across classes
sns.violinplot(x="Pclass", y="Age", data=df, color="purple")

# Multi-dimensional categorical analysis
sns.countplot(x="Embarked", hue="Pclass", data=df, palette="dark:green")
```

## 💡 Key Insights Discovered

### Economic Stratification
- **Clear Class-Fare Correlation**: Higher class passengers paid significantly more
- **Port Premium**: Passengers from Port C paid 2-6x more than others
- **Gender Patterns**: Notable fare differences between male and female passengers

### Demographic Patterns
- **Age Distribution**: Relatively young passenger base (median 28 years)
- **Class Demographics**: Each class showed distinct age and fare profiles
- **Geographic Patterns**: Different ports served different socioeconomic segments

### Data Quality Insights
- **Missing Data Patterns**: Cabin information missing for majority (systematic issue)
- **Age Data**: 20% missing but successfully imputed using median
- **High Data Integrity**: No duplicates, consistent formatting

## 🗂️ Project Structure
```
SCT_TrackCode_Task2/
├── README.md                        # Project documentation
├── Task2_Titanic_EDA.ipynb         # Main analysis notebook
├── data/                           # Dataset files
│   └── titanic_test.csv
├── visualizations/                 # Generated plots
│   ├── age_distribution.png
│   ├── fare_analysis.png
│   └── correlation_heatmap.png
└── requirements.txt                # Dependencies
```

## 🚀 How to Run

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### Execution Steps
1. Clone repository:
   ```bash
   git clone https://github.com/yourusername/SCT_TrackCode_Task2.git
   ```
2. Navigate to directory:
   ```bash
   cd SCT_TrackCode_Task2
   ```
3. Launch Jupyter:
   ```bash
   jupyter notebook Task2_Titanic_EDA.ipynb
   ```
4. Run all cells to reproduce analysis

## 📚 Learning Outcomes

### Technical Skills Developed
- **Advanced EDA Techniques**: Multi-dimensional data exploration
- **Data Cleaning Mastery**: Handling missing values and data quality issues
- **Statistical Analysis**: Groupby operations and correlation analysis
- **Visualization Expertise**: Multiple plot types for different data insights
- **Pattern Recognition**: Identifying meaningful trends in complex datasets

### Domain Knowledge Gained
- **Historical Data Analysis**: Understanding socioeconomic patterns from 1912
- **Maritime Transportation**: Passenger classification and pricing structures
- **Data Storytelling**: Extracting human narratives from numerical data

## 🎯 Business Applications

### Real-World Relevance
- **Customer Segmentation**: Understanding different customer profiles
- **Pricing Strategy**: Analyzing price sensitivity across demographics
- **Market Research**: Identifying patterns in consumer behavior
- **Risk Assessment**: Understanding demographic risk factors
- **Service Optimization**: Tailoring services to different customer segments

### Industry Applications
- **Transportation**: Passenger analysis and service optimization
- **Hospitality**: Customer segmentation and pricing strategies  
- **Insurance**: Risk assessment and demographic analysis
- **Retail**: Customer profiling and targeted marketing

## 📊 Statistical Summary

| Metric | Value | Insight |
|--------|-------|---------|
| **Total Records** | 418 | Complete test dataset |
| **Data Completeness** | 79% | After cleaning missing values |
| **Age Range** | 0.17 - 76 years | Wide demographic spread |
| **Fare Range** | $0 - $512.33 | Extreme fare variations |
| **Class Distribution** | 3rd: 218, 1st: 107, 2nd: 93 | Majority budget travelers |

## 🔍 Code Highlights

### Efficient Data Cleaning
```python
# Smart missing value handling
df["Age"] = df["Age"].fillna(df["Age"].median())
df["Fare"] = df["Fare"].fillna(df["Fare"].median())
df = df.drop(columns=["Cabin"])  # Strategic column removal
```

### Advanced Groupby Analysis
```python
# Multi-level statistical analysis
df.groupby("Pclass")["Fare"].mean()
df.groupby(["Sex", "Pclass"])["Age"].describe()
```

### Professional Visualizations
```python
# Clean, publication-ready plots
sns.violinplot(x="Pclass", y="Age", data=df, color="purple")
plt.title("Age Distribution Across Passenger Classes")
```

## 🤝 Contributing
Educational project for SkillCraft Technology Internship. Suggestions welcome through:
1. Fork the repository
2. Create feature branch
3. Submit pull request

## 📞 Contact Information
**Author**: [Your Name]  
**Program**: SkillCraft Technology Internship  
**LinkedIn**: [Your LinkedIn Profile]  
**Email**: [Your Email]  

## 📜 License
Created for educational purposes as part of SkillCraft Technology Internship Program.

---

**⭐ Star this repository if you found the analysis insightful!**

---

### 🏷️ Keywords
`exploratory-data-analysis` `titanic-dataset` `python` `pandas` `seaborn` `data-cleaning` `statistical-analysis` `data-visualization` `eda` `skillcraft-technology` `internship-project` `data-science`
