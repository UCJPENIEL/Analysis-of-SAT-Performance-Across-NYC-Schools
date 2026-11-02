# NYC Public School SAT Performance Analysis

*An end-to-end exploratory data analysis of school-level SAT performance across New York City's five boroughs.*

## Project overview

This project analyzes public high-school SAT results to answer three original questions:

1. Which NYC schools have the strongest average Math SAT results (at least 640 out of 800)?
2. Which schools have the ten highest combined SAT section averages?
3. Which borough has the greatest variation in combined school-level SAT scores?

The analysis preserves these original questions and extends them with data-quality checks, feature validation, distribution analysis, correlation analysis, and stakeholder-focused limitations.

## Dataset and grain

- **File:** `schools.csv`
- **Source:** NYC public-school SAT dataset supplied for this analysis.
- **Grain:** one record per school.
- **Fields:** school name, borough, building code, average Math, Reading and Writing scores, and percentage of students tested.
- **Score scale:** each SAT section ranges from 0 to 800; the combined score ranges from 0 to 2,400.
- **Participation:** percentage tested ranges from 0 to 100 and contains missing observations.

The unit of analysis is the school. These are school-level averages, not individual student records.

## End-to-end analytical workflow

1. **Problem definition:** retain the three original project questions.
2. **Dataset understanding:** inspect dimensions, column names, data types, summary statistics, and the school-level grain.
3. **Raw-data validation:** audit schema, missingness, exact duplicate rows, repeated school names/building codes, categorical values, and valid score/percentage ranges.
4. **Cleaning decisions:** standardize surrounding whitespace and ensure numeric fields are numeric. Missing participation values are retained because they are not needed for SAT totals and should not be fabricated. Shared building codes are investigated, not automatically deleted.
5. **Feature engineering:** calculate combined SAT only when all three section scores are present.
6. **Feature validation:** verify combined scores fall within 0–2,400 and equal the sum of the three sections.
7. **Exploratory and main analysis:** investigate borough distribution, high Math scores, top combined-score schools, borough means, medians, standard deviations, and group sizes.
8. **Relationship analysis:** compare SAT sections using Pearson and Spearman correlations; examine participation versus performance using complete observations.
9. **Post-analysis validation:** reconcile rankings and borough counts with the underlying data.
10. **Communication:** interpret findings with sample sizes, outlier context, and explicit limitations.

## Statistical and analytical considerations

- **Mean** is the arithmetic average and can be influenced by extreme values.
- **Median** is the middle observation and is less sensitive to extreme values.
- **Standard deviation** measures dispersion, not the level of performance. A borough with a larger standard deviation has more variation among its school averages; it does not necessarily have a higher or lower average.
- **Group size** matters. Borough comparisons should be interpreted alongside the number of schools represented.
- **IQR outliers** are flagged for investigation, not automatically removed.
- **Correlation** measures association. It does not demonstrate that participation causes SAT performance to rise or fall.

## Visualizations

The notebook includes:
- School counts by borough.
- Schools meeting the Math benchmark.
- Top ten schools by combined SAT score.
- Borough mean and standard deviation comparisons.
- Borough-level SAT score distributions and potential outliers.
- Pearson and Spearman correlation heatmaps.
- Participation versus combined SAT scatter/regression plot.

## Limitations

- The dataset is observational and school-level; it cannot explain individual student outcomes.
- Participation percentage is missing for some schools. Participation analysis therefore uses complete pairs and reports the sample size.
- Boroughs have unequal numbers of schools, which affects the stability and comparability of summary statistics.
- SAT averages alone do not measure overall school quality, teaching effectiveness, or student potential.
- Socioeconomic conditions, resources, enrollment, student composition, and selection effects are not fully represented.
- Associations cannot be interpreted as causal effects.

## Stakeholder interpretation

Use the analysis to identify patterns, questions for further investigation, and potential areas for additional support—not as a definitive school-quality ranking or a standalone basis for funding decisions. A stronger equity assessment would combine SAT results with school resources, socioeconomic context, enrollment, and longitudinal outcomes.

## Tools

- Python
- Pandas and NumPy
- Matplotlib and Seaborn
- Jupyter Notebook
- Git and GitHub

## Repository contents

- `Analysis of SAT Performance Across NYC Schools.ipynb` — reproducible analysis and narrative.
- `schools.csv` — source dataset.
- `NYC_Schools_SAT_Analysis.pdf` — previously generated report (review separately against the updated notebook before reuse).
- `schoolbus (1).jpg` — project image.

## Run the project

1. Clone or download this repository.
2. Install the required packages: `pandas`, `numpy`, `matplotlib`, `seaborn`, and `jupyter`.
3. Keep `schools.csv` in the same directory as the notebook.
4. Open the notebook and run all cells from top to bottom.

## Author

**Ugochukwu Joshua Toluwaleke**  
Data Analyst | Python | Statistical & Decision Analysis

[LinkedIn](https://www.linkedin.com/in/joshuaugochukwu) · [GitHub](https://github.com/UCJPENIEL)
