# 🏏 IPL 2025–2026 Performance Analytics Dashboard

An interactive Power BI dashboard analyzing IPL 2025 and 2026 ball-by-ball cricket data to uncover batting performance, bowling efficiency, scoring patterns, team trends, and venue characteristics.

![Power BI](https://img.shields.io/badge/Power%20BI-Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Analytics-0078D4?style=for-the-badge)
![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Transformation-217346?style=for-the-badge)
![Seasons](https://img.shields.io/badge/Seasons-2025%20%7C%202026-2EAD67?style=for-the-badge)

---

## 📌 Project Overview

This project presents an interactive cricket analytics dashboard developed using Microsoft Power BI, covering the Indian Premier League (IPL) 2025 and 2026 seasons.

Using ball-by-ball delivery data, the project transforms raw cricket records into meaningful analytical insights through data cleaning, feature engineering, dimensional data modeling, DAX calculations, and interactive visualizations.

The dashboard explores how teams score runs, how individual batters and bowlers perform, how scoring patterns change across innings phases, and how performance varies across teams and venues.

The objective is to demonstrate an end-to-end data analytics workflow while making cricket performance insights accessible through an intuitive, multi-page dashboard.

## 📊 Project Highlights

| Metric | Value |
|---|---:|
| Seasons analyzed | 2 |
| Matches analyzed | 148 |
| Innings analyzed | 297 |
| Total runs | 53,887 |
| Total runs in 2025 | 26,493 |
| Total runs in 2026 | 27,394 |
| Dashboard pages | 4 |

## 🛠️ Technology Stack

- **Microsoft Power BI Desktop** – Dashboard development and interactive reporting.
- **Power Query (M)** – Data cleaning, transformation, and feature engineering.
- **DAX (Data Analysis Expressions)** – Calculated measures, KPIs, and analytical calculations.
- **Dimensional Data Modeling** – Fact and dimension tables with one-to-many relationships.
- **Data Visualization** – Comparative charts, scatter plots, matrices, and KPI cards.

## 📂 Dashboard Pages

The report consists of four analytical pages, each addressing a different aspect of IPL performance.

### 1. Tournament Overview

Provides a consolidated overview of the two IPL seasons.

**Key insights and visuals:**
- Total matches, innings, runs, and batting strike rate.
- Total fours and sixes.
- Season-wise total run comparison.
- Season performance snapshot.
- Scoring distribution across innings phases.
- Top 10 run scorers.
- Top 10 wicket takers.

**Analytical objective:** Understand overall tournament performance and compare the two seasons.

### 2. Batting and Scoring Analysis

Examines how runs are scored throughout an innings and evaluates individual batting performance.

**Key insights and visuals:**
- Scoring tempo across the innings.
- Average runs per over across Powerplay, Middle Overs, and Death Overs.
- Batting impact analysis using runs scored versus strike rate.
- Batting delivery profile comparing boundaries, dot balls, and other scoring deliveries.

**Analytical objective:** Identify scoring patterns, batting effectiveness, and differences in scoring behavior between seasons.

### 3. Bowling and Defensive Analysis

Evaluates bowling performance through scoring control, wicket-taking ability, and phase-wise specialization.

**Key insights and visuals:**
- Bowling impact using economy rate versus dot-ball percentage.
- Bowler phase specialization across Powerplay, Middle Overs, and Death Overs.
- Economy rate comparison by bowling phase and season.
- Overall bowling performance matrix.
- Legal deliveries, dot-ball percentage, economy rate, wickets, and wickets per over.

**Analytical objective:** Understand how bowlers restrict scoring, create pressure, and take wickets across different innings phases.

### 4. Team Strategy and Match Insights

Explores team scoring patterns, innings comparisons, and venue characteristics.

**Key insights and visuals:**
- Average first-innings score by team and season.
- Average innings score comparison between first and second innings.
- Venue-wise average innings scoring comparison.
- Top 10 highest-scoring matches across the two seasons.

**Analytical objective:** Identify differences in team scoring performance, innings scoring trends, and venue-specific scoring characteristics.

## 🧹 Data Preparation and Transformation

The original datasets contained ball-by-ball delivery records from the 2025 and 2026 IPL seasons.

Data preparation was performed using Power Query.

Major preprocessing activities included:

- Handling missing and inconsistent values.
- Standardizing venue names.
- Cleaning and standardizing player names.
- Resolving ambiguous player names.
- Handling missing fielder and dismissal information.
- Correcting inconsistent wicket records.
- Removing identified duplicate or anomalous records.
- Combining the two seasons into a consolidated dataset.

### Feature Engineering

Several cricket-specific columns were derived to support the analysis.

| Derived Column | Description |
|---|---|
| `over_number` | Extracted the over number from the original over notation. |
| `ball_number` | Extracted the delivery number within an over. |
| `total_runs` | Sum of batter runs and extras. |
| `is_legal_delivery` | Identifies legal deliveries, excluding wides and no-balls. |
| `is_wicket` | Identifies recorded wicket events. |
| `is_bowler_wicket` | Identifies wickets credited to the bowler under the project's dismissal rules. |
| `phase_category` | Classifies deliveries into Powerplay, Middle Overs, and Death Overs. |
| `is_boundary` | Identifies deliveries resulting in four or six runs off the bat. |
| `boundary_type` | Categorizes boundaries as 4, 6, or None. |
| `is_dot_ball` | Identifies legal deliveries resulting in zero total runs. |

### Innings Phase Classification

| Phase | Overs |
|---|---|
| Powerplay | 1–6 |
| Middle Overs | 7–15 |
| Death Overs | 16–20 |

## 🏗️ Data Modeling

A dimensional data model was implemented to organize the ball-by-ball dataset and support analytical queries.

**Fact Table**
- `fact_deliveries`

**Dimension Tables**
- `dim_matches`
- `dim_date`
- `dim_batter`
- `dim_bowler`
- `dim_batting_team`
- `dim_bowling_team`
- `dim_dismissed_players`
- `dim_venue`

One-to-many relationships were established between the dimension tables and the central fact table.

This structure provides a consistent foundation for filtering, aggregation, season comparisons, and player-level analysis.

## 📐 DAX Measures and KPIs

DAX measures were developed to calculate the primary batting, bowling, and tournament metrics.

### Batting Metrics

- Runs From Bat
- Balls Faced
- Batting Strike Rate
- Total Boundaries
- Boundary Ball Percentage
- Total Dot Balls
- Dot Ball Percentage

Example:

```DAX
Batting Strike Rate =
DIVIDE(
    [Runs From Bat],
    [Balls Faced]
) * 100
```

### Bowling Metrics

- Runs Conceded
- Legal Balls Bowled
- Economy Rate
- Bowler Wickets
- Bowler Dot Balls
- Bowler Dot Ball Percentage
- Wickets per Over

Example:

```DAX
Economy Rate =
DIVIDE(
    [Runs Conceded],
    [Legal Balls Bowled]
) * 6
```

### Match and Team Metrics

- Total Matches
- Total Innings
- Total Runs
- Average Innings Score
- Average First Innings Score
- Average Second Innings Score

## 🎨 Dashboard Design and Interactivity

The report uses a consistent dark navy theme with contrasting white visual panels.

Key design considerations:
- Season-wise color comparisons.
- Consistent typography and chart titles.
- Interactive season and team slicers.
- Cross-filtering between visuals.
- KPI cards for high-level performance indicators.
- Conditional formatting in bowling performance matrices.
- Tooltips for additional analytical context.

The objective was to make the report intuitive for users while maintaining analytical depth.

## 🚀 How to Explore the Project

1. Clone or download this repository.
2. Install Microsoft Power BI Desktop.
3. Open the `.pbix` file from the `PowerBI` folder.
4. If prompted, configure the source-data paths to match your local environment.
5. Refresh the dataset if the original source files are available.
6. Explore all four dashboard pages using the season and team slicers.

**Note:** The original dataset files may not be included in this repository. Refer to the dataset source and licensing information below.

## 📚 Dataset and Attribution

The project uses IPL 2025 and 2026 ball-by-ball cricket datasets.

- Dataset source:
  
**https://www.kaggle.com/datasets/sahiltailor/ipl-2024-ball-by-ball-dataset?select=ipl_2025_deliveries.csv**
**https://www.kaggle.com/datasets/sahiltailor/ipl-2024-ball-by-ball-dataset?select=ipl_2026_deliveries.csv**
- Data coverage: IPL 2025 and IPL 2026.
- Granularity: Individual ball-by-ball deliveries.
- Data preparation: Power Query.

Dataset attribution and licensing information should be retained in accordance with the original provider's terms.

## ⚠️ Data Limitations

The analysis is based on the fields available in the ball-by-ball datasets.

- Toss winner and toss decision analysis is not included because those fields were unavailable.
- Actual match-winner and win-percentage analysis is not included because reliable match-result information was unavailable.
- Match dominance is not inferred solely from the difference between final innings scores.
- Detailed extras analysis is not included in the current dashboard.

The report focuses on metrics that can be supported by the available data.

## 💡 Key Learnings

This project provided practical experience in:

- Cleaning and transforming real-world structured datasets.
- Applying domain-specific feature engineering.
- Designing fact and dimension tables.
- Building DAX measures and understanding filter context.
- Developing interactive Power BI reports.
- Selecting appropriate visualizations for analytical questions.
- Validating metrics and investigating inconsistencies.
- Translating raw data into meaningful insights.

## 👨‍💻 Author

**Mukesh Venkatesh**

Final-year B.Tech – Computer Science and Engineering (AI & Data Science)

Interested in Data Analytics, Data Science, and Machine Learning.

---

⭐ If you find this project interesting, feel free to explore the dashboard and its analytical approach.
