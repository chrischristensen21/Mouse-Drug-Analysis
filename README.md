# Mouse Drug Analysis Using Matplotlib

## Overview

The goal of this project was to take two datasets and analyze it using python pandas  and matplotlib. The datasets were from a study to compare the performance of a drug (Capomulin) to other drug regimens in their ability to treat squamous cell carcinoma (SCC) tumor growth in mice. In the study, 249 mice observed with SCC tumor growth were treated with Capomulin along with other drugs over the course of 45 days and the results were recorded.

## Outline

#### Setup and Data Read

* The basic dependencies were read in:
  * pandas, matplotlib, scipy stats, and numpy
* Two CSV's containing the data were read in
  * Mouse data and Study results
* The mouse data and study data were combined into a single pandas dataframe for easier analysis.

#### Data Cleanup

* First the number of unique mice was verified by using a .unique()
* Any duplicated records were verified and viewed using a duplicated function and then dropped using a drop duplicates function
* A quick summary of the information was printed to the screen to verify that the duplicated information was removed.
* The cleaned data was then used in all other steps

#### Summary Statistics

* A summary statistics table was generated that included the mean, median, variance, standard deviation, SEM of the tumor volume for each of the drugs.
  * a groupby on tumor volume was performed for each statistic mentioned above, saved into a variable and a pandas dataframe was created with the information.
* A table with the same information was created using a different method (aggregate method).

#### Number of Mice per Drug Regimen

* The number of mice used for each drug regimen was determined.
* A bar plot was generated with that information using both Matplotlib and the built in Pandas plot.

#### Distribution of Male and Female Mice

* Generate a pie plot using both Pandas's `DataFrame.plot()` and Matplotlib's `pyplot` that shows the distribution of female or male mice in the study.

  * **NOTE:** These plots should look identical.

* Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Calculate the quartiles and IQR and quantitatively determine if there are any potential outliers across all four treatment regimens.

* Using Matplotlib, generate a box and whisker plot of the final tumor volume for all four treatment regimens and highlight any potential outliers in the plot by changing their color and style.

  **Hint**: All four box plots should be within the same figure. Use this [Matplotlib documentation page](https://matplotlib.org/gallery/pyplots/boxplot_demo_pyplot.html#sphx-glr-gallery-pyplots-boxplot-demo-pyplot-py) for help with changing the style of the outliers.

* Select a mouse that was treated with Capomulin and generate a line plot of tumor volume vs. time point for that mouse.

* Generate a scatter plot of mouse weight versus average tumor volume for the Capomulin treatment regimen.

* Calculate the correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin treatment. Plot the linear regression model on top of the previous scatter plot.

* Look across all previously generated figures and tables and write at least three observations or inferences that can be made from the data. Include these observations at the top of notebook.

Here are some final considerations:

* You must use proper labeling of your plots, to include properties such as: plot titles, axis labels, legend labels, _x_-axis and _y_-axis limits, etc.

* See the [starter workbook](Pymaceuticals/pymaceuticals_starter.ipynb) for help on what modules to import and expected format of the notebook.

