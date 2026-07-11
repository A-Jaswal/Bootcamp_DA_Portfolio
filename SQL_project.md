## 📘 SQL Queries & Output Screenshots

### 1️⃣ Count Cities in USA
SELECT COUNT(*) AS Cities_in_USA
FROM city
WHERE CountryCode = 'USA';

![Query 1 Output](Images/query1_output.png)

---

### 2️⃣ Country with Highest Life Expectancy
SELECT Name AS Country, LifeExpectancy
FROM country
ORDER BY LifeExpectancy DESC
LIMIT 1;

![Query 2 Output](Images/query2_output.png)

---

### 3️⃣ Cities Containing 'New'
SELECT Name AS City
FROM city
WHERE Name LIKE '%New%';

![Query 3 Output](Images/query3_output.png)

---

### 4️⃣ First 10 Cities by Population
SELECT Name AS City, Population
FROM city
ORDER BY Population DESC
LIMIT 10;

![Query 4 Output](Images/query4_output.png)

---

### 5️⃣ Cities with Population > 2,000,000
SELECT Name AS City, Population
FROM city
WHERE Population > 2000000
ORDER BY Population DESC;

![Query 5 Output](Images/query5_output.png)

---

### 6️⃣ Cities Beginning with 'Be'
SELECT Name AS City
FROM city
WHERE Name LIKE 'Be%';

![Query 6 Output](Images/query6_output.png)

---

### 7️⃣ Cities with Population Between 500,000 and 1,000,000
SELECT Name AS City, Population
FROM city
WHERE Population BETWEEN 500000 AND 1000000;

![Query 7 Output](Images/query7_output.png)

---

### 8️⃣ Cities Sorted Alphabetically
SELECT Name AS City
FROM city
ORDER BY Name ASC;

![Query 8 Output](Images/query8_output.png)

---

### 9️⃣ Most Populated City
SELECT Name AS City, MAX(Population) AS Population
FROM city
GROUP BY Name
ORDER BY Population DESC
LIMIT 1;

![Query 9 Output](Images/query9_output.png)

---

### 🔟 City Name Frequency Analysis
SELECT DISTINCT Name AS City, COUNT(Name)
FROM city
GROUP BY Name
ORDER BY Name;

![Query 10 Output](Images/query10_output.png)

---

### 1️⃣1️⃣ City with the Lowest Population
SELECT Name AS City, MIN(Population) AS Population
FROM city
GROUP BY Name
ORDER BY Population ASC
LIMIT 1;

![Query 11 Output](Images/query11_output.png)

---

### 1️⃣2️⃣ Country with Largest Population
SELECT Name AS Country, MAX(Population) AS Population
FROM country
GROUP BY Name
ORDER BY Population DESC
LIMIT 1;

![Query 12 Output](Images/query12_output.png)

---

### 1️⃣3️⃣ Capital of Spain
SELECT c.Name AS Country, ci.Name AS Capital
FROM Country c
JOIN City ci ON c.Capital = ci.ID
WHERE c.Name = 'Spain';

![Query 13 Output](Images/query13_output.png)

---

### 1️⃣4️⃣ Cities in Europe
SELECT c.Continent, ci.Name AS City
FROM Country c
JOIN City ci ON c.Capital = ci.ID
WHERE c.Continent = 'Europe';

![Query 14 Output](Images/query14_output.png)

---

### 1️⃣5️⃣ Average Population by Country
SELECT Name AS Country, AVG(Population) AS Avg_Population
FROM Country
GROUP BY Name;

![Query 15 Output](Images/query15_output.png)

---

### 1️⃣6️⃣ Capital Cities Population Comparison
SELECT Name AS City, Population
FROM city
ORDER BY Population DESC;

![Query 16 Output](Images/query16_output.png)

---

### 1️⃣7️⃣ Countries with Low Population Density
SELECT Name AS Country, Population
FROM country
ORDER BY Population ASC;

![Query 17 Output](Images/query17_output.png)

---

### 1️⃣8️⃣ Cities with High GDP per Capita
SELECT ci.Name AS City, c.GNP AS GDP_per_capita
FROM city ci
JOIN Country c ON ci.ID = c.Capital
WHERE GNP = (SELECT AVG(GNP))
ORDER BY GNP DESC;

![Query 18 Output](Images/query18_output.png)

---

### 1️⃣9️⃣ Display Cities (Rows 31–40)
SELECT Name AS City, Population
FROM city
ORDER BY Population
LIMIT 10 OFFSET 30;

![Query 19 Output](Images/query19_output.png)

