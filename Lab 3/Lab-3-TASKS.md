---
output:
  pdf_document: default
  html_document: default
---
# GreenLab-LAB3-2024
A set of exercises for the GreenLab Lab 3 2024 (4th October 2024). This lab 
focuses on running basic statistical tests and manipulating data. It will be required
to install libraries `ARTool` and `bestNormalize`. Their respective docs:
https://cran.r-project.org/web/packages/ARTool/readme/README.html
https://cran.r-project.org/web/packages/bestNormalize/vignettes/bestNormalize.html

On top of that you mind need dplyr doc:
https://dplyr.tidyverse.org/

## Exercise 0 - lgg data preprocessing
### Task 1
In a directory data/lgg6 there is data scattered in 3 directories. 
Each directory stores information about measures taken for different devices
(cpu/display/speaker).

Your task is to load the scattered data and combine in into a single tibble with two columns:

  1. `Joule_calculated` which is a numerical variable
  2. `experiment` which is a factor with 3 values: `cpu_test`, `display_test`, `speaker_test`

To solve this question use a function `list.files` and pass correct `pattern` parameter.
Then divide it into 3 vectors with `grepl` command to find files corresponding to proper device
and at the end concatenate them.

At this point you should end up with a vector of paths, which then you can
load with `lapply`, `read_csv` and `bind_rows` into a single tibble.
Finally add the column corresponding to the experiment type as a factor.

### Task 2
Visualize `Joule_calculated` for each experiment type and test it for normality.
You can utilize `group_by`, `group_split` and `lapply` with R lambda functions
to create all the plots at the same time. You can also use `summarize` function
to run all the tests.

### Task 3
Test if different experiments have different mean joule calculated.
Use a proper test (parametric/non-parametric) and rationalize it.

## Exercise 1 - Normalization
The Autotrader data contains information about the price of a car with respect 
to its mileage and age. Load it to a dataframe from `data/autotrader/data.csv`. 

### Task 4
Fit a linear model with response variable `price` and predictor variables 
`yearsold` and `mileage`. Plot residuals of the model. What's wrong with residuals and why?

### Task 5
Use histograms and normality tests to verify which variables need normalizing.
Normalize relevant vairables using `bestNormalize` function from the bestNormalize
library. Perform the same steps as in the previous tasks, except use normalized 
variables.
What change can you see?

## Exercise 2 - ART
### Task 6
Load the data from `./data/dry_matter/data.csv`. It's a data frame from an 
experiment in which the effects of Moisture and Fertilizer on DryMatter in 
peat pots was tested.
Columns `Fertilizer`, `Tray` and `Moisture` are factors, while column `DryMatter`
will be the response variable.

Construct a model using art() function (Aligned Rank Transform) with the fixed effects and all of their 
interactions (Moisture*Fertilizer) and a grouping term (1|Tray).

Run `anova()` on the constructed model and draw conclusions from the output.
Plot the residuals to validate normality of the errors.
