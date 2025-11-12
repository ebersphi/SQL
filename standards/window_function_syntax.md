
Oracle - version 8.1.6 in 2000.[12][13]
PostgreSQL - version 8.4 in 2009.[14]
MySQL - version 8 in 2018.[15][16]
MariaDB - version 10.2 in 2016.[17]
SQLite - release 3.25.0 in 2018.[18]
Windows function

https://en.wikipedia.org/wiki/Window_function_(SQL)

https://sqlite.org/windowfunctions.html


| Standard |Feature | Description/Keyword | MariaDB | MySQL | Oracle | PostgreSQL | SQL Server | SQLite |
| :-- | :-- | :-- | :---: | :---: | :---: | :---: | :---: | :---: |
| SQL:2003 |  | Windows Functions | 10.2 (216) | 8 (2018) | 8.1.6 (2000) | 8.4 (2009) |  | 3.25.0 (2018) |


## `window frame clause` ::=  `window frame units` `window frame extent`

`window frame extent` ::=  `window frame start`  \| BETWEEN `window frame start` AND `window frame end`


| Syntax elements | ISO Feature | MariaDB | MySQL | Oracle | PostgreSQL | SQL Server | SQLite |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| `window frame units` ||||||||
|  RANGE  |  |  |  |  |  |  | x |
|  ROWS   |  |  |  |  |  |  | x |
|  GROUPS |  |  |  |  |  |  | x |
| `window frame start` |  |  |  |  |  |  |  |
| UNBOUNDED PRECEDING |  |  |  |  |  |  |  |
| UNBOUNDED FOLLOWING |  |  |  |  |  |  |  |
| `uint` PRECEDING |  |  |  |  |  |  |  |
| `uint` FOLLOWING |  |  |  |  |  |  |  |
| CURRENT ROW | |  |  |  |  |  |  |


Based on Standard: ISO/IEC 9075-2:2003 (SQL/Foundation)
Clause 10.9 — window function

`window function` ::=
    `window function type` OVER `window name or specification`

`window function type` ::=
      `rank function type`
    | `aggregate function`
    | `value expression primary`        -- for windowed scalar functions

`window name or specification` ::=
    `window name` | `in-line window specification`

`in-line window specification` ::=
    ( [ `existing window name` ]
      [ PARTITION BY `value expression list` ]
      [ ORDER BY `sort specification list` ]
      [ `window frame clause` ] )


Standard: ISO/IEC 9075-2:2003
Clause 10.9.6 — window frame clause
Syntax (from §10.9.6, Figure 10-11)


`window frame clause` ::=
    `window frame units` `window frame extent`

`window frame units` ::= ROWS | RANGE

`window frame extent` ::=
      `window frame start`
    | BETWEEN `window frame start` AND `window frame end`

`window frame start` ::= `window frame bound`
`window frame end`   ::= `window frame bound`

`window frame bound` ::=
      UNBOUNDED PRECEDING
    | UNBOUNDED FOLLOWING
    | `unsigned value specification` PRECEDING
    | `unsigned value specification` FOLLOWING
    | CURRENT ROW


Examples
ROW_NUMBER() OVER (PARTITION BY department_id ORDER BY salary DESC)

SUM(salary) OVER (
  PARTITION BY department_id
  ORDER BY hire_date
  ROWS BETWEEN UNBOUNDED PRECEDING AND CURRENT ROW
)

