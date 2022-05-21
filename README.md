# Fall 2022 Data Science Intern Challenge 

Fall 2022 Data Science Intern Challenge 

Please complete the following questions, and provide your thought process/work. You can attach your work in a text file, link, etc. on the application page. Please ensure answers are easily visible for reviewers!


Question 1: Given some sample data, write a program to answer the following: click here to access the required data set

On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis. 

Think about what could be going wrong with our calculation. Think about a better way to evaluate this data.
What metric would you report for this dataset?
What is its value?

Outliers have the ability to cause issues in our statistical analysis, as larger outliers can increase the value of our mean. Upon analysis of the data, we discovered that the largest outlier was $704,000. 
Determining the median, which is $284, would be a more effective way of determining the central tendency of the data. Also, observing the range of data between the lower and upper quartile ($163 and $390, respectively) tells us that though the average is $3145.13 is inaccurate if we are observing central tendencies of our data.

Python code from my analysis can be found at: https://www.github.com/ryanneilscott/Shopify_Intern_Project


Question 2: For this question you’ll need to use SQL. Follow this link to access the data set required for the challenge. Please use queries to answer the following questions. Paste your queries along with your final numerical answers below.

How many orders were shipped by Speedy Express in total?
54 orders were shipped by Speedy Express in total.

SELECT COUNT(DISTINCT OrderID)
FROM [Orders]
WHERE ShipperID = 1


What is the last name of the employee with the most orders?
The last name is Peacock with a total of 40 orders

SELECT e.LastName, MAX(o.Num_of_Orders)
FROM [Employees] AS e
JOIN (
      SELECT EmployeeID, Count(OrderID) AS Num_of_Orders
      FROM [Orders]
      Group By EmployeeID) AS o
On e.EmployeeID = o.EmployeeID



What product was ordered the most by customers in Germany?
The product is Boston Crab Meat, with a quantity shipped of 160

SELECT od.ProductID, p.ProductName, SUM(od.Quantity) AS Quantity
FROM [OrderDetails] as od
JOIN [Products] as p
On od.ProductID = p.ProductID
WHERE od.OrderID IN
            (SELECT o.OrderID
             FROM [Orders] as o
             JOIN [Customers] as c
             On o.CustomerID = c.CustomerID
             WHERE c.Country = "Germany")
GROUP BY od.ProductID
ORDER BY Quantity DESC






