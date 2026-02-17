**Pakistan Crimes Analysis (2000–2024)**

Comprehensive national crime trend analysis with socioeconomic correlations

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-CC%20BY--SA%204.0-green.svg)](LICENSE)
[![Data Source](https://img.shields.io/badge/Data-Pakistan%20Bureau%20of%20Statistics-orange.svg)](https://www.pbs.gov.pk/)


**Overview**

This project examines 25 years of crime data in Pakistan (2000–2024) and explores how crime rates correlate with key socioeconomic indicators. Through statistical analysis and data visualization, I investigate whether literacy, economic development, unemployment, poverty, and urbanization have measurable relationships with national crime patterns.

The goal is to provide evidence-based insights that can inform policy decisions, resource allocation, and crime prevention strategies.

Table of Contents

[Dataset](#dataset)
[Key Findings](#key-findings)
[Visualizations](#visualizations)
[Methodology](#methodology)
[Project Structure](#project-structure)
[Installation & Usage](#installation--usage)
[Technologies Used](#technologies-used)
[Data Sources](#data-sources)
[Limitations](#limitations)
[Future Work](#future-work)
[Contributing](#contributing)
[License](#license)
[Contact](#contact)


Dataset

The dataset integrates crime statistics with socioeconomic indicators spanning 25 years.

**What's Included**

Crime Data (9 categories tracked):
Murder
Attempt to Murder  
Kidnapping / Abduction
Dacoity
Robbery
Burglary
Cattle Theft
Other Theft
Others (miscellaneous offenses)

**Socioeconomic Variables:**
Population (Census data + projections)
National literacy rate
GDP per capita (USD)
Unemployment rate
Poverty rate
Urbanization rate

**Data Composition**

| Period | Records | Source | Quality |
|--------|---------|--------|---------|
| 2012–2017 | 54 | Pakistan Bureau of Statistics | ✓ Verified official data |
| 2000–2011, 2018–2024 | 171 | Statistical projection | Modeled using OLS regression |

**Total:** 225 records (25 years × 9 crime types)



 **Key Findings**

Based on analysis of verified data (2012–2017):

**Crime & Socioeconomic Correlations**

**Literacy Rate**  
Correlation with crime rate: **r = −0.633**
Interpretation: Higher literacy is associated with lower crime rates
Significance: p = 0.178 (moderate evidence)

**Economic Development**  
Correlation with crime rate: **r = −0.468**  
Interpretation: Higher GDP per capita correlates with reduced crime
Significance: p = 0.349

**Long-term Trends**  
Total crimes recorded (2000–2024): **16.3 million incidents**
Population growth: **+72.5%** (142M → 245M)
Literacy improvement: **+14.5 percentage points** (45% → 59.5%)
Crime rate trend: **Declining** despite population growth

**Crime Distribution**

- **Most common:** "Others" category (79.6% of all crimes)
- **Violent crimes:** Murder + Attempt to Murder = 4.3% of total
- **Property crimes:** Burglary + Robbery + Theft = 10.4% of total



**Visualizations**

Comprehensive Dashboard

![Pakistan Crimes Dashboard](visualizations/pakistan_crimes_dashboard_linkedin.png)

This dashboard presents:
1. **Key Statistics:** Total crimes, average crime rate, population growth, literacy gains
2. **Time Series:** Crime trends by category (2000–2024)
3. **Correlation Heatmap:** Relationships between crime and socioeconomic factors
4. **Scatter Plots:** Crime vs. literacy and crime vs. economic development
5. **Crime Distribution:** Breakdown by offense type
6. **Contextual Trends:** Evolution of literacy, unemployment, and poverty



**Methodology**

Data Collection

Crime data comes from the Pakistan Bureau of Statistics (PBS), the official government source for national statistics. Socioeconomic indicators were compiled from:

**Population:** Pakistan Census 1998, 2017, 2023 + PBS demographic projections
**Literacy:** Pakistan Economic Survey (annual publications 2000–2024), UNESCO Institute for Statistics, Pakistan Social & Living Standards Measurement (PSLM) surveys
**Economic Data:** World Bank Open Data, State Bank of Pakistan annual reports
**Poverty & Development:** World Bank poverty estimates, UNDP Human Development Reports

 **Statistical Approach**

**For verified period (2012–2017):**
Direct extraction from PBS Crime Statistics Portal
No estimation or modeling required

**For extended coverage (2000–2011, 2018–2024):**
1. Calculated per-capita crime rates from verified data
2. Fitted linear regression models for each crime type
3. Applied trends to historical and future population estimates
4. Added realistic variance (±5%) to avoid artificial smoothness
5. Clearly tagged all projections in Data_Source column

**Correlation Analysis:**
Pearson correlation coefficients calculated
Two-tailed significance tests performed
Limited to verified data only (2012–2017) for robustness

**Data Integrity**

All projections are:
Based on established statistical methods
Transparent and reproducible
Clearly documented in the datasetConservative (using linear trends, not complex models)


## Technologies Used

- **Python 3.12** – Data analysis and visualization
- **Pandas** – Data manipulation and cleaning
- **NumPy** – Numerical computations
- **SciPy** – Statistical testing (correlation, regression)
- **Matplotlib** – Visualization framework
- **Seaborn** – Statistical data visualization
- **Jupyter Notebook** – Interactive analysis environment
- **Microsoft Excel / LibreOffice Calc** – Multi-sheet data workbook


## Data Sources

All data is from official, publicly accessible sources:

### Primary Sources

1. **Pakistan Bureau of Statistics (PBS)**  
   Crime Statistics Portal: [https://social.data.gov.pk/](https://social.data.gov.pk/)  
   Pakistan Census 1998, 2017, 2023

2. **World Bank Open Data**  
   GDP, poverty, urbanization: [https://data.worldbank.org/](https://data.worldbank.org/)

3. **Pakistan Economic Survey**  
   Annual reports (2000–2024): [https://www.finance.gov.pk/](https://www.finance.gov.pk/)

4. **UNESCO Institute for Statistics**  
   Literacy data: [http://uis.unesco.org/](http://uis.unesco.org/)

5. **State Bank of Pakistan**  
   Economic indicators: [https://www.sbp.org.pk/](https://www.sbp.org.pk/)

### Data Availability

- **Fully verified:** 2012–2017 (PBS Crime Portal)
- **Projected:** 2000–2011, 2018–2024 (statistical extrapolation clearly documented)

---

## Limitations

This analysis has important constraints to keep in mind:

1. **Projected Data:** Crime figures for 2000–2011 and 2018–2024 are statistical estimates, not official records. They assume linear trends, which may not capture non-linear changes.

2. **Reporting Accuracy:** Crime statistics depend on reporting rates. Underreporting (especially of certain crimes) may affect accuracy.

3. **National Level Only:** Provincial or district-level breakdowns are not available for the full 25-year period. Regional variations are not captured.

4. **Correlation vs. Causation:** Statistical correlations do not prove causation. Multiple factors influence crime beyond those analyzed here.

5. **COVID-19 Impact:** The 2020–2021 period may show unusual patterns due to pandemic-related lockdowns and reporting changes.

6. **"Others" Category:** This broad category (79.6% of crimes) includes many offense types, limiting granular analysis.



## Future Work

Potential extensions of this analysis:

- [ ] Incorporate provincial-level data (2012–2017) for regional comparisons
- [ ] Add time-series forecasting models (ARIMA, Prophet)
- [ ] Machine learning classification: predict crime category based on socioeconomic factors
- [ ] Panel regression analysis with fixed effects
- [ ] Integrate additional variables: education spending, police per capita, judicial efficiency
- [ ] Interactive dashboard using Plotly/Dash for real-time exploration
- [ ] Comparison with neighboring countries (India, Bangladesh, Afghanistan)

Contributions are welcome! See [Contributing](#contributing) below.

---

## Contributing

I welcome suggestions, corrections, and contributions to improve this analysis.

### How to Contribute

1. **Fork this repository**
2. **Create a feature branch:** `git checkout -b feature/your-feature-name`
3. **Commit your changes:** `git commit -m "Add your message"`
4. **Push to the branch:** `git push origin feature/your-feature-name`
5. **Open a Pull Request**

### Issues

If you find errors or have questions:
- Open an issue on GitHub
- Provide detailed information (what you found, what you expected, screenshots if relevant)

---

## License

This project is licensed under the **Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)**.

**You are free to:**
- ✓ Share — copy and redistribute the material
- ✓ Adapt — remix, transform, and build upon the material for any purpose, even commercially

**Under the following terms:**
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made
- **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license

See [LICENSE](LICENSE) file for full details.

### Citation

If you use this dataset or analysis in academic work, please cite:

> Rabbani, M. (2024). Pakistan Crimes Analysis (2000–2024): National trends with socioeconomic correlations. GitHub repository. https://github.com/YOUR-USERNAME/pakistan-crimes-analysis

---

## Contact

**Mohammad Rabbani**  
Data Analyst & Research Consultant

- **LinkedIn:** www.linkedin.com/in/rabbani-analyst
- **Kaggle:** (https://www.kaggle.com/rabbani0123)
- **Email:** mrabbani777tcd@gmail.com
- **Location:** Mingora, Khyber Pakhtunkhwa, Pakistan

### Let's Connect!

I am always interested in discussing data analysis, criminology research, development economics, or potential collaboration opportunities. Feel free to reach out!

---

**⭐ If you find this project useful, please consider starring it on GitHub! It helps others discover this work.**

---

*Last updated: February 2026*
