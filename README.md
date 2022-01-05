# Mouse Drug Analysis Using Pandas and Matplotlib

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

* The Count of Male and Female was determined
* A pie plot was generated with the determined gender information using both Matplotlib and the built in Pandas pie plot.

#### Final Tumor Volumes

* The final tumor volume of each mouse across all the drug regimes  Capomulin, Ramicane, Infubinol, and Ceftamin was determined based off of the final timepoint for each mouse. 
  * Greatest time point was determined and saved into a variable which was then merged back into the original cleaned mouse dataframe to get the the tumor volume at the final time point.
  * Only pertinent columns remained while all other columns were dropped.
  * The datframe was sorted to find most promising drug regimen.

#### Quartiles, IQR and Potential Outliers

* The most promising treatments were put into a list to perform for loop and later create plot labels
* For Loop was created to calculate quartiles, IQR and any pontential outliers across the most promising drug regimens and was printed to the screen.
* Matplotlib was used to create a box and whisker plot of the final tumor volume of the four treatments and potential outlier shown.

#### Line and Scatter Plots

*  A line plot of tumor volume vs. time point a mouse treated with Capomulin was created.
* A scatter plot of mouse weight versus average tumor volume for the Capomulin was created.

#### Correlation and Regression

* The correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin was calculated and added to the mouse weight and tumor volume scatter plot

#### Observations and Insights

- Three observations and/or insights were added:
  1. In the Capomulin line graph you can clearer see a decrease in the tumor volume over time, it would be interesting to do a scatter plot of tumor volumes for each unique mouse vs time point and test the r-squared.
  2. The scatter plot "tumor volume vs weight" clearly shows a correlation (albeit not perfect), this could lead to further analysis: You could divide each mouse according to various weight classes and see how the drug regimen affected each weigh class. Was each mouse given the same dose regardless of weight? Did weight affect the change in tumor volume? etc.
  3. It would be interesting to pull out the potential outlier and see how this affects the trends/correlation.
