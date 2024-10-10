# GreenLab-LAB4-2024: Visualization with R

This repository contains a set of exercises for the GreenLab Lab 4 of 2024 (11th October 2024). The exercises are designed to help students get familiar with the ggplot2 package, some of its different plot types and how customizable and flexible they are.

You can consult `ggplot2_cheat_sheet.pdf` as a reference point.

## **Exercise 0 - Before Plotting**

In a new R Markdown document, install and load ggplot2. Load `Run_Table_TPCH.csv` as a data frame.

For the following exercises, we will call each combination of library and dataframe_size an **"experiment"**.

## **Exercise 1 - Box plot**

**Task 1:** Create a boxplot to visualize the distribution of `energy_usage` for each **"experiment"**. Use `facet_wrap()` to adequately separate the experiments by library or dataframe size.

**Task 2**: Label the x-axis as ”Dataframe Size” and the y-axis as ”Energy Usage”

## **Exercise 2 - Violin plot**

**Task 3:** Create a violin plot of `energy_usage` for each **"experiment"**.

**Task 4:** Overlay a boxplot inside the violin plot to show statistical summary. Adjust its opacity if necessary for better visibility.

**Task 5:** add `geom_jitter()` to overlay individual datapoints. Adjust the size of the points if necessary for better visibility.

## **Exercise 3 - Boxplot + mean and standard error**

**Task 6:** Create a boxplot of `energy_usage` for each **"experiment"**. If you created a ggplot object containing your plot from Exercise 1, you can reuse it.

**Task 7:** Use `stat_summary()` to show the mean and standard error on the boxplot.

## **Exercise 4 - Scatter plot**

**Task 8:** Create a scatter plot (`geom point()`) to show how `energy_usage` varies over `trial`.

**Task 9:** Assign a unique color to each **”experiment”** and add a legend

## **Exercise 5 - Linear Regression trend line in Scatter Plot**

**Task 10:** Using faceting, create a grid with 4 scatter plots (one per **"experiment"**) showing how `energy_usage` correlates to `execution_time`, Including trend lines.

**Task 11:** If you plot `memory_usage` or `cpu_usage` as a function of `execution_time`, can you conclude whether memory or CPU are correlated to energy in any of the **"experiments"**? (Hint: looking at task 10, is energy always correlated to time in the same direction on all experiments?)

## **Exercise 6 - Density plot**

**Task 12:** Create a density plot for `energy_usage` for each **"experiment"**, separate them using `facet_grid()`.

## **Exercise 7 - LaTeX Table**

LaTeX is a typesetting system commonly used in scientific publishing.

**Task 13:** Use dplyr functions to calculate the average `cpu_usage`, `memory_usage` and `energy_usage` for each **"experiment"**.

**Task 14:** Using the xtable package, format the summary table as LaTeX. You can copy the output for rendering in engines such as Overleaf or LaTeXiT.