# GreenLab-LAB4-2024: Visualization with R

This repository contains a set of exercises for the GreenLab Lab 4 of 2024 (11th October 2024). The exercises are designed to help students get familiar with the ggplot2 package, some of its different plot types and how customizable and flexible they are.

You can consult `ggplot2_cheat_sheet.pdf` as a reference point.

## **Exercise 0 - Install and load the ggplot2 package. Load data**

In a new R Markdown document, install and load ggplot2. Load `Run_Table_TPCH.csv` as a data frame.

## **Exercise 1 - Box plot**

**Task 1:** Create a boxplot to visualize the distribution of `energy_usage` for each combination of `library` and `dataframe_size`

**Task 2**: Label the x-axis as ”Dataframe Size” and the y-axis as ”Energy Usage”

## **Exercise 2 - Violin plot**

**Task 3:** Create a violin plot of `energy_usage` for each combination of `library` and `dataframe_size`

**Task 4:** Overlay a boxplot inside the violin plot to show statistical summary.

**Task 5:** add `geom_jitter()` to overlay individual datapoints.

## **Exercise 3 - Boxplot + mean and standard error**

**Task 6:** Create a boxplot for ”Joule calculated” for each ”experiment.”

**Task 7:** Use `stat_summary()` to show the mean and standard error on the boxplot.

## **Exercise 4 - Scatter plot**

**Task 8:** Create a scatter plot (`geom point()`) to show how ”Joule calculated” varies among experiments.

**Task 9:** Assign a unique color to each ”experiment” and add a legend

## **Exercise 5 - Density plot**

**Task 10:** Create a density plot for ”Joule calculated” for each ”experiment”.
