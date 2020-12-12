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
of 393 cannot  be considered to be a representative sample of the population.  Keeping in mind the likelihood of bias because of sample size, I think
this dataset will be an interesting one to work with.

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
A count plot is a histogram across a categorical, instead of quantitative, variable. 
The plot clearly shows a high correlation between mother's education and the child's G3 school grade.  The purple bar represents mothers with 3rd level education and this
bar is most highly correlated with children in the 14 - 20 grade scores.

I used the crosstab and countplot functions to perform the same analysis of the father's grade and child performance in school.
The plot shows a medium correlation between father's education and the child's G3 school grade.  The purple bar represents fathers with 3rd level education and this
bar is correlated with children in the 14 - 20 grade score.

The seaborn barplot was useful to demonstrate the correlation between the number of absent days and the G3 grade the students scored.  The barchart
shows clearly that students who missed 20+ days of school were mainly represented in the lower scores of G3 and students with 5 or fewer absence days are highly represented in the 14+ grade point scores. 

This data trying to show a correlation between students ambitions to attend 3rd Level and their G3 maths grades is not successful.
Because this is a secondary school most students attending would intend to attend third level.  It seems that in the Portugese educational system it is normal to leave
at 15 if you are not planning 3rd level.  Therefore it is safe to assume that those who go to secondary want to go to third level even if their grades do not make that a likely outcome.
