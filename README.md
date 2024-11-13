Steps for Each Chart:
1. Sum of Profit by Day
Visualization Type: Clustered Column Chart
Fields to Add:
Axis: Day (You’ll need a calculated column that extracts the day from the Order Date)
Values: Sum of Profit
Calculated Column for Day:
In "orders," go to the "Modeling" tab > New Column.
Enter this formula:
DAX
Copy code
Day = DAY(orders[Order Date])
Add this "Day" column to the Axis.
2. Sum of Profit by Month
Visualization Type: Clustered Column Chart
Fields to Add:
Axis: Month (Create a calculated column for the month number)
Values: Sum of Profit
Calculated Column for Month:
In the same way, create another column:
DAX
Copy code
Month = MONTH(orders[Order Date])
Add this "Month" column to the Axis.
3. Sum of Profit by Month Name
Visualization Type: Clustered Column Chart
Fields to Add:
Axis: Month Name (A calculated column for the month name)
Values: Sum of Profit
Calculated Column for Month Name:
Use this formula:
DAX
Copy code
Month Name = FORMAT(orders[Order Date], "MMMM")
4. Sum of Profit by Quarter
Visualization Type: Clustered Column Chart
Fields to Add:
Axis: Quarter (Extract quarter from Order Date)
Values: Sum of Profit
Calculated Column for Quarter:
DAX
Copy code
Quarter = QUARTER(orders[Order Date])
5. Sum of Profit by Quarter Name
Similar to the above chart but with Quarter names:
Calculated Column for Quarter Name:
DAX
Copy code
Quarter Name = "Q" & QUARTER(orders[Order Date])
6. Sum of Profit by WeekNum
Visualization Type: Clustered Column Chart
Calculated Column for Week Number:
DAX
Copy code
WeekNum = WEEKNUM(orders[Order Date])
7. Sum of Profit by WeekDay
Calculated Column for Weekday:
DAX
Copy code
WeekDay = WEEKDAY(orders[Order Date])
8. Sum of Profit by Day of Week Name
Calculated Column for Day of Week Name:
DAX
Copy code
Day of weekName = FORMAT(orders[Order Date], "dddd")
9. Sum of Profit by Year
Calculated Column for Year:
DAX
Copy code
Year = YEAR(orders[Order Date])
Let me know if you encounter any specific errors at each step! We’ll address them one by one.






You said:
how to get quater name in ascending order
ChatGPT said:
ChatGPT
To get the quarter names in ascending order in Power BI, we need to ensure that the "Quarter Name" column is sorted by the quarter number rather than alphabetically. Here’s how you can do that:

Ensure You Have a Quarter Number Column:

If you don’t already have one, create a calculated column to get the quarter number:
DAX
Copy code
QuarterNum = QUARTER(orders[Order Date])
Sort the Quarter Name Column by Quarter Number:

Go to the "Data" view in Power BI.
Select the "Quarter Name" column that you created earlier.
In the Modeling tab, select Sort by Column > QuarterNum.
This will force Power BI to display the quarters in the correct order (Q1, Q2, Q3, Q4) instead of alphabetically. Now, when you use the "Quarter Name" column in your visuals, it will appear in ascending order.
