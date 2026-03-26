# Biodiversity and Conservation Analysis in National Parks

## Introduction

Biodiversity plays a critical role in maintaining ecological balance, and national parks are at the center of conservation efforts. Understanding which species are at risk and how they are distributed across parks is essential for effective conservation planning.

In this project, I analyzed biodiversity data from the National Parks Service to explore patterns in species conservation status, identify at-risk categories, and examine how species are distributed across different parks.

Using Python and common data science libraries including Pandas, NumPy, Matplotlib, Seaborn, and SciPy, I explored the dataset through data cleaning, exploratory analysis, statistical testing, and multiple visualizations. These visualizations help highlight patterns in species protection, category-level conservation risk, and park-level observation trends.

The main research questions guiding this analysis are:

- What is the distribution of conservation status for species?
- Are certain types of species more likely to be endangered?
- Are differences in conservation status across species statistically significant?
- Which animals are most prevalent, and how are they distributed across parks?

By analyzing biodiversity records and conservation data, this project aims to provide a clearer picture of how species risk and ecological observations vary across national parks.

---

## Project Overview

This project performs exploratory data analysis and visualization to investigate biodiversity and conservation patterns in national parks.

The analysis includes:

- Exploring the dataset
- Investigating missing conservation status values
- Visualizing conservation status distribution
- Comparing conservation categories across species groups
- Performing statistical significance testing
- Analyzing protected versus non-protected species
- Identifying the most frequently observed animal
- Examining animal observation distribution across parks

The goal is to understand how conservation status varies across species categories and how biodiversity observations are distributed among national parks.

---

## Dataset

The analysis is based on two datasets:

### `species_info.csv`

Contains information about each species, including:

- category
- scientific name
- common names
- conservation status

### `observations.csv`

Contains observation records, including:

- scientific name
- park name
- number of observations

### Columns included in the dataset

| Dataset            | Important Columns                                            |
| ------------------ | ------------------------------------------------------------ |
| `species_info.csv` | category, scientific_name, common_names, conservation_status |
| `observations.csv` | scientific_name, park_name, observations                     |

The data includes species observations across four national parks.

---

## Tools Used

The analysis was conducted using the following Python libraries:

- Pandas for data manipulation
- NumPy for numerical operations
- Matplotlib for visualization
- Seaborn for statistical plotting
- SciPy for Chi-Square testing

These tools enabled efficient data loading, cleaning, exploration, visualization, and statistical analysis.

---

## Project Structure Key Visualizations

text
Biodiversity-Conservation-Analysis/
├── species_info.csv
├── observations.csv
├── biodiversity_analysis.ipynb
├── README.md

## Key Visualizations

The project generates several visualizations to analyze biodiversity and conservation patterns.

### Missing Data by Category

Shows how missing conservation status varies across different species categories.

### Conservation Status Distribution

Displays the overall distribution of species across conservation categories such as:

- no concern
- species of concern
- endangered
- threatened
- in recovery

### Animal Conservation Distribution

Focuses on animal groups such as mammals, birds, reptiles, amphibians, and fish to compare conservation patterns more directly.

### Stacked Bar Chart of Conservation by Category

Shows how protected species are distributed across species categories.

### Bat Observations Across Parks

Displays how bat observations vary across parks and compares protected versus non-protected bat observations.

---

## Key Findings

Several important findings emerge from the analysis:

- The vast majority of species are not under conservation concern.
- **No Concern: 5,633 vs Protected: 191**
- Mammals and birds have the highest proportion of species under protection.
- Mammals and birds do not show a statistically significant difference in conservation percentage.
- Mammals and reptiles do show a statistically significant difference in conservation percentage.
- Bats were identified as the most frequently observed animal.
- Yellowstone National Park had the highest number of bat observations.

---

## Missing Data Analysis

One of the most important findings in the project was that missing conservation status data was not random.

### Observations

- Plants had a very high proportion of missing conservation status
- Mammals and birds had fewer missing values

### Interpretation

This suggests the missingness is not MCAR.

Instead, the pattern indicates:

- Missingness depends on category, which suggests **MAR**
- Domain reasoning suggests missing values likely represent species with no conservation concern, which points toward **domain-driven MNAR**

To proceed with analysis, missing values were filled as:

````python
species['conservation_status'] = species['conservation_status'].fillna('no concern')

## Statistical Analysis

To validate whether the observed conservation differences between species categories were meaningful, Chi-Square tests were used.

### Results

- Mammals vs Birds → Not statistically significant
- Mammals vs Reptiles → Statistically significant

This confirms that conservation status is not uniformly distributed across all species categories.

---

## Key Insights

Several insights emerge from the analysis:

- Most species are not currently under conservation concern
- Missing data reflects real-world conservation recording patterns
- Birds and mammals are more likely to be protected than other groups
- Conservation differences across categories are statistically significant in some cases
- Bats are the most frequently observed species in the dataset
- Yellowstone National Park shows the highest observation counts for bats

---

## Limitations

Although the analysis reveals meaningful biodiversity patterns, several limitations exist:

- The dataset covers only a short time period of observations
- No geographic coordinates are provided for spatial analysis
- Park size is not included, which may affect interpretation of observation counts
- Missing data assumptions rely partly on domain knowledge

---

## Future Work

Potential future improvements for this project include:

- Analyzing biodiversity trends over time
- Incorporating geospatial analysis
- Building predictive models for conservation status
- Including environmental variables such as climate and habitat conditions
- Comparing biodiversity counts relative to park size

---

## How to Run the Project

### Clone the repository

```bash
git clone <your-repository-link>

## How to Run the Project

### Navigate to the project directory

```bash
cd Biodiversity-Conservation-Analysis

## Conclusion

This project demonstrates how data science can be applied to ecological datasets to uncover meaningful patterns in biodiversity and conservation.

The analysis shows that conservation is not evenly distributed across species, but instead varies by category, ecological importance, and observation patterns. It also highlights that missing data is not always just a data quality issue. In some cases, it reflects real-world processes and conservation practices.

By combining data cleaning, visualization, and statistical testing, this project provides a data-driven understanding of biodiversity patterns and conservation priorities across national parks.

---


## Author
Sasi Maddineni

````
