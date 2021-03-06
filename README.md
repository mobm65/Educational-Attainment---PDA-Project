SOURCES

P. Cortez and A. Silva. Using Data Mining to Predict Secondary School Student Performance. In A. Brito and J. Teixeira Eds., Proceedings of 5th FUture BUsiness TEChnology Conference (FUBUTEC 2008) pp. 5-12, Porto, Portugal, April, 2008, EUROSIS, ISBN 978-9077381-39-7. 
http://www3.dsi.uminho.pt/pcortez/student.pdf
 These two sources were very useful.  I found my dataset in the first source and used the second to find out how the Cortez & Silva
study related to predicting success in education by examining variables in the students' lives.

http://uis.unesco.org/country/PT
    Provides data of population of Portugal broken down by age.
    
https://www.oecd-ilibrary.org/docserver/9789264117020-4-en.pdf
    Provided me with information about Portugese school system.
   
https://www.shanelynn.ie/using-pandas-dataframe-creating-editing-viewing-data-in-python/
    This source helped me to tidy up the dataset into the columns and rows I wanted to keep.

https://thispointer.com/python-pandas-how-to-display-full-dataframe-i-e-print-all-rows-columns-without-truncation/
    This source helped me to find a way to display all the data in the dataset.
    
https://www.earthdatascience.org/courses/intro-to-earth-data-science/scientific-data-structures-python/pandas-dataframes/indexing-filtering-data-pandas-dataframes/
    This source was very useful with appropriate functions to interpret the data.

https://seaborn.pydata.org/
    This source helped me to use correct syntax to plot my data.  It was also excellent to help me choose which plots to use.

My plan is to investigate correlations between achievement; parental education, attendance and plans to attend 3rd level.
I predict there is a link between the variables; school attendance, mother's education, father's education, plans to attend 
higher education and achievement.  I will use the dataset produced by Cortez and Silva which includes these variables among others.
First I will import the dataset and eliminate the other variables until I have the ones I want to investigate. 

Cortez and Silva studied a cohort of students in two Portugese secondary schools. The attendees of Portugese secondary schools are normally
within the 15 years to 17 years age group.  Given the population of people in Portugal between 15 and 19 is approximately 520,000, a sample size
of 393 cannot  be considered to be a representative sample of the population.  Keeping in mind the likelihood of bias because of sample size, I still think
this dataset will be an interesting one to work with.

Cortez and Silva studied students on two subjects, Portugese and Maths.  I selected the csv for Maths because I thought it would be more relatable
for me to choose a universal school subject.

Cortez and Silva were mining data to predict test scores.  They examined 33 variables, I will examine only four.  They were trying to find causal
predictive relationships between their variables and test scores.  In Portugal students are graded on a 0-20 system in exams where 16-20 is equivalent to
an A, 14-15 is equivalent to a B, 12-13 is equivalent to a C, 10-11 is equivalent to a D, 0-9 is an E(fail).

Parent's education is scored on a 0-4 scale where; 0 = no education, 1 = primary to 4th grade (9 years old), 2 = primary to 9th grade (14 years old), 
3 = secondary (17 years old) and 4 = third level.

Absences are measured in number of days the student was not present.

Intention to go to third level is a binary choice, either yes or no.

My first step was to import the dataset.  I had to download it to my local machine and unzip it before I could upload it to my Jupyter notebook. 
I then stripped out the columns I didn't want as part of my dataframe using the .drop function.  When I had the number of columns I wanted I used .set_option
to display all the rows and columns. My dataframe is called dfgrade. I then used .info, .describe, .iloc, .loc to examine the data. 

Having later crosstabulated all the data I found there is a large number of students who got 0 as their final grade (G3).  
I took this group out of the cohort because they are skewing the statistics.  I assume for one reason or another they
did not take the final exam.  I used the .drop function to do this.

I used the pandas crosstab function to produce a table showing the correlation between the G3 (final year grade) and the mother's education level.
I then used the seaborn crossplot function to plot the data above to examine the relationship between mother's education level and child performance in school. 
The plot clearly shows a high correlation between mother's education and the child's G3 school grade.  The purple bar represents mothers with 3rd level education and this
bar is most highly correlated with children in the 14 - 20 grade scores.

I used the crosstab and countplot functions to perform the same analysis of the father's grade and child performance in school.
The plot shows a medium correlation between father's education and the child's G3 school grade.  The purple bar represents fathers with 3rd level education and this
bar is correlated with children in the 14 - 20 grade score.

The seaborn barplot was useful to demonstrate the correlation between the number of absent days and the G3 grade the students scored.  The barchart
shows clearly that students who missed 20+ days of school were mainly represented in the lower scores of G3 and students with 5 or fewer absence days are highly represented in the 14+ grade point scores. 

This data trying to show a correlation between students ambitions to attend 3rd Level and their G3 maths grades is not successful.
Because this is a secondary school most students attending would intend to study at third level.  It seems that in the Portugese educational system it is normal to leave
at 14/15 if you are not planning 3rd level.  Therefore it is safe to assume that those who go to secondary want to go to third level even if their grades do not make that a likely outcome.

I then created two further plots for each variable.  The sources which helped me construct my plots are listed above.  I plotted a normal distribution and a histogram for each
variable; Mothers' education, Fathers' education, absences and G3, the final score each of the 359 recieved in maths in the year of the study.  

Having run the complete file I realise that I have used the same code for the real dataset and the simulated dataset to perform some statistical analyses so my results are the same.  I will try to modify the code to have the simulated data resemble the other not match it.

EXTRA SOURCES

https://numpy.org/doc/stable/reference/generated/numpy.histogram.html Useful to check correct syntax.

https://datatofish.com/list-to-dataframe/ I realised I had to change lists to dataframes so I could compare/contrast.

https://stackoverflow.com/users/959876/moldovean A very handy guide to loc and iloc to isolate a column.

https://scipy-lectures.org/packages/scikit-learn/index.html I did a lot of research on machine learning when trying to find some way to make the simulated data similar to the real world data, this site was very informative.

https://www.tutorialspoint.com/numpy/numpy_statistical_functions.html This site helped me adapt the function I got from the runaway horse source below to my situation.

https://github.com/runawayhorse001/statspy/blob/master/statspy/basics.py This was the most useful source I found and I have been down many disappointing alleyways! It gave me a defined function that I could apply to my real world data to recreate datasets which had the same number of samples, the same mean and standard deviation. A simulated dataset which shares these in common with a real world dataset is representative of the real world dataset.

https://www.youtube.com/watch?v=xlD8FIM5biA from a website called OSPY.
This site helped me to save my images correctly and import them into my notebook.

To replicate similar simulated data to the original dataset I knew I had to find some way of including mean and standard deviation.  I eventually found a rnorm function by Wenqiang Feng on the above url.  This allowed me to use the parameters of my original datasets to create four simulated datasets for mother's education, father's education, absences and final grade score.  The datasets for mother's education, father's education and final grade score were reasonably similar to the real world data.  Absences was very difficult to recreate, I don't think I managed to do it properly.  Perhaps because the possible number of days absent was between 1 and 75 the standard deviation was very high.  When I used rnorm many of the answers were negative, as it is not possible to be minus days absent from school I tried the following on the data.  I squared every element of the list and then got its square root, this got rid of negative numbers.  When I plotted this data on a histogram it clearly doesn't replicate the original data and I am unable to figure out where to go next.

When the four simulated datasets were ready I created a histogram for each using Matplotlib.  I then used Image from IPython to copy the images of the real datasets into a folder called img and then displayed them next to each simulated dataset for comparison.  

Results

1. I sourced a suitable dataset of student attributes across a variety of variables.
2. I imported the dataset into this jupyter notebook and isolated 359 samples across
    seven variables, I eventually narrowed this down to four variables.
3. I analysed the data using crosstabulation and various plots.  I finally made histogram plots
    of each of four variables.
4. The final task was to create simulated data which shared characteristics with the real world
    data.  I used the function rnorm so I could base the simulated data on the real data.
5. I made histogram plots to illustrate the simulated datasets.  I then used Image to show the real
    world plots beside the simulated data plots.
  

Conclusion

It is clear that the simulated data doesn't resemble the real world data as much as I would expect, 
especially the Absences dataset.  I am not entirely happy with the outcome but I have certainly 
learned a lot more, particularly in the area of research.
