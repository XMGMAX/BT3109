# Copilot Instructions for BT3109

## Project Overview

This repository contains a **Spatio-Temporal Framework for Regional Food Security and Climate Impact Modeling**. The project analyzes climate data to understand regional climate patterns and their impact on food security across various regions in India.

## Project Context

- **Domain**: Climate Science & Data Analytics for Food Security
- **Primary Language**: Python 3
- **Key Technologies**: Jupyter Notebooks, pandas, matplotlib, numpy
- **Data Sources**: NASA POWER satellite data, Kaggle climate datasets, local weather data
- **Time Period**: 2010-2024 (15 years of monthly climate data)
- **Geographic Focus**: Multiple Indian regions (Prayagraj, Bangalore, Jaipur, and other coordinates)

## Code Structure

### Main Components

1. **MAIN-FOR-DATA-AS01.ipynb**: Exploratory Data Analysis (EDA)
   - Data loading and initial exploration
   - Descriptive statistics
   - Time-series visualization
   - Rainfall and temperature trend analysis

2. **MAIN-FOR-DATA-AS02.ipynb**: Advanced Analysis
   - Data preprocessing and cleaning
   - Correlation analysis
   - Predictive modeling
   - Spatio-temporal pattern analysis

3. **Data Files**:
   - `POWER_Point_Monthly_*.csv`: NASA POWER satellite climate data for specific coordinates
   - `Bangalore.csv`, `Jaipur.csv`: Local city climate data
   - Additional cleaned datasets referenced in notebooks

## Development Guidelines

### Data Handling

- **Climate Variables**: Focus on rainfall (mm/year) and temperature (°C)
- **Temporal Resolution**: Monthly data aggregated to annual trends
- **Spatial Coordinates**: Use precise lat/lon coordinates in filename format (e.g., `025d44N_081d84E`)
- **Data Integrity**: Always validate data ranges (rainfall: 500-1200mm, temp: 25-28°C)
- **Missing Data**: Document any gaps in the 2010-2024 timeline

### Code Conventions

- Use **pandas** for all data manipulation operations
- Use **matplotlib** for visualizations with clear labels and titles
- Include descriptive variable names (e.g., `mean_annual_rainfall` instead of `mar`)
- Add markdown cells in notebooks to explain each analysis step
- Document data sources with full citations

### Analysis Best Practices

- Always start with `df.head()` and `df.describe()` for initial data exploration
- Create separate visualizations for rainfall and temperature trends
- Use consistent color schemes across all plots
- Include units in all axis labels (mm/year for rainfall, °C for temperature)
- Calculate and report statistical summaries (mean, std, min, max)

### Notebook Structure

Follow this structure for any new analysis notebooks:
1. **Imports**: All required libraries at the top
2. **Data Loading**: Load datasets with clear file paths
3. **Data Exploration**: Initial inspection and statistics
4. **Data Cleaning**: Handle missing values, outliers
5. **Analysis**: Core analytical work with explanatory text
6. **Visualization**: Clear, labeled plots
7. **Conclusions**: Summary of findings

### Common Tasks

#### Loading Climate Data
```python
import pandas as pd
import matplotlib.pyplot as plt

# Load NASA POWER data
df = pd.read_csv('POWER_Point_Monthly_[coordinates]_LST.csv')

# Display basic info
print(df.head())
print(df.describe())
```

#### Creating Time-Series Plots
```python
plt.figure(figsize=(12, 6))
plt.plot(df['Year'], df['Rainfall'], marker='o')
plt.xlabel('Year')
plt.ylabel('Rainfall (mm/year)')
plt.title('Annual Rainfall Trend (2010-2024)')
plt.grid(True)
plt.show()
```

#### Adding New Geographic Regions
When adding new regions:
1. Use NASA POWER API or download data for specific coordinates
2. Name files using format: `POWER_Point_Monthly_[date_range]_[lat]_[lon]_LST.csv`
3. Update analysis notebooks to include the new region
4. Add region to spatial comparison analysis

### Testing and Validation

- Verify all data files load without errors
- Check that date ranges are complete (2010-2024)
- Validate statistical outputs against expected ranges
- Ensure all plots render correctly
- Cross-reference results with known climate patterns

### Dependencies

Core Python libraries required:
- `pandas` >= 1.3.0
- `matplotlib` >= 3.3.0
- `numpy` >= 1.20.0
- `jupyter` or `jupyterlab` for notebook execution

Install using:
```bash
pip install pandas matplotlib numpy jupyter
```

## Working with Copilot

### When Adding New Analysis

- Describe the climate variable you want to analyze (rainfall, temperature, humidity, etc.)
- Specify the geographic region or coordinate
- Indicate the type of analysis (trend, correlation, prediction, comparison)
- Request visualizations with specific chart types

### When Debugging

- Provide the error message and the notebook cell that failed
- Share the shape and structure of the dataframe (`df.info()`)
- Mention which data file is being processed

### When Creating Visualizations

- Specify the type of plot (line, scatter, bar, heatmap)
- Indicate which variables to plot (x-axis, y-axis)
- Request specific styling (colors, labels, legend placement)

## Important Notes

- This is a research project focused on climate impact on food security
- Data spans 15 years (2010-2024) - maintain this consistency
- Geographic focus is on Indian regions
- Results may inform policy decisions on agricultural planning and food security
- Always cite data sources: NASA POWER project, Kaggle datasets, local weather stations

## Questions to Ask Copilot

Good prompts for this project:
- "Load the NASA POWER data for [coordinates] and calculate the mean annual rainfall"
- "Create a time-series plot comparing rainfall trends across all regions"
- "Calculate correlation between rainfall and temperature for [region]"
- "Add a new region analysis for coordinates [lat, lon]"
- "Generate summary statistics for all climate variables"
- "Create a spatial comparison plot showing regional differences"

## Additional Resources

- NASA POWER Project: https://power.larc.nasa.gov/
- Climate data documentation: Check each CSV file header for variable definitions
- Project context: BT3109 coursework on climate modeling and food security
