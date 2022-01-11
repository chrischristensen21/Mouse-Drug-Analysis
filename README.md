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
![Set Up](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Set%20Up%20.png)

#### Data Cleanup

* First the number of unique mice was verified by using a .unique()
![Unique Mice](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Unique%20Mice.png)
* Any duplicated records were verified and viewed using a duplicated function and then dropped using a drop duplicates function
![Duplicated Mice](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Duplicated%20Mice%20Records.png)
![Duplicated Mice](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Drop%20Duplicates.png)
* A quick summary of the information was printed to the screen to verify that the duplicated information was removed.
![Cleaned Summary](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Cleaned%20Data%20Summary.png)
* The cleaned data was then used in all other steps

#### Summary Statistics

* A summary statistics table was generated that included the mean, median, variance, standard deviation, SEM of the tumor volume for each of the drugs.
  * a groupby on tumor volume was performed for each statistic mentioned above, saved into a variable and a pandas dataframe was created with the information.
![Summary Statistics](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Summary%20Statistics.png) 
* A table with the same information was created using a different method (aggregate method).
![Summary Statistics Aggregate](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Aggregate%20Method%20Summary%20Statistics.png)

#### Number of Mice per Drug Regimen

* The number of mice used for each drug regimen was determined.
* A bar plot was generated with that information using both Matplotlib and the built in Pandas plot.
![# of Mice per Drug Pyplot](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/%23%20Mice%20Per%20Drug%20Pyplot%20Bar%20Chart.png)
![# of Mice per Drug Pandas](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/%23%20Mice%20Per%20Drug%20Pandas%20Bar%20Chart.png)

#### Distribution of Male and Female Mice

* The Count of Male and Female was determined
* A pie plot was generated with the determined gender information using both Matplotlib and the built in Pandas pie plot.
![Pyplot Pie Chart](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Distribution%20of%20Male%20and%20Female%20Mice%20Pyplot.png)
![Pandas Pie Chart](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Distribution%20of%20Male%20and%20Female%20Mice%20Pandas.png)

#### Final Tumor Volumes

* The final tumor volume of each mouse across all the drug regimes  Capomulin, Ramicane, Infubinol, and Ceftamin was determined based off of the final timepoint for each mouse. 
  * Greatest time point was determined and saved into a variable which was then merged back into the original cleaned mouse dataframe to get the the tumor volume at the final time point.
  * Only pertinent columns remained while all other columns were dropped.
  * The datframe was sorted to find most promising drug regimen.
![Final Tumor Volume Code](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Final%20Tumor%20Volumes%20per%20Drug%20Regimen%20Code.png)

#### Quartiles, IQR and Potential Outliers

* The most promising treatments were put into a list to perform for loop and later create plot labels
* For Loop was created to calculate quartiles, IQR and any pontential outliers across the most promising drug regimens and was printed to the screen.
* Matplotlib was used to create a box and whisker plot of the final tumor volume of the four treatments and potential outlier shown.
![Quartiles, IQR and Potential Outliers Code](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Quartiles%2C%20IQR%20and%20Potential%20Outliers%20Code.png)
![Quartiles, IQR and Potential Outliers Output](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Quartiles%2C%20IQR%20and%20Potential%20Outliers%20Output.png)

#### Line and Scatter Plots

*  A line plot of tumor volume vs. time point a mouse treated with Capomulin was created.
![Line Plot](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Line%20Plot.png)
* A scatter plot of mouse weight versus average tumor volume for the Capomulin was created.
![Scatter Plot](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Scatterplot.png)

#### Correlation and Regression

* The correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin was calculated and added to the mouse weight and tumor volume scatter plot
![Scatter Plot](https://github.com/chrischristensen21/Mouse-Drug-Analysis-Using-Pandas-and-Matplotlib/blob/main/Screen%20Shots/Correlation%20and%20Regression.png)

#### Observations and Insights

- Three observations and/or insights were added:
  1. In the Capomulin line graph you can clearer see a decrease in the tumor volume over time, it would be interesting to do a scatter plot of tumor volumes for each unique mouse vs time point and test the r-squared.
  2. The scatter plot "tumor volume vs weight" clearly shows a correlation (albeit not perfect), this could lead to further analysis: You could divide each mouse according to various weight classes and see how the drug regimen affected each weigh class. Was each mouse given the same dose regardless of weight? Did weight affect the change in tumor volume? etc.
  3. It would be interesting to pull out the potential outlier and see how this affects the trends/correlation.
