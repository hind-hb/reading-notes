## SQL

### Exercise 01 
**Find the title of each movie**
SELECT Title
FROM Movies;

**Find the director of each movie**
SELECT Director
FROM Movies;

**Find the title and director of each movie**
SELECT Title, Director
FROM Movies;

**Find the title and year of each movie**
SELECT Title, Director
FROM Movies;

**Find all the information about each movie**
SELECT *
FROM Movies;
![ex1](https://user-images.githubusercontent.com/75991604/155153396-5f750a46-a525-4146-812d-67a5b1c2d66b.png)
### Exercise 02
 CH2 - Queries with constraints (Pt. 1)

**Find the movie with a row id of 6**
SELECT *
FROM Movies
WHERE Id = 6;

**Find the movies released in the years between 2000 and 2010**
SELECT *
FROM Movies
WHERE Year BETWEEN 2000 AND 2010;

**Find the movies not released in the years between 2000 and 2010**
SELECT *
FROM Movies
WHERE Year NOT BETWEEN 2000 AND 2010;

**Find the first 5 Pixar movies and their release  year**
SELECT *
FROM Movies
WHERE Id BETWEEN 1 AND 5;
![ex2](https://user-images.githubusercontent.com/75991604/155153422-ba94af4e-4ac8-488a-b22a-79fb5ab06620.png)
### Exercise 03
 CH3 - Queries with constraints (Pt. 2)

**Find all the Toy Story movies**
SELECT *
FROM Movies
WHERE Title LIKE "%Toy Story%";

**Find all the movies directed by John Lasseter**
SELECT *
FROM Movies
WHERE Director = "John Lasseter";

**Find all the movies (and director) not directed by John Lasseter**
SELECT *
FROM Movies
WHERE Director != "John Lasseter";

**Find all the WALL-* movies**
SELECT *
FROM Movies
WHERE Title LIKE "%WALL%";

![ex3](https://user-images.githubusercontent.com/75991604/155153467-af9415dc-9e8b-40cc-84d1-e098588e025e.png)
### Exercise 04
** CH4 - Filtering and sorting Query results**

**List all directors of Pixar movies (alphabetically), without duplicates**
SELECT DISTINCT Director
FROM Movies
ORDER BY Director;

**List the last four Pixar movies released (ordered from most recent to least)**
SELECT *
FROM Movies
ORDER BY Year DESC
LIMIT 4;

**List the first five Pixar movies sorted alphabetically**
SELECT *
FROM Movies
ORDER BY Title ASC
LIMIT 5;

**List the next five Pixar movies sorted alphabetically**
SELECT *
FROM Movies
ORDER BY Title ASC
LIMIT 5
OFFSET 5;
![ex4](https://user-images.githubusercontent.com/75991604/155153506-d9303cb6-cfe9-411c-8503-480068ae23c2.png)
### Exercise 05

**CH5 - Review Simple SELECT Queries**

**List all the Canadian cities and their populations **
SELECT *
FROM North_american_cities
WHERE Country LIKE "Canada";

**Order all the cities in the United States by their latitude from north to south**
SELECT *
FROM North_american_cities
WHERE Country = "United States"
ORDER BY Latitude DESC;

 **List all the cities west of Chicago, ordered from west to east**
SELECT *
FROM North_american_cities
WHERE Longitude < -87.69
ORDER BY Longitude ASC;

**List the two largest cities in Mexico (by population)**
SELECT *
FROM North_american_cities
WHERE Country LIKE "Mexico"
ORDER BY Population DESC
LIMIT 2;

 **List the third and fourth largest cities (by population) in the United States and their population**
SELECT *
FROM North_american_cities
WHERE Country LIKE "United States"
ORDER BY Population DESC
LIMIT 2
OFFSET 2;
![ex5](https://user-images.githubusercontent.com/75991604/155153540-3baddabd-7c49-4488-958e-d376a6d0c7b1.png)
### Exercise 06
 **CH6 - Multi-table queries with JOINs**

**Find the domestic and international sales for each movie**
SELECT Title, International_sales, Domestic_sales
FROM Movies JOIN Boxoffice
ON Id=Movie_id;

**Show the sales numbers for each movie that did better internationally rather than domestically**
SELECT Title, International_sales, Domestic_sales
FROM Movies JOIN Boxoffice
ON Id=Movie_id
WHERE International_sales > Domestic_sales;

 **List all the movies by their ratings in descending order**
SELECT Title, Rating
FROM Movies JOIN Boxoffice
ON Id=Movie_id
ORDER BY Rating DESC;
![ex6](https://user-images.githubusercontent.com/75991604/155153573-9bd7c5f5-eed0-4237-bec7-589b33ade74f.png)
### Exercise 07

**Find the list of all buildings that have employees**
SELECT DISTINCT Building
FROM Employees
LEFT JOIN Buildings ON Building=Building_name
WHERE Years_employed NOT NULL;

**Find the list of all buildings and their capacity**
SELECT *
FROM Buildings;

**List all buildings and the distinct employee roles in each building (including empty buildings)**
SELECT DISTINCT Building_name, Role 
FROM Buildings 
LEFT JOIN employees ON building_name = building;
![ex7](https://user-images.githubusercontent.com/75991604/155153604-0bbdc4b5-4632-44f3-82a5-3fafbfe19a36.png)
### Exercise 08
**CH8 - A short note on NULLs**

**Find the name and role of all employees who have not been assigned to a building**
SELECT *
FROM Employees
LEFT JOIN Buildings
ON Building_name = Building
WHERE Building IS NULL;

 **Find the names of the buildings that hold no employees**
SELECT *
FROM Buildings
LEFT JOIN Employees
ON Building_name = Building
WHERE Building IS NULL;
![ex8](https://user-images.githubusercontent.com/75991604/155153633-9dbf3761-016d-41fa-997a-b2a5bbddef8d.png)
### Exercise 09
 **CH9 - Queries with expressions**

 **List all movies and their combined sales in millions of dollars**
SELECT Title, (Domestic_sales + International_sales)/1000000 AS Total_Sales_Millions
FROM Movies
LEFT JOIN Boxoffice ON Id=Movie_Id;

 **List all movies and their ratings in percent**
SELECT Title, Rating*10 as Percent
FROM Movies
LEFT JOIN Boxoffice ON Id=Movie_Id;

 List all movies that were released on even number years
SELECT Title, Year
FROM Movies
LEFT JOIN Boxoffice ON Id=Movie_Id
WHERE Year % 2 = 0;
![ex9](https://user-images.githubusercontent.com/75991604/155153702-1e040848-d290-48b2-a335-005f72957d48.png)
### Exercise 10
 **CH10 - Queries with aggregates (Pt. 1)**

**Find the longest time that an employee has been at the studio**
SELECT MAX(Years_employed)
FROM Employees;

**For each role, find the average number of years employed by employees in that role**
SELECT Role, AVG(Years_Employed) 
FROM Employees
GROUP BY Role;

 **Find the total number of employee years worked in each building**
SELECT Building, SUM(Years_Employed) 
FROM Employees
GROUP BY Building;
![ex10](https://user-images.githubusercontent.com/75991604/155153763-cd2a5a15-1a11-4231-b9dc-9c58cd20faa0.png)
### Exercise 11
**CH11 - Queries with aggregates (Pt. 2)**
 **Find the number of Artists in the studio (without a HAVING clause)**
SELECT Role, COUNT(*) AS Number_of_Artists
FROM Employees
WHERE Role = "Artist";

 **Find the number of Employees of each role in the studio**
SELECT Role, COUNT(*)
FROM Employees
GROUP BY Role;

**Find the total number of years employed by all Engineers**
SELECT Role, SUM(Years_Employed)
FROM Employees
GROUP BY Role
HAVING Role = "Engineer";
![ex11](https://user-images.githubusercontent.com/75991604/155153796-cf3b5f66-4ee9-4c96-8683-2817b4d77dec.png)
### Exercise 12
 **CH12 - Order of execution of a Query**

 **Find the number of movies each director has directed**
SELECT *, COUNT(Title)
FROM Movies
GROUP BY Director;

 **Find the total domestic and international sales that can be attributed to each director**
SELECT Director, sum(Domestic_sales + International_Sales) as Total_Sales
FROM Movies
LEFT JOIN Boxoffice ON Id = Movie_ID
GROUP BY Director;
![ex12](https://user-images.githubusercontent.com/75991604/155153827-5759eae5-50a7-4913-b521-eeed43b6e179.png)
### Exercise 13

 **CH13 - Inserting rows**

**Add the studio's new production, Toy Story 4 to the list of movies (you can use any director)**
INSERT INTO Movies,
VALUES (4, "Toy Story 4", "John Lasseter", 2017, 123);

 **Toy Story 4 has been released to critical acclaim! It had a rating of 8.7, and made 340 million domestically and 270 million internationally. Add the record to the  BoxOffice table.**
INSERT INTO Boxoffice
VALUES (4, 8.7, 340000000, 270000000);

![ex13](https://user-images.githubusercontent.com/75991604/155153902-0ea6b785-694e-4410-be2a-f4ec62f153b2.png)
### Exercise 14

 **CH14 - Updating rows**

 **The director for A Bug's Life is incorrect, it was actually directed by John Lasseter**
UPDATE Movies
SET Director = "John Lasseter"
WHERE Id = 2;

**The year that Toy Story 2 was released is incorrect, it was actually released in 1999**
UPDATE Movies
SET Year = "1999"
WHERE Id = 3;

 **Both the title and directory for Toy Story 8 is incorrect! The title should be "Toy Story 3" and it was directed by Lee Unkrich**
UPDATE Movies
SET Title = "Toy Story 3", Director = "Lee Unkrich"
WHERE Id = 11;
![ex14](https://user-images.githubusercontent.com/75991604/155153923-37032f76-38b1-400a-9d0a-8e3e46a99121.png)
### Exercise 15
**CH15 - Deleting rows**

**This database is getting too big, lets remove all movies that were released before 2005.**
DELETE FROM Movies
WHERE Year < 2005;

 **Andrew Stanton has also left the studio, so please remove all movies directed by him.**
DELETE FROM Movies
WHERE Director = "Andrew Stanton";


![ex15](https://user-images.githubusercontent.com/75991604/155153951-15154d94-5f65-4704-9ded-a792ee5b9174.png)
### Exercise 16
**CH16 - Creating Tables**

 Create a new table named Database with the following columns:
 1. Name A string (text) describing the name of the database
 2. Version A number (floating point) of the latest version of this database
 3. Download_count An integer count of the number of times this database was downloaded
 This table has no constraints.
CREATE TABLE Database (
    Name TEXT,
    Version FLOAT,
    Download_Count INTEGER);
![ex16](https://user-images.githubusercontent.com/75991604/155154002-8dcfe16c-d813-45eb-99cf-08f8f39d2b82.png)
### Exercise 17
 **CH17 - Altering Tables**

 Add a column named Aspect_ratio with a FLOAT data type to store the aspect-ratio each movie was released in.
ALTER TABLE Movies
  ADD COLUMN Aspect_ratio FLOAT DEFAULT 3;
  
Add another column named Language with a TEXT data type to store the language that the movie was released in. Ensure that the default for this language is English.
ALTER TABLE Movies
  ADD COLUMN Language TEXT DEFAULT "English";
![ex17](https://user-images.githubusercontent.com/75991604/155154039-74db1447-3f8b-46a5-a3d4-67474e47baf4.png)
### Exercise 18
 **CH18 - Dropping Tables**

 We've sadly reached the end of our lessons, lets clean up by removing the Movies table
DROP TABLE Movies;
 And drop the BoxOffice table as well
DROP TABLE BoxOffice;
![ex18](https://user-images.githubusercontent.com/75991604/155154103-25495261-6d12-4f54-91b8-25cafb95db06.png)

