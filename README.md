# Udacity Data Science Nano Degree Blog

This project takes a look at the past three Stack Over Flow Develper Surveys from 2017, 2018 and 2019  to look at a couple of different items to see how they compare from year to year.

# Motivation

To take a peek and to try to gain some insight from the Stack Overflow surveys to get a view of the status of the industry as seen  by the developers that chose to respond



## Data
 
 The datasets are too large to be stored on GitHub so the data could be found here
 
 [2019 Survey] (https://drive.google.com/open?id=1QOmVDpd8hcVYqqUXDXf68UMDWQZP0wQV)
 
 [2018 Survey] (https://drive.google.com/uc?export=download&id=1_9On2-nsBQIw3JiY43sWbrF8EjrqrR4U)
 
 [2017 Survey] (https://drive.google.com/uc?export=download&id=0B6ZlG_Eygdj-c1kzcmUxN05VUXM)

##   The code can be found at 
`git clone https://github.com/beachkrp/Blog.git`

## Files in the Repository

A Jupyter Notebook with the code for this project
This README file

## Examining the Distribution of respondants by country.

This is a straight forward examination.  This was just a matter of performing a .value_counts() method on the "Country" column. 

It is possible to use subplots to plot these three graphs together, however, this caused the x_ticks to run into the 
subplot below.  It actually became a better looking presentatin to plot three bar charts separately

## Looking at the languages used.

 This is a bit more complicated as the languages used were jumbled together in a single string delimited by semicolons.  While this is simple enough to separate out by using the split method from the Pandas.str library,  there is the matter of embedded spaces that caused some languages to be duplicated because of stray whitespace.  

 Fortunately, the Pandas.str library also has methods for stripping whitespace and for replacing regular expressions.  These methods are combined to be able to extract the different languages used and then this column is tranformed into a language matrix which is used for visualization. 


## Salaries comparison

Comparing the salaries from year to year are not straight forward for a number of reason.   First of all, the "Salary"  column for the 2019 survey does not exist and there is a column for Total Compensation, and it is not clear how this relates to the Salary in the previous years' survey.

Also, there is an issue with different countries using different currencies, so without a conversion to a common currency it is not possible to make a valid comparison because salaries of developers between countries. Therefore only a few select countries are examined and visualized.

Another issue is that Salary column for the 2018 is a string value and not a number so it has to be wrangled to be a float to be able to be used for a box plot, which was the preferred format.

Because the surveys from the various years were of different lengths, there were a number of nan values which caused problems with the plotting of box plots.  Thus each column had to have the null values dropped before they could  be plotted

The missing values were dropped and not imputed because in the drawing of a box plot, the quartiles are key in a visual interpreatation of the data.  While it may be tempting to impute the mean or the median value into the missing values, to do so would "shrink the box" and greatly distort the visualization


## Blog 

 The actual blog can be found on [Medium](https://medium.com/@kevinpearson_20937/a-quick-peek-at-stack-overflow-surveys-from-2017-to-2019-4a330b32a1e2)
 
 
 # Acknowledgemenst
 
 Python Data Science and Machine Learning Bootcamp, Pierian Data
 
 https://stackoverflow.com/questions/22483588/how-can-i-plot-separate-pandas-dataframes-as-subplots
 
 https://github.com/matplotlib/matplotlib/issues/8105/
 
 https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.subplots.html
 
 