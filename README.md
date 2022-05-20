# Fall 2022 Data Science Intern Challenge 

Please complete the following questions, and provide your thought process/work. You can attach your work in a text file, link, etc. on the application page. Please ensure answers are easily visible for reviewers!


Question 1: Given some sample data, write a program to answer the following: click here to access the required data set

On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis. 

Think about what could be going wrong with our calculation. Think about a better way to evaluate this data.
What metric would you report for this dataset?
What is its value?

Outliers have the ability to cause issues in our statistical analysis, as larger outliers can increase the value of our mean. Upon analysis of the data, we discovered that the largest outlier was $704,000. 
Determining the median, which is $284, would be a more effective way of determining the central tendency of the data. Also, observing the range of data between the lower and upper quartile ($163 and $390, respectively) tells us that though the average is $3145.13 is inaccurate if we are observing central tendencies of our data.
