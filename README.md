# Ford GoBike Usage Analysis

## Overview

This project analyzes Ford GoBike trip activity across the greater San Francisco Bay Area during February 2019.

The analysis examines how customers and subscribers used the bike-share system, how long typical trips lasted, and how trip demand changed across hours and days of the week. The project includes both exploratory and explanatory analysis, progressing from data preparation and pattern discovery to a focused presentation of the most important findings.

The results provide insight into user behavior, commuter demand, trip duration, and differences between subscription-based and occasional riders.

## Analytical Questions

The analysis addresses the following questions:

1. How long are typical Ford GoBike trips?
2. Are most trips taken by subscribers or customers?
3. How does trip duration differ between user types?
4. When are trips most common by hour and day of the week?
5. Do age, gender, and user type show visible relationships with trip duration?

## Dataset

The original dataset contains **183,412 individual bike-share trips** and **16 source fields** from the Ford GoBike system.

The data includes:

- Trip start and end timestamps
- Trip duration
- Start and end stations
- User type
- Member birth year
- Member gender
- Bike-share program participation

Four additional fields were created for analysis:

| Field | Description |
|---|---|
| `duration_min` | Trip duration converted from seconds to minutes |
| `member_age` | Rider age calculated from birth year |
| `start_hour` | Hour when the trip began |
| `day_of_week` | Day when the trip began |

## Data Preparation

The dataset was cleaned and prepared before visualization.

The preparation process included:

- Converting start and end timestamps to datetime values
- Converting trip duration from seconds to minutes
- Calculating rider age
- Extracting trip start hour
- Extracting and ordering days of the week
- Removing rows with missing demographic or station information
- Restricting rider age to a reasonable range of 18 through 80
- Creating a typical-trip subset containing trips of 60 minutes or less

The resulting analysis subset contains **173,374 trips** and **20 fields**.

Long-duration trips were excluded from the primary visual analysis because extreme values made the central trip-duration patterns difficult to interpret.

## Analysis Process

### Exploratory Analysis

The exploratory phase evaluates individual variables and relationships across the dataset.

#### Univariate Analysis

Individual distributions were examined for:

- Trip duration
- User type
- Member age
- Member gender
- Start hour
- Day of the week

#### Bivariate Analysis

Relationships were evaluated between:

- Trip duration and user type
- Trip duration and member age
- Trip duration and gender
- Trip frequency and time of day
- Trip frequency and day of the week

#### Multivariate Analysis

The analysis then examined how multiple variables interacted, including:

- Hourly usage patterns by user type
- Day-of-week demand by time period
- Trip duration across age, gender, and user type

### Explanatory Analysis

The explanatory phase presents the three clearest findings from the exploratory work:

1. Most Ford GoBike trips were short
2. Customers generally took longer trips than subscribers
3. Weekday commute periods produced the highest trip volumes

## Key Findings

### 1. Most trips were short

The median trip duration for the typical-trip dataset was approximately **8.5 minutes**.

The distribution was right-skewed, with most rides concentrated at shorter durations and progressively fewer trips at longer durations.

### 2. Subscribers generated most system activity

Subscribers accounted for most recorded trips, indicating that recurring users were the primary source of system activity during the month analyzed.

This pattern suggests that the service was used extensively for repeated transportation needs.

### 3. Customers took longer trips

Customers completed fewer trips overall but generally had longer trip durations than subscribers.

Subscribers appeared more likely to use the system for shorter, routine trips, while customers appeared more likely to take occasional or extended rides.

### 4. Usage peaked during commute hours

Trip counts were highest during weekday commute periods, particularly around:

- **8:00 AM**
- **5:00 PM**

Weekend activity was lower and more evenly distributed throughout the day.

This pattern indicates that weekday travel and commuting were major components of Ford GoBike demand during February 2019.

### 5. User type was a stronger differentiator than age or gender

Age and gender showed limited visible relationships with trip duration.

Most trips remained relatively short across demographic groups. User type and trip timing provided clearer distinctions in rider behavior.

## Business Relevance

The findings can support bike-share planning in several areas:

- Positioning bikes near high-demand stations before commute periods
- Planning bike and dock availability around morning and evening peaks
- Developing separate engagement strategies for subscribers and occasional customers
- Evaluating whether longer customer trips represent recreational or tourism-related use
- Comparing weekday transportation demand with weekend activity

## Visualizations

The notebooks include:

- Trip-duration histogram
- User-type count chart
- Member-age distribution
- Trip-duration box plots
- Hourly trip distributions
- Weekday trip-count charts
- Age and trip-duration scatter plots
- User-type hourly facet plots
- Day-and-hour heatmap
- Clustered weekday and time-period comparisons

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Repository Structure

```text
.
├── Part_I_notebook.ipynb
├── Part_I_notebook.html
├── Part_II_notebook.ipynb
├── Part_II_notebook.html
├── fordgobike-tripdata.csv
└── README.md
```

### File Descriptions

| File | Description |
|---|---|
| `Part_I_notebook.ipynb` | Full exploratory data analysis |
| `Part_I_notebook.html` | Browser-viewable exploratory analysis |
| `Part_II_notebook.ipynb` | Focused explanatory analysis |
| `Part_II_notebook.html` | Browser-viewable explanatory presentation |
| `fordgobike-tripdata.csv` | Original trip dataset |
| `README.md` | Project overview and findings |

## Running the Analysis

### 1. Clone the repository

```bash
git clone https://github.com/halebeau/ford-gobike-usage-analysis.git
cd ford-gobike-usage-analysis
```

### 2. Install the required packages

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the exploratory notebook

```text
Part_I_notebook.ipynb
```

Run the cells from top to bottom to reproduce the data preparation and exploratory analysis.

### 5. Open the explanatory notebook

```text
Part_II_notebook.ipynb
```

Run the cells from top to bottom to reproduce the final visual presentation.

The file `fordgobike-tripdata.csv` must be stored in the repository root unless the file path inside the notebooks is updated.

## Limitations

- The dataset covers only February 2019
- Results may not represent seasonal or long-term usage patterns
- The analysis is limited to the greater San Francisco Bay Area
- Trips longer than 60 minutes were excluded from the primary visual analysis
- Missing demographic and station records were removed
- Rider age was calculated from birth year and may not reflect the rider’s exact age at the time of every trip
- Observed relationships are descriptive and should not be interpreted as causal

## Potential Enhancements

Future analysis could include:

- Comparing multiple months or years
- Examining seasonal changes in demand
- Mapping high-volume stations geographically
- Identifying common origin and destination combinations
- Measuring station-level bike availability
- Comparing weekday and weekend station demand
- Building an interactive Power BI or Tableau dashboard
- Developing a trip-demand forecasting model
- Analyzing subscriber retention and customer conversion opportunities

## Author

**Beau Hale**

Data Analyst | Web Developer | Technical Business Analyst
