<img width="32766" height="21" alt="image" src="https://github.com/user-attachments/assets/eeacb27d-dbbb-4642-a799-c7ca40ca0d51" />

## Chronologic introduction of SQL features

|Norme |Document|Data types|Structure|Operators|Selection|DML|DDL|
|:---|:---|:---|:---|:---|:---|:---|:---|
|SQL-86 / SQL-89<br>ANSI:1986<br>ISO:1987|	SQL1	|NUMERIC<br> DECIMAL<br> INTEGER<br> SMALLINT<br> FLOAT<br> REAL<br> "DOUBLE PRECISION"|||SELECT<br>FROM<br>WHERE<br>"GROUP BY"<br>HAVING<br>"ORDER BY"	|INSERT<br>UPDATE<br>DELETE	|CREATE TABLE<br>CREATE VIEW|
|SQL-92|	SQL2|	date<br> time <br>timestamp<br> interval<br> bit<br> varchar<br> "national character"|	SCHEMA<br>"isolations transactionelles"|CAST<br>"CASE WHEN"|	"\[ INNER<br> \|LEFT<br> \|RIGHT<br> \|FULL<br> \|NATURAL<br> \|CROSS ] <br>&nbsp; JOIN"<br>UNION<br>INTERSECT<br>EXCEPT	||ALTER TABLE<br>DROP TABLE<br>ALTER VIEW|
SQL :1999	SQL3	LOB CLOB	OLAP		"ROLLUP
CUBE
GROUPING SETS
ORDER BY <expr>"		recursive CTE
SQL :2003	extension	"auto-generated columns
identity columns
BIT et ""BIT VARYING"""	sequence generator	XML functions	window functions	MERGE	"CREATE TABLE AS 
CREATE TABLE LIKE"
SQL :2006	extension			"storing XML
XQUERY"			
SQL :2008	extension		partitioned join tables	XQUERY reg exp/pattern matching		"MERGE
DIAGNOSTIC"	"TRUNCATE TABLE
INSTEAD OF triggers"
SQL :2011	extension		system-versioned tables (aka transaction time tables)	"CONTAINS OVERLAPS EQUALS 
[IMMEDIATELY] PRECEDES
[IMMEDIATELY]  SUCCEEDS "			temporal PK
SQL :2016	extension	DECFLOAT	support JSON	LISTAGG			polymorphic table fucntions
SQL :2019	extension		tableaux multidimensionnels				
SQL :2023	extension	JSON	"JSON related functions and operators
PGQ Property Graph Query"	"GRATEST LEAST
LPAD RPAD
ANY_VALUE
underscore in numeric literals + hexa, octal, binary"			
<img width="1204" height="701" alt="image" src="https://github.com/user-attachments/assets/82eaf165-0029-4706-a1b7-65581cceede1" />
