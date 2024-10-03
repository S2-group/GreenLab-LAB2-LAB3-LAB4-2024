# GreenLab-LAB3-2024
A set of exercises for the GreenLab Lab 3 2024 (4th October 2024). This lab 
focuses on running basic statistical tests and manipulating data. It will be required
to install libraries `ARTool` and `bestNormalize`. Their respective docs:

https://cran.r-project.org/web/packages/ARTool/readme/README.html

https://cran.r-project.org/web/packages/bestNormalize/vignettes/bestNormalize.html

On top of that you mind need dplyr doc:

https://dplyr.tidyverse.org/

## Exercise 1 - Data loading and inspection
### Task 1
In a directory `data/ease2024/Run_Table_TPCH.csv` there is data describing 
results of Data Analysis Tasks Benchmarking. 

Your task is to load the data in into a single tibble with 4 columns:
`library`, `dataframe_size`, `trial` and our target variable `energy_usage`.

Load the dataframe and transform proper columns into factors.

### Task 2
Visualize `energy_usage` with histograms for each combination of `library` and
`dataframe_size`. You can utilize `group_by`, `group_split` and `lapply` 
with R lambda functions to create all the plots at the same time. 

### Task 3
Test normality of `energy_usage` for each combination of `library` and
`dataframe_size` type with `shapiro.test`.
On top of functions specified in the Task 2 you can also use `summarize` 
function to run all the tests.

## Exercise 2 - Normalization
### Task 4
Normalize target variable `energy_usage` using `bestNormalize` package. Create a 
new column `norm_energy_usage` with normalized data.

### Task 5
Plot `norm_energy_usage` for each combination of `library` and
`dataframe_size` separately and run the normality tests. 
Can you use parametric test with new normalized data?

## Exercise 3 - Parametric and non-parametric tests
### Task 6
Use non-parametric test `wilcox.test` to check whether energy usage is different 
between libraries for small dataframes. What can you observe?

### Task 7
Use art() model to observe influence of `library`, `dataframe_size` and its interactions to
`energy_used`. Treat `trial` as a random effect for repeated measures experiment. 
What can you see? 

Validate your model with `summary(model)`.

### Task 8
Similarly to art, run lmer() model to observe similar effects, except your target
variable should be `norm_energy_used`. 

Verify normality of residuals. How to check if this model is correct?
