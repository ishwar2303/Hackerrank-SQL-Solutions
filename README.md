# Hackerrank-SQL-Solutions
# EASY

## Revising the Select Query I
```sql
SELECT * FROM CITY WHERE POPULATION > 100000 AND COUNTRYCODE = 'USA';
```

## Revising the Select Query II
```sql
SELECT NAME FROM CITY WHERE POPULATION > 120000 AND COUNTRYCODE = 'USA';
```

## Select All
```sql
SELECT * FROM CITY;
```

## Select By ID
```sql
SELECT * FROM CITY WHERE ID = 1661;
```

## Japanese Cities' Attributes
```sql
SELECT * FROM CITY WHERE COUNTRYCODE = 'JPN';
```

## Japanese Cities' Names
```sql
SELECT NAME FROM CITY WHERE COUNTRYCODE = 'JPN';
```

## Weather Observation Station 1
```sql
SELECT CITY, STATE FROM STATION;
```

## Weather Observation Station 3
```sql
SELECT DISTINCT CITY FROM STATION WHERE ID%2 = 0;
```

## Weather Observation Station 4
### Function : COUNT()
```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) AS  Difference  FROM STATION;
```

## Weather Observation Station 5
```sql
SELECT CITY, LENGTH(CITY) AS CityLength FROM STATION ORDER BY CityLength ASC, CITY ASC LIMIT 1;
SELECT CITY, LENGTH(CITY) AS CityLength FROM STATION ORDER BY CityLength DESC, CITY ASC LIMIT 1;
```


## Weather Observation Station 6
```sql
SELECT DISTINCT CITY
FROM STATION WHERE 
SUBSTR(CITY, 1, 1) = 'a' 
OR SUBSTR(CITY, 1, 1) = 'e' 
OR SUBSTR(CITY, 1, 1) = 'i' 
OR SUBSTR(CITY, 1, 1) = 'o' 
OR SUBSTR(CITY, 1, 1) = 'u';
```

## Weather Observation Station 6, Alternate way
```sql
SELECT CITY FROM STATION 
WHERE 
CITY LIKE 'A%' 
OR 
CITY LIKE 'E%'
OR 
CITY LIKE 'I%'
OR 
CITY LIKE 'O%'
OR 
CITY LIKE 'U%';
```

## Weather Observation Station 7
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE 
CITY LIKE '%A' 
OR 
CITY LIKE '%E'
OR 
CITY LIKE '%I'
OR 
CITY LIKE '%O'
OR 
CITY LIKE '%U';
```

## Weather Observation Station 8
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE 
(
CITY LIKE 'A%' 
OR 
CITY LIKE 'E%'
OR 
CITY LIKE 'I%'
OR 
CITY LIKE 'O%'
OR 
CITY LIKE 'U%'
)
AND
(
CITY LIKE '%A' 
OR 
CITY LIKE '%E'
OR 
CITY LIKE '%I'
OR 
CITY LIKE '%O'
OR 
CITY LIKE '%U'
);
```

## Weather Observation Station 9
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE 
CITY NOT LIKE 'A%' 
AND
CITY NOT LIKE 'E%'
AND
CITY NOT LIKE 'I%'
AND
CITY NOT LIKE 'O%'
AND
CITY NOT LIKE 'U%';
```

## Weather Observation Station 10
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE 
CITY NOT LIKE '%A' 
AND
CITY NOT LIKE '%E'
AND
CITY NOT LIKE '%I'
AND
CITY NOT LIKE '%O'
AND
CITY NOT LIKE '%U';
```

## Weather Observation Station 11
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE 
(
CITY NOT LIKE 'A%' 
AND
CITY NOT LIKE 'E%'
AND
CITY NOT LIKE 'I%'
AND
CITY NOT LIKE 'O%'
AND
CITY NOT LIKE 'U%'
)
OR
(
CITY NOT LIKE '%A' 
AND
CITY NOT LIKE '%E'
AND
CITY NOT LIKE '%I'
AND
CITY NOT LIKE '%O'
AND
CITY NOT LIKE '%U'
);
```

## Weather Observation Station 12
```sql
SELECT DISTINCT CITY FROM STATION 
WHERE 
(
CITY NOT LIKE 'A%' 
AND
CITY NOT LIKE 'E%'
AND
CITY NOT LIKE 'I%'
AND
CITY NOT LIKE 'O%'
AND
CITY NOT LIKE 'U%'
)
AND
(
CITY NOT LIKE '%A' 
AND
CITY NOT LIKE '%E'
AND
CITY NOT LIKE '%I'
AND
CITY NOT LIKE '%O'
AND
CITY NOT LIKE '%U'
);
```

## Higher Than 75 Marks
```sql
SELECT Name FROM STUDENTS WHERE Marks > 75 ORDER BY SUBSTR(Name, LENGTH(Name)-2) ASC, ID ASC;
```

## Employee Names
```sql
SELECT name FROM Employee ORDER BY name;
```

## Employee Salaries
```sql
SELECT name FROM Employee WHERE salary > 2000 AND months < 10;
SELECT name FROM Employee WHERE salary > 2000 AND months < 10 ORDER BY employee_id ASC;
```

## Revising Aggregations - The Count Function
```sql
SELECT COUNT(ID) FROM CITY WHERE POPULATION > 100000;
```

## Revising Aggregations - The Sum Function
```sql
SELECT SUM(POPULATION) FROM CITY
WHERE DISTRICT = 'California';
```

## Revising Aggregations - Averages
```sql
SELECT AVG(POPULATION) FROM CITY WHERE DISTRICT = 'California';
```

## Average Population
```sql
SELECT ROUND(AVG(POPULATION)) FROM CITY;
```

## Japan Population
```sql
SELECT SUM(POPULATION) FROM CITY WHERE COUNTRYCODE = 'JPN';
```

## Population Density Difference
```sql
SELECT (MAX(POPULATION) - MIN(POPULATION)) AS Difference FROM CITY;
```

## The Blunder
```sql
## Function : AVG(), REPLACE()
SELECT CEIL(AVG(Salary) - AVG(replace(Salary, 0, ''))) AS Error FROM EMPLOYEES;
```

## Top Earners
```sql
SELECT salary*months, COUNT(*) FROM Employee GROUP BY salary*months ORDER BY salary*months DESC LIMIT 1;
```

## Weather Observation Station 14
```sql
SELECT ROUND(MAX(LAT_N), 4) FROM STATION WHERE LAT_N < 137.2345;
```

## Weather Observation Station 15
```sql
SELECT ROUND(LONG_W, 4) FROM STATION
WHERE LAT_N = (SELECT MAX(LAT_N) FROM STATION WHERE LAT_N < 137.2345);
;
```

## Weather Observation Station 16
```sql
SELECT ROUND(MIN(LAT_N), 4) FROM STATION WHERE LAT_N > 38.7880;
```

## Weather Observation Station 17
```sql
SELECT ROUND(LONG_W, 4) FROM STATION 
WHERE LAT_N = (SELECT MIN(LAT_N) FROM STATION WHERE LAT_N > 38.7880);
```

## Weather Observation Station 18
```sql
SELECT ROUND(ABS(A-C) + ABS(B-D), 4) AS ManhattanDistance FROM
(
SELECT MIN(LAT_N) AS A, MIN(LONG_W) AS B, MAX(LAT_N) AS C, MAX(LONG_W) AS D FROM STATION
) AliasTable;
```

## Weather Observation Station 19
```sql
SELECT ROUND(SQRT(POWER(A-C, 2) + POWER(B-D, 2)), 4) AS EuclideanDistance FROM
(
SELECT MIN(LAT_N) AS A, MIN(LONG_W) AS B, MAX(LAT_N) AS C, MAX(LONG_W) AS D FROM STATION
) AliasTable;
```

## Weather Observation Station 20
```sql
SELECT ROUND(LAT_N, 4) FROM STATION S1
WHERE (SELECT CEIL((COUNT(ID)/2) - 1) FROM STATION) = 
(SELECT COUNT(S2.ID) FROM STATION S2 WHERE S2.LAT_N > S1.LAT_N ORDER BY LAT_N ASC) 
ORDER BY LAT_N ASC;
```

## Type of Triangle
```sql
SELECT 
    IF(A + B <= C OR B + C <= A OR A + C <= B, 'Not A Triangle', 
       IF(A = B AND B = C, 'Equilateral',
          IF((A = B AND B != C) OR (A = C AND A != B), 'Isosceles', 
             IF(A != B AND B != C AND C != A, 'Scalene', '')
           )
        )
     )
     AS TriangleType
FROM TRIANGLES;
```

## African Cities
```sql
SELECT CITY.NAME FROM COUNTRY INNER JOIN CITY ON COUNTRY.CODE = CITY.COUNTRYCODE WHERE CONTINENT = 'Africa';
```

## Average Population of Each Continent
```sql
SELECT DISTINCT CONTINENT, FLOOR(AVG(CITY.POPULATION)) AS AverageCityPopulation FROM COUNTRY INNER JOIN CITY ON COUNTRY.CODE = CITY.COUNTRYCODE GROUP BY CONTINENT ORDER BY AverageCityPopulation;
```

## The Report
```sql
SELECT IF(GRADES.GRADE >=8, STUDENTS.NAME, NULL), GRADES.GRADE, STUDENTS.MARKS
FROM STUDENTS CROSS JOIN GRADES
WHERE STUDENTS.MARKS BETWEEN GRADES.MIN_MARK AND GRADES.MAX_MARK
ORDER BY GRADES.GRADE DESC, STUDENTS.NAME ASC;
```

##  Draw The Triangle 1
```sql
SET @NUM = 21;
SELECT REPEAT('* ', @NUM := @NUM - 1) FROM INFORMATION_SCHEMA.TABLES LIMIT 20;
```

## Draw The Triangle 2 
```sql
SET @ROWS = 20;
SET @ITR = 0;
SELECT REPEAT('* ', @ITR := @ITR + 1) FROM INFORMATION_SCHEMA.TABLES LIMIT 20;
```

## Population Census
```sql
SELECT SUM(CITY.POPULATION) AS TotalCitiesPopulationInAsia FROM COUNTRY INNER JOIN CITY ON COUNTRY.CODE = CITY.COUNTRYCODE WHERE CONTINENT = 'Asia';
```



## OVER(PARITION BY ____ ORDER BY ____)
## SELECT ID, NAME, GENDER, DENSE_RANK() OVER(PARTITION BY GENDER ORDER BY NAME ASC, GENDER DESC) AS RANK FROM GENERAL;
## DENSE_RANK() Window function assigns a rank to each row with in a partition



#  MEDIUM

## The Pads
### Functions : CONCAT(), COUNT(), LOWER()
```sql
SELECT CONCAT(Name, '(', SUBSTR(Occupation, 1, 1), ')') FROM OCCUPATIONS ORDER BY Name ASC;
SELECT CONCAT('There are a total of ', COUNT(Occupation), ' ', LOWER(Occupation), 's.') AS Total FROM OCCUPATIONS GROUP BY Occupation ORDER BY COUNT(Occupation), Occupation ASC;
```

## Top Competitors
```sql
SELECT 
    H.HACKER_ID AS HACKER_ID, 
    NAME
FROM SUBMISSIONS S
INNER JOIN CHALLENGES C ON S.CHALLENGE_ID = C.CHALLENGE_ID 
INNER JOIN HACKERS H ON S.HACKER_ID = H.HACKER_ID 
INNER JOIN DIFFICULTY D ON 
                            C.DIFFICULTY_LEVEL = D.DIFFICULTY_LEVEL  
                            AND
                            S.SCORE = D.SCORE
GROUP BY H.HACKER_ID, NAME 
HAVING COUNT(H.HACKER_ID) > 1
ORDER BY COUNT(H.HACKER_ID) DESC, H.HACKER_ID ASC;
```


## Challenges
##  Number of `Challenges` created by `hackers`
```sql
SELECT H.NAME AS NAME, COUNT(CHALLENGE_ID) AS ChallengesCreatedByHacker
FROM CHALLENGES C
INNER JOIN HACKERS H ON C.HACKER_ID = H.HACKER_ID
GROUP BY C.HACKER_ID, H.NAME;
```

##  Maximum number of `Challenges` created by a `hacker`
```sql
SELECT MAX(MCVALUE) 
FROM
(
SELECT COUNT(CM.CHALLENGE_ID) AS MCVALUE
FROM CHALLENGES CM
INNER JOIN HACKERS HM ON CM.HACKER_ID = HM.HACKER_ID
GROUP BY CM.HACKER_ID, HM.NAME
) MALIAS;
```


## Contest Leaderboard
```sql
SELECT HACKER_ID, NAME, SUM(CHALLENGE_MAXIMUM_SCORE) AS HACKER_TOTAL_SCORE 
FROM
(
SELECT 
        H.HACKER_ID AS HACKER_ID,
        H.NAME AS NAME,
        MAX(S.SCORE) AS CHALLENGE_MAXIMUM_SCORE
FROM SUBMISSIONS S
INNER JOIN HACKERS H ON S.HACKER_ID = H.HACKER_ID
GROUP BY S.CHALLENGE_ID, H.NAME, H.HACKER_ID
) ALIASTABLE
GROUP BY HACKER_ID, NAME 
HAVING SUM(CHALLENGE_MAXIMUM_SCORE) != 0
ORDER BY SUM(CHALLENGE_MAXIMUM_SCORE) DESC, HACKER_ID ASC;
```


## Binary Tree Nodes
##  ROOT NODE P IS NULL
##  LEAF NODE IS NOT PRESENT IN P
##  INTERNAL NODE IS PRESENT IN N AND P
```sql
SELECT 
        N,
        IF(P IS NULL, 'Root', 
           IF((SELECT COUNT(P) AS C FROM BST GROUP BY P HAVING P = N) > 0, 'Inner', 
              'Leaf')) AS CATEGORY
FROM BST ORDER BY N;
```

## Ollivander's Inventory
```sql
SELECT
        W.ID,
        WP.AGE,
        W.COINS_NEEDED,
        W.POWER
FROM WANDS W
INNER JOIN WANDS_PROPERTY WP ON W.CODE = WP.CODE
INNER JOIN
(
    SELECT 
            AGE AS _AGE,
            MIN(COINS_NEEDED) AS _MINIMUM_COINS_NEEDED,
            POWER AS _POWER
    FROM WANDS W1
    INNER JOIN WANDS_PROPERTY WP1 ON W1.CODE = WP1.CODE
    WHERE IS_EVIL = 0
    GROUP BY POWER, AGE
) AS ALIASTABLE
ON W.POWER = _POWER AND W.COINS_NEEDED = _MINIMUM_COINS_NEEDED AND WP.AGE = _AGE
ORDER BY W.POWER DESC, WP.AGE DESC;
```

## Symmetric Pairs
```sql
SELECT X, Y FROM
(
    (
        SELECT 
                F1.X AS X,
                F1.Y AS Y
        FROM Functions F1 
        WHERE X = Y
        GROUP BY X, Y HAVING COUNT(X) = 2
    )
    UNION
    (
        SELECT
                F1.X AS X,
                F1.Y AS Y
        FROM Functions F1, Functions F2
        WHERE 
        (F1.X = F2.Y AND F1.Y = F2.X)
        AND
        (F1.X < F1.Y)
    )
) B
ORDER BY X;
```
