# NYC Public School SAT Performance Analysis

An end-to-end exploratory data analysis of historical SAT results for 375 New York City public high-school records. The project preserves the original three questions—high Math scores, top combined scores, and borough-level variation—while adding data-quality controls, statistical interpretation, validation, reproducible charts, and an automated PDF report.

> **Historical-score warning:** this file uses the legacy three-section SAT format (Math, Critical Reading/Reading, and Writing), each scored from 200 to 800, giving a combined range of 600–2,400. It is not the current Digital SAT, which has two sections and a 400–1,600 total score. Do not compare these totals directly with current Digital SAT results. See the [College Board's current SAT structure](https://satsuite.collegeboard.org/sat-school-day/taking-the-test/structure).

## Project questions

1. Which NYC schools have an average Math score of at least 640 (80% of the 800-point section maximum)?
2. Which ten schools have the highest combined score, calculated as the sum of their three school-level section averages?
3. Which borough has the largest standard deviation in combined school-level SAT scores?

The 640 Math cutoff is a project-defined screening threshold, not an official College Board proficiency benchmark. The analysis is descriptive and is intended to identify patterns and questions for further investigation—not to determine overall school quality.

## Dataset and grain

- **Dataset:** [NYC Public School SAT Performance — Kaggle](https://www.kaggle.com/datasets/mohamedmostafa259/nyc-public-school-sat-performance-dataset)
- **File:** `schools.csv`
- **Observed size:** 375 rows × 7 columns.
- **Grain:** one row represents one school record, not one student and not one physical building.
- **Coverage:** the analysis describes the 375 records in this file. It does not establish that every NYC public high school is represented.
- **Date:** the Kaggle upload/update date is not necessarily the SAT testing year. The exact testing year for this copy is not established in this repository; treat the data as historical, not current.
- **Reproducibility:** a copy of the CSV is included in the repository.

### Data dictionary

| Column | Meaning | Expected type / valid values |
|---|---|---|
| `school_name` | School name | Text |
| `borough` | NYC borough | Text; Bronx, Brooklyn, Manhattan, Queens, Staten Island |
| `building_code` | Building identifier | Text; repeated values are possible |
| `average_math` | School's average legacy SAT Math score | Integer, 200–800 |
| `average_reading` | School's average legacy SAT Critical Reading score | Integer, 200–800 |
| `average_writing` | School's average legacy SAT Writing score | Integer, 200–800 |
| `percent_tested` | Percentage of students tested | Numeric, 0–100; may be missing |

## End-to-end workflow

1. **Problem definition:** state the three original questions, the intended stakeholders, and the limits of descriptive school-level comparisons.
2. **Understand the data:** inspect dimensions, field names, data types, summaries, example records, unique school names, and unique building codes.
3. **Validate raw data:** audit missing values, exact duplicates, repeated names and building codes, borough labels, numeric types, SAT ranges, and participation percentages.
4. **Clean carefully:** trim surrounding whitespace and convert numeric columns explicitly. Keep all school rows. Preserve missing participation values rather than imputing them.
5. **Validate after cleaning:** confirm the expected columns and types, no new missing values from conversion, consistent borough labels, no exact duplicate rows, no duplicate school names, and unchanged row count.
6. **Engineer a feature:** calculate `total_SAT` only when all three section averages are present; validate the arithmetic and the 600–2,400 range.
7. **Explore and analyse:** identify schools above the Math threshold, rank the top ten, compare borough group sizes/means/medians/standard deviations, and inspect the score distributions.
8. **Investigate outliers:** use the IQR rule to flag unusual combined scores. Do not delete a school simply because its score is statistically unusual.
9. **Examine relationships:** calculate Pearson and Spearman correlations among SAT sections and between participation and combined score.
10. **Validate results:** check rankings, group totals, engineered values, correlation bounds, participation sample size, chart files, and report generation.
11. **Interpret responsibly:** distinguish average from median, dispersion from achievement, association from causation, and school-level averages from individual student results.

## Data-quality findings

The current `schools.csv` file contains:

- **375 school records** and 7 columns.
- **No missing values** in school name, borough, building code, or the three SAT section averages.
- **20 missing `percent_tested` values** (5.33%). These remain missing; they are not converted to zero.
- **0 exact duplicate rows** and **0 repeated school names**.
- **233 unique building codes**. Some building codes repeat because more than one school can share a building; repeated codes are not treated as duplicate schools.
- All observed borough labels match the five expected NYC boroughs.
- The observed section score ranges are Math 317–754, Reading 302–697, and Writing 284–693. The allowed legacy section range is 200–800.
- Reported participation values range from 18.5% to 100%, within the valid 0–100% range.

Cleaning does not remove rows. The 20 missing participation values only reduce the sample available for the participation relationship analysis.

## Results from the current file

### Original project questions

- **Math threshold:** 10 schools have an average Math score of at least 640.
- **Highest combined school-level score:** Stuyvesant High School, 2,144 out of 2,400.
- **Largest within-borough standard deviation:** Manhattan, 230.29 points across 89 school records.

### Borough comparison

| Borough | Schools | Mean | Median | Sample standard deviation |
|---|---:|---:|---:|---:|
| Staten Island | 10 | 1,439.00 | 1,382 | 222.30 |
| Queens | 69 | 1,345.48 | 1,290 | 195.25 |
| Manhattan | 89 | 1,340.13 | 1,284 | 230.29 |
| Brooklyn | 109 | 1,230.26 | 1,186 | 154.87 |
| Bronx | 98 | 1,202.72 | 1,190 | 150.39 |

Interpretation:

- Staten Island has the highest mean in this file, but it has only 10 school records. Its result should not be treated as a definitive borough-wide student average.
- Manhattan has the largest standard deviation. This means its recorded school scores are more spread out; it does **not** mean Manhattan has the highest achievement.
- The mean is higher than the median in every borough, consistent with a higher-scoring upper tail in the school-level distributions.
- Borough means are **unweighted**: each school contributes equally because student enrollment and SAT test-taker counts are not included. They are not averages across all individual students in a borough.
- Pandas' default `std()` uses the sample standard deviation (`ddof=1`).

### Distributions and outliers

The global IQR rule flags 27 potential high-score outliers above the upper fence (about 1,590.8); none fall below the lower fence (about 896.8). These observations may be genuine high-performing schools. The count uses one global IQR fence across all schools; the borough boxplot calculates separate whiskers and visual outlier markers within each borough, so the two counts need not match. An IQR flag is a prompt to inspect a record, not proof of an error and not a reason to remove it automatically.

### Relationships among SAT sections

Pearson correlations are:

- Math–Reading: **0.928**
- Math–Writing: **0.934**
- Reading–Writing: **0.985**

Spearman correlations are also strongly positive: 0.875, 0.884, and 0.965 respectively. The especially high Reading–Writing relationship means schools with higher average Reading scores in this file also tend to have higher average Writing scores. These are school-level associations, not evidence that one section causes another.

### Participation versus performance

Among the **355 schools** with a reported participation percentage:

- Pearson correlation: **0.604**
- Spearman correlation: **0.606**

This is a positive association: schools with higher reported participation tend to have higher combined school-level section averages in this dataset. It does not show that increasing participation would cause scores to rise. School selectivity, student composition, resources, socioeconomic context, and other unmeasured factors could influence both variables. The 20 schools with missing participation percentages are excluded from this pairwise analysis, and their missingness may not be random.

## Visualizations

All six figures are generated by executing the notebook and saved under `images/`.

| Figure | Purpose |
|---|---|
| [Math threshold schools](images/01_math_benchmark_schools.png) | Schools with average Math ≥ 640 |
| [Top 10 combined scores](images/02_top_10_combined_sat.png) | Highest sums of the three school-level section averages |
| [Borough mean and variation](images/03_borough_mean_and_variation.png) | Borough means and sample standard deviations |
| [Score distribution by borough](images/04_sat_distribution_by_borough.png) | Medians, spread, and potential outliers |
| [SAT-section correlations](images/05_sat_section_correlations.png) | Pearson and Spearman relationships among sections |
| [Participation versus SAT](images/06_participation_vs_sat.png) | Scatterplot and trend line for complete participation pairs |

The participation scatterplot is generated as its own figure; the automated workflow checks that it is a valid image and is not a duplicate of the SAT-section correlation chart.

## Reproduce the analysis

1. Clone or download this repository.
2. Use Python 3.10 or later.
3. Install the dependencies:

```bash
pip install -r requirements.txt
```

4. Open `Analysis of SAT Performance Across NYC Schools.ipynb` in Jupyter Notebook or JupyterLab.
5. Run **Kernel → Restart Kernel and Run All Cells**.

The notebook searches the current folder and its parent folders for `schools.csv`. Charts are saved in the `images/` directory.

### Automated validation

GitHub Actions executes every notebook code cell when the notebook, dataset, dependencies, or workflow changes. It then:

- checks that all code cells executed without notebook errors;
- verifies the six exported PNG files are valid and non-empty;
- checks that the participation chart is not a byte-for-byte duplicate of the section-correlation chart;
- generates `NYC_Schools_SAT_Analysis.pdf` from the current dataset and charts; and
- commits the executed notebook, charts, and PDF to the repository.

The latest successful workflow run is linked from the repository's [Actions page](https://github.com/UCJPENIEL/Analysis-of-SAT-Performance-Across-NYC-Schools/actions).

## Limitations and stakeholder conclusions

- The exact SAT testing year for this Kaggle copy is not established. The three-section score format is historical and is not comparable directly with current Digital SAT totals.
- The analysis covers the 375 records supplied in this file, not necessarily every NYC public high school.
- The unit is the school. Aggregated averages cannot reveal how individual students performed.
- Missing participation data may create selection bias in the 355-school participation analysis.
- Borough means are unweighted because school enrollment/test-taker counts are absent.
- The dataset does not include socioeconomic indicators, school resources, enrollment, student-level outcomes, or longitudinal trends.
- Correlations do not establish causation. The data cannot explain why score differences occur.

**Stakeholder conclusion:** use these findings to identify schools and borough patterns that merit further investigation. Do not use SAT averages alone to rank school quality, infer individual student potential, or make funding decisions. A stronger follow-up would combine current, same-year SAT results with school enrollment, test-taker counts, socioeconomic context, resources, and longitudinal outcomes.

## Repository contents

- `Analysis of SAT Performance Across NYC Schools.ipynb` — end-to-end analysis and executed outputs.
- `schools.csv` — source data copy.
- `images/` — six exported visualizations.
- `NYC_Schools_SAT_Analysis.pdf` — generated visual report.
- `requirements.txt` — Python dependencies.
- `.github/workflows/execute-analysis.yml` — automated notebook execution and validation.

## Tools

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook, ReportLab, GitHub Actions.
