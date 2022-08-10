

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
### SELECT DATE, MONTH AND QUARTER FROM CURRENT DATE

```
SELECT
EXTRACT(YEAR FROM   CURRENT_TIMESTAMP()) AS Year,
EXTRACT(MONTH FROM   CURRENT_TIMESTAMP()) AS Month,
EXTRACT(QUARTER FROM   CURRENT_TIMESTAMP()) AS Quarter
;
```


---

### INSERT MULTIPLE VALUES USING ONE INSERT STATEMENT

```
DROP table student;
CREATE TABLE student ( Row_id int,
StudentName VARCHAR(70), 
 Subject     VARCHAR(20), 
 Marks       INT
);


INSERT INTO student VALUES ('1','Rahul','Maths',90),
('2','Santosh','English',99),
('3','Asha','Maths',96),
('3','Asha','Maths',96),
('4','Easha','Maths',96);

``` 

### SELECT DUPLICATE ROWS


--- 

```
SELECT Row_id, student_name, COUNT(Row_id)
FROM student
GROUP BY Row_id
HAVING COUNT(Row_id) > 1;

```

### DELETE DUPLICATE RECORDS WITH DELETE STATEMENT

```
CREATE TABLE contacts (
    id INT PRIMARY KEY AUTO_INCREMENT,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL, 
    email VARCHAR(255) NOT NULL
);

INSERT INTO contacts (first_name,last_name,email) 
VALUES ('Carine ','Schmitt','carine.schmitt@verizon.net'),
       ('Jean','King','jean.king@me.com'),
       ('Peter','Ferguson','peter.ferguson@google.com'),
       ('Janine ','Labrune','janine.labrune@aol.com'),
       ('Jonas ','Bergulfsen','jonas.bergulfsen@mac.com'),
       ('Janine ','Labrune','janine.labrune@aol.com'),
       ('Susan','Nelson','susan.nelson@comcast.net'),
       ('Zbyszek ','Piestrzeniewicz','zbyszek.piestrzeniewicz@att.net'),
       ('Roland','Keitel','roland.keitel@yahoo.com'),
       ('Julie','Murphy','julie.murphy@yahoo.com'),
       ('Kwai','Lee','kwai.lee@google.com'),
       ('Jean','King','jean.king@me.com'),
       ('Susan','Nelson','susan.nelson@comcast.net'),
       ('Roland','Keitel','roland.keitel@yahoo.com');
       
    SELECT * FROM   contacts ;
       
       DELETE t1 FROM contacts t1
INNER JOIN contacts t2 
WHERE 
    t1.id = t2.id AND 
    t1.email = t2.email;
    
```

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
