# Unemployment Analysis in India with Python

**Author:** Kinjal Nigam

An exploratory data analysis of unemployment in India from **May 2019 to June 2020**, with a focus on the impact of the Covid-19 lockdown. The project covers data cleaning, exploration, visualization, and policy-oriented insights, all in Python.

---

## Objectives

- Clean and prepare the unemployment rate data
- Explore unemployment trends across time, states, and rural vs urban areas
- Measure the impact of Covid-19 on unemployment
- Identify patterns and seasonal trends
- Present insights that could inform economic and social policy

## Dataset

- **Source:** [Unemployment in India (Kaggle)](https://www.kaggle.com/datasets/gokulrajkmv/unemployment-in-india)
- **File used:** `Unemployment in India.csv`
- **Size:** 768 rows x 7 columns (740 rows after removing empty rows)
- **Coverage:** 28 states and union territories, monthly, May 2019 to June 2020

| Column | Description |
|--------|-------------|
| Region | State or union territory |
| Date | Month-end date (dd-mm-yyyy) |
| Frequency | Data frequency (Monthly) |
| Estimated Unemployment Rate (%) | Percentage of the labour force that is unemployed |
| Estimated Employed | Estimated number of employed people |
| Estimated Labour Participation Rate (%) | Share of the working-age population in the labour force |
| Area | Rural or Urban |

## Tools and Libraries

- Python 3
- pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

## Project Workflow

1. **Data cleaning:** renamed columns, stripped whitespace, removed 28 empty rows, converted dates with `dayfirst=True`, and added Month and Year columns.
2. **Exploration:** summary statistics, state-wise averages, rural vs urban comparison, and correlations.
3. **Covid-19 analysis:** split the timeline into four phases (Pre-Covid, Lockdown Onset, Lockdown Peak, Recovery) and compared them overall, by area, and by state.
4. **Visualization:** line charts, bar charts, a state-by-month heatmap, and box plots.
5. **Seasonality check:** monthly pattern using pre-Covid months only, so the lockdown does not distort the result.

## Key Findings

| Phase | Average Unemployment Rate |
|-------|---------------------------|
| Pre-Covid (May 2019 - Feb 2020) | 9.51% |
| Lockdown Onset (Mar 2020) | 10.70% |
| Lockdown Peak (Apr - May 2020) | 24.26% |
| Recovery (Jun 2020) | 11.90% |

1. **A large but short-lived shock.** The average rate rose by 14.75 percentage points (about 2.6x) during the lockdown peak. May 2020 was the highest month at 24.88%. By June it fell to 11.90%, still above the pre-Covid level.
2. **The headline rate understates the damage.** Total estimated employment fell from roughly 400 million to roughly 269 million in April 2020, and the labour participation rate dropped from about 44% to about 35%. Many people left the labour force rather than being counted as unemployed.
3. **Urban areas peaked higher.** Peak rates were 26.93% (urban) vs 21.48% (rural). By June the two had nearly converged (11.98% vs 11.83%), but rural areas remained further above their own pre-Covid level.
4. **States fall into two groups.**
   - *Covid-driven spikes from a low base:* Puducherry (1.59% to 75.42%), Tamil Nadu (2.84% to 40.85%), Karnataka, Telangana, Andhra Pradesh.
   - *Structurally high unemployment:* Haryana (22.94% pre-Covid), Jharkhand (14.28%), Bihar (13.83%), and Tripura.
5. **No clear seasonality.** Pre-Covid rates stayed in a narrow band of roughly 9% to 10%. With only one year of data, a seasonal pattern cannot be confirmed.

## Policy Implications

- **Extend safety nets to cities:** the urban peak was highest, so urban unemployment support or an urban job guarantee is worth considering.
- **Support rural recovery:** rural areas were slower to return to pre-Covid levels, so rural employment programmes remain important.
- **Tailor responses by state:** emergency relief and fast reopening support for Covid-driven states, long-term job creation for structurally high states.
- **Track participation, not only the unemployment rate:** the fall in labour participation shows the headline rate can hide people who stopped looking for work.

## Limitations

- The data covers only 14 months, so real seasonality and long-term trends cannot be established.
- State averages are simple, unweighted averages and do not account for population.
- The data comes from survey estimates (CMIE), not official government statistics.
- Some state values look extreme or noisy, such as Puducherry at about 75% in April and May 2020, which may reflect small-sample effects.
- Missing data: Chandigarh (Apr - May 2020), Jammu & Kashmir (Apr 2020), Goa (Jun 2020), and Sikkim (Jan - Feb 2020).

## Visualizations

Charts are saved in the `images/` folder.

![National unemployment trend](images/national_trend.png)
![Unemployment by Covid-19 phase](images/covid_phases.png)
![State-wise heatmap](images/state_heatmap.png)

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo-name>.git
   cd <your-repo-name>
   ```
2. Install the dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn jupyter
   ```
3. Make sure `Unemployment in India.csv` is in the same folder as the notebook.
4. Launch Jupyter and open the notebook:
   ```bash
   jupyter notebook
   ```
5. Run all cells (**Kernel > Restart & Run All**).

## Repository Structure

```
├── Unemployment in India.csv
├── unemployment_analysis.ipynb
├── images/
└── README.md
```

## Author

**Kinjal Nigam**

---

If you found this project useful, feel free to star the repository.
