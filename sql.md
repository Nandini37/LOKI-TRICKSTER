

## ORDER SQL QUERY BY last three characters OF NAME

Query the Name of any student in STUDENTS who scored higher than  Marks. 
Order your output by the last three characters of each name. 
If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

```
SELECT NAME FROM STUDENTS 
WHERE MARKS > 75
ORDER BY RIGHT(NAME, 3), ID ASC;
```

### SELECT LONGEST CITY NAME

```
select city, length(city) from station
order by length(city) desc
limit 1;

```

--- 
# WINDOW FUNCTIONS
## AVERAGE MARKS BY SUBJECTS

```
SELECT StudentName, Subject, Marks,
 AVG (Marks) OVER( PARTITION BY Subject ORDER BY Subject) AS Avg_Marks
 FROM ExamResult;
 ```
 
 ## SQL RANK FUNCTION
 
 ### ROW_Number() SQL RANK function
 
 - [x] get a unique sequential number for each row in the specified data
 
 ```
 SELECT Studentname, 
       Subject, 
       Marks, 
       ROW_NUMBER() OVER(ORDER BY Marks) RowNumber
FROM ExamResult;

```

### 
