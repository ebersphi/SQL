

INNER JOIN
OUTER JOIN
NATURAL JOIN

| Keywords | ANSI/ISO | DB2 LUW | DB2 zOS| H2 | MSSQL | MySQL | MariaDB | PGSQL | Oracle |
| :---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |
| \[INNER] JOIN | SQL-92 | V2 | V2 | V1 | 7.0 (1998) | V4 | V5 | V6 | V7 |
| LEFT \[OUTER] JOIN | SQL-92 | V4 (1994) | | V1 | 6.5 (1996) | N.S. | N.S. | V6 | V7 |
| RIGHT \[OUTER] JOIN | SQL-92 | V4 (1994) | | V1 | 6.5 (1996) | N.S. | N.S. | V6 | V7 |
| FULL \[OUTER] JOIN | SQL-92 | V4 (1994) | | 1.4.200 (2016) | 6.5 (1996) |  N.S. | N.S. | 7.1 (2001) | 9i (2001) |
| CROSS JOIN | SQL-92 | V9 |  V10 | V1 | 7.0 (1998) | V4 | V5 | V6 | V7 |
| NATURAL \[JOIN] | SQL:1999 | N.S. | N.S. | V1 | N.S. | 5.0.12 (2005) | V5 | V6 | 9i (2011) |
| LATERAL | SQL:2011 | TABLE<sup>1</sup> | V6<sup>1</sup> (1998)  | 1.4.200 (2016) | N.S. | 8.0.14 (2018) | 10.3.3 (2018) | 8.0.10 (2018) | 12c (2013) |
| CROSS APPLY | N.S. | N.S. | N.S. | 9.0 (2005) | N.S. | N.S. | N.S. | N.S. | 12c (2013) |
| OUTER APPLY | N.S. | N.S. | N.S. | 9.0 (2005) | N.S. | N.S. | N.S. | N.S. | 12c (2013) |

<sup>1</sup> LATERAL is synonym for TABLE keyword. DB z/OS only supports TABLE keyword.
N.S. Not Supported

References
ISO/IEC 9075‑2:1999 (“SQL/Foundation” part of SQL:1999) see Clause 7.7 “\<joined table>” and Clause 7.5 “\<from clause>”.
https://docs.actian.com/vector/5.0/index.html#page/SQLLang/ANSI_2fISO_Join_Syntax.htm
https://conferences.gse.org.uk/2021/presentations/2AD.pdf
