# matplotlib-challenge
Module 05 Matplotlib Challenge

Overview: Analyze the provided data and create visuals for a high level summary of the findings. The goal is to use the skills learned in Module 05 to complete the following (from the Module 05 Challenge page):
    1. Prepare the data
    2. Generate summary statistics
    3. Create bar charts and pie charts
    4. Calculate quartiles, find outliers, and create a box plot
    5. Create a line plot and a scatter plot
    6. Calculate correlation and regression
    7. Submit final analysis
 
 -
------------------------------------------------------------------------------------
1. Prepare the data
    - I counted the number of mice based on ID and used .nunique() to count each unique ID.
    - To find the duplicate values based on Mouse ID and Timepoint, I needed to use a few resources, including a study group. I created a
        variable to hold the duplicates. From there I used the .loc() and .duplicated() functions to pull out and display the duplicates.
        Ref: https://www.w3schools.com/python/pandas/pandas_cleaning_duplicates.asp
        Ref: https://stackoverflow.com/questions/63678603/find-duplicates-in-dataframe-by-compound-criteria?rq=3
        Ref: study group with Melissa Krachmer, Christine Jaregui, Tianyue Li, Gabby Olker
    - In order to clean up the dataframe, I used the .drop_duplicates() function on the original merged dataframe (dropping the duplicates
        found in Mouse ID and Timepoint), and renamed the dataframe as clean_mouse. Five rows of duplicate data were removed.
    - The last task was to reScount the number of mice in the clean_mouse dataframe. I accomplished this by using the .nunique() function
        again to count each unique Mouse ID, and found that the number of Mouse IDs stayed the same.
 
-
------------------------------------------------------------------------------------
2. Generating Summary Statistics
    -Create data frame of summary statistics
        - First I 
    -Include a row for each drug regimen (names should be the index column)
        - I reset the index by using the .set_index() function with Drug Regimen as the index, inplace = True.
    
    -Columns for Mean, Median, Variance, Standard Deviation, SEM of Tumor Value
    
    REQUIREMENTS:
    - the stats are all calculated using groupby
    - new df is created using the summary stats
    
    
-
------------------------------------------------------------------------------------
3. Creating Bar Charts and Pie Charts
    1. Create 2 bar charts, include the total number of rows (Mouse ID/Timepoints) for each drug regimen throughout the study.
        Use DataFrame.plot() to create the first one, and pyplot methods to create the second one.
    2. Create 2 pie charts showing the distribution between female and male mice in the study.
        Use DataFrame.plot() to create the first one, and pyplot methods to create the second one.
    
    REQUIREMENTS:
    - bar charts for total number of time points for all mice tested for each drug regimen
        -1 using Pandas, 1 using pyplot
    - pie charts for distribution of female vs male mice
        -1 using Pandas, 1 using pyplot
        
        

-
------------------------------------------------------------------------------------
4. Calculate Quartiles, Find Outliers, and Create a Box Plot
    1. Calculate the final tumor volumne for each mouse using the four most promising treatments (Capomulin, Ramicane, Infubinol, Ceftamin).
        Find the quartiles and IQR, determine if there's any potential outliers from the four listed treatments.
        -create a grouped DataFrame that shows the last (greatest) time point for each mouse and merge this df with the original cleaned df.
        -create a list that stores the treatment names, and a second empty list to store tumor volume data.
        -loop through each drug in the treatment list, locating the rows in the merged df that correspond with each treatment. Append the 
            final resulting tumor volumes for each drup to the empty list.
        -find outliers by using the upper and lower bounds, print the results.
    2. Use Matplotlib to create a box plot that shows the distribution of the final tumor volume for all mice in each treatment group. 
        Highlight any potential outliers by changing their color/style.
    3. ALL FOUR BOX PLOTS SHOULD BE WITHIN SAME FIGURE
        
    REQUIREMENTS
    - df created by groupby that has last time point for each mouse ID
    - df index reset
    - retrieve max time point for each mouse
    - the four treament groups are put in a list
    - empty list created to fill with tumor vol data
    - use a for loop to display IQR and outliers for each treatment group
    - box plot created showing distrib. of final tumor vol for all mice in each treatment group



-
------------------------------------------------------------------------------------
5. Create a line plot and a scatter plot
    1. Select a single mouse that was treated with Capomulin, and create a line plot of tumor volume vs time point for it.
    2. Create a scatter plot of mouse weight vs avg observed tumor volume for the entire Capomulin treatment regimen.
    
    REQUIREMENTS
    - line plot created that shows tumor vol vs time point for one mouse treated with Capomulin
    - scatter plot created showing avg tumor vol vs mouse wt for Capomulin
    
-
------------------------------------------------------------------------------------
6. Calculate Correlation and Regression
    1. Find the correlation coeff and linear regr model between mouse wt and avg observed tumor volume for the entire Capomulin regimen.
    2. Plot the linear regr model on top of the previous scatter plot.
    
    REQUIREMENTS
    - correlation coeff and linear regr model are calculated for mouse wt and avg tumor vol for Capomulin