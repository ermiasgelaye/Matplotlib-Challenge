# Matplotlib - The Power of Plots

### "Visual storytelling of one kind or another has been around since caveman were drawing on the walls." Frank Darabont
![Laboratory](Images/Laboratory.jpg)

## Background
These respository apply a Python Matplotlib to visualize a real-world Pymaceuticals data. The data is sourced from Pymaceuticals Inc., a burgeoning pharmaceutical company based out of San Diego. Pymaceuticals specializes in anti-cancer pharmaceuticals. In its most recent efforts, it began screening for potential treatments for squamous cell carcinoma (SCC), a commonly occurring form of skin cancer.

This analysis used a complete data from their most recent animal study in two datasets in CSV format. Data set one is [Mouse_metadata.csv](Pymaceuticals/data/Mouse_metadata.csv) wich includes 249 mice identified data with SCC tumor growth were treated through a variety of drug `regimens`, and their `Sex`, `Age_months`	and `Weight (g)`. The other dataset is [Study_results.csv](Pymaceuticals/data/Study_results.csv) file which includes the results of the study in each columns `Mouse I`,`Timepoint`,`Tumor Volume (mm3)`, and `Metastatic Sites`.

The purpose of this study was to compare the performance of Pymaceuticals' drug of interest, Capomulin, versus the other treatment regimens. The analysis also generated all of the table and figures needed for the technical, and top-level summary report of the study. For this analysis both datasets imported, merged,cleaned and the aggregate data diplayed in to Python Pandas dataframes, visualized in Matplotlib, and other libraries used in order to make a stastical analysis. The project is conducted in Jupyter notebook to showcase, and communicate the analysis report the following link is created: [Jupyter Notebook Viewer](https://nbviewer.jupyter.org/github/ermiasgelaye/Matplotlib-Challenge/blob/master/Pymaceuticals/.ipynb_checkpoints/pymaceuticals_starter-checkpoint.ipynb) 

## Observable Trends

* 

* 

## Table of Contents
* [Data cleaning](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [summary statistics](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [District Summary](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [School Summary](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Top Performing Schools (By % Overall Passing)](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Bottom Performing Schools (By % Overall Passing)](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Math Scores by Grade](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Reading Scores by Grade](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Scores by School Spending](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Scores by School Size](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)
* [Scores by School Type](https://nbviewer.jupyter.org/github/ermiasgelaye/pandas-challenge/blob/master/PyCitySchools/.ipynb_checkpoints/PyCitySchools_starter-checkpoint.ipynb)


## Solutions

## Data Cleaning
* The data was loaded, read, combined, duplicate removed, and the head (5 rows on the top) of cleaned data out put looks as follows

<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th>Mouse ID</th>
      <th>Drug Regimen</th>
      <th>Sex</th>
      <th>Age_months</th>
      <th>Weight (g)</th>
      <th>Timepoint</th>
      <th>Tumor Volume (mm3)</th>
      <th>Metastatic Sites</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>k403</td>
      <td>Ramicane</td>
      <td>Male</td>
      <td>21</td>
      <td>16</td>
      <td>0</td>
      <td>45.000000</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>k403</td>
      <td>Ramicane</td>
      <td>Male</td>
      <td>21</td>
      <td>16</td>
      <td>5</td>
      <td>38.825898</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>k403</td>
      <td>Ramicane</td>
      <td>Male</td>
      <td>21</td>
      <td>16</td>
      <td>10</td>
      <td>35.014271</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>k403</td>
      <td>Ramicane</td>
      <td>Male</td>
      <td>21</td>
      <td>16</td>
      <td>15</td>
      <td>34.223992</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>k403</td>
      <td>Ramicane</td>
      <td>Male</td>
      <td>21</td>
      <td>16</td>
      <td>20</td>
      <td>32.997729</td>
      <td>1</td>
    </tr>
  </tbody>
</table>

## Summary statistics

* A summary statistics table was generated by using two techniques one is by creating multiple series, and putting them all together at the end, and the other method produces everything in a single groupby function. The summery statistic table consis the mean, median, variance, standard deviation, and SEM of the tumor volume for each drug regimen. The summery stastics tables looks as follws:

<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th>Mean</th>
      <th>Median</th>
      <th>Variance</th>
      <th>Standard Deviation</th>
      <th>SEM</th>
    </tr>
    <tr>
      <th>Drug Regimen</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Capomulin</th>
      <td>40.675741</td>
      <td>41.557809</td>
      <td>24.947764</td>
      <td>4.994774</td>
      <td>0.329346</td>
    </tr>
    <tr>
      <th>Ceftamin</th>
      <td>52.591172</td>
      <td>51.776157</td>
      <td>39.290177</td>
      <td>6.268188</td>
      <td>0.469821</td>
    </tr>
    <tr>
      <th>Infubinol</th>
      <td>52.884795</td>
      <td>51.820584</td>
      <td>43.128684</td>
      <td>6.567243</td>
      <td>0.492236</td>
    </tr>
    <tr>
      <th>Ketapril</th>
      <td>55.235638</td>
      <td>53.698743</td>
      <td>68.553577</td>
      <td>8.279709</td>
      <td>0.603860</td>
    </tr>
    <tr>
      <th>Naftisol</th>
      <td>54.331565</td>
      <td>52.509285</td>
      <td>66.173479</td>
      <td>8.134708</td>
      <td>0.596466</td>
    </tr>
    <tr>
      <th>Placebo</th>
      <td>54.033581</td>
      <td>52.288934</td>
      <td>61.168083</td>
      <td>7.821003</td>
      <td>0.581331</td>
    </tr>
    <tr>
      <th>Propriva</th>
      <td>52.320930</td>
      <td>50.446266</td>
      <td>43.852013</td>
      <td>6.622085</td>
      <td>0.544332</td>
    </tr>
    <tr>
      <th>Ramicane</th>
      <td>40.216745</td>
      <td>40.673236</td>
      <td>23.486704</td>
      <td>4.846308</td>
      <td>0.320955</td>
    </tr>
    <tr>
      <th>Stelasyn</th>
      <td>54.233149</td>
      <td>52.431737</td>
      <td>59.450562</td>
      <td>7.710419</td>
      <td>0.573111</td>
    </tr>
    <tr>
      <th>Zoniferol</th>
      <td>53.236507</td>
      <td>51.818479</td>
      <td>48.533355</td>
      <td>6.966589</td>
      <td>0.516398</td>
    </tr>
  </tbody>
</table>


* Generate a bar plot using both Pandas's `DataFrame.plot()` and Matplotlib's `pyplot` that shows  the number of total mice for each treatment regimen throughout the course of the study.

  * **NOTE:** These plots should look identical.

* Generate a pie plot using both Pandas's `DataFrame.plot()` and Matplotlib's `pyplot` that shows the distribution of female or male mice in the study.

  * **NOTE:** These plots should look identical.

* Calculate the final tumor volume of each mouse across four of the most promising treatment regimens: Capomulin, Ramicane, Infubinol, and Ceftamin. Calculate the quartiles and IQR and quantitatively determine if there are any potential outliers across all four treatment regimens.

* Using Matplotlib, generate a box and whisker plot of the final tumor volume for all four treatment regimens and highlight any potential outliers in the plot by changing their color and style.

  **Hint**: All four box plots should be within the same figure. Use this [Matplotlib documentation page](https://matplotlib.org/gallery/pyplots/boxplot_demo_pyplot.html#sphx-glr-gallery-pyplots-boxplot-demo-pyplot-py) for help with changing the style of the outliers.

* Select a mouse that was treated with Capomulin and generate a line plot of time point versus tumor volume for that mouse.

* Generate a scatter plot of mouse weight versus average tumor volume for the Capomulin treatment regimen.

* Calculate the correlation coefficient and linear regression model between mouse weight and average tumor volume for the Capomulin treatment. Plot the linear regression model on top of the previous scatter plot.

* Look across all previously generated figures and tables and write at least three observations or inferences that can be made from the data. Include these observations at the top of notebook.

Here are some final considerations:

* You must use proper labeling of your plots, to include properties such as: plot titles, axis labels, legend labels, _x_-axis and _y_-axis limits, etc.

* See the [starter workbook](Pymaceuticals/pymaceuticals_starter.ipynb) for help on what modules to import and expected format of the notebook.

## Hints and Considerations

* Be warned: These are very challenging tasks. Be patient with yourself as you trudge through these problems. They will take time and there is no shame in fumbling along the way. Data visualization is equal parts exploration, equal parts resolution.

* You have been provided a starter notebook. Use the code comments as a reminder of steps to follow as you complete the assignment.

* Don't get bogged down in small details. Always focus on the big picture. If you can't figure out how to get a label to show up correctly, come back to it. Focus on getting the core skeleton of your notebook complete. You can always revisit old problems.

* While you are trying to complete this assignment, feel encouraged to constantly refer to Stack Overflow and the Pandas documentation. These are needed tools in every data analyst's tool belt.

* Remember, there are many ways to approach a data problem. The key is to break up your task into micro tasks. Try answering questions like:

  * How does my DataFrame need to be structured for me to have the right _x_-axis and _y_-axis?

  * How do I build a basic scatter plot?

  * How do I add a label to that scatter plot?

  * Where would the labels for that scatter plot come from?

  Again, don't let the magnitude of a programming task scare you off. Ultimately, every programming problem boils down to a handful of bite-sized tasks.

* Get help when you need it! There is never any shame in asking. But, as always, ask a _specific_ question. You'll never get a great answer to "I'm lost."

### Copyright

Trilogy Education Services © 2020. All Rights Reserved.
