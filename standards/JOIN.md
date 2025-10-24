

## FROM syntax (SQL-86)
```
   FROM  <table-expr> [ , <table-expr> ... ]
   WHERE <filter-predicates> | <join-predicates>
```

## FROM syntax (SQL-92)
```
    FROM <table-expr> <JOIN-keyword> <table-expr> [ ON <join-predicates> ]
    WHERE <filter-predicates>
```

**IMPORTANT**
<br>The join-predicates are applied to generate the data set on which the filter-predicates will be applied.

> NOTE:
> You may also use filter predicates in the ON-Clause and/or put join-predicates in the WHERE-Clause.
> <br>Doing this with an INNER JOIN has no incidence on the resultset. But may have an incidence on the processing.
> <br>Doing this with all other JOIN types may have an incidence on the resultset as well as the processing.   </bold>

``` 
join-clause ::= <table-expr> <JOIN-keyword> <table-expr> [ ON <join-predicates> ]
```
<table>
<tr><th>Join type</th><th>JOIN-keyword</th><th> Operation</th></tr>
<tr><td>Inner join </td><td> [INNER] JOIN </td><td> get all rows from 2 table-expr matching the join-predicates </td></tr>
<tr><td>Outer join</td><td colspan=2>get all rows from 2 table-expr matching the join-predicates, plus the non matching rows from </td></tr>
<tr><td></td><td>
<li>LEFT [OUTER] JOIN</li>
<li>RIGHT [OUTER] JOIN</li>
<li>FULL [OUTER] JOIN</li></td>
<td>
<li>the first &lt;table-expr&gt; (LEFT)</li>
<li>the second &lt;table-expr&gt; (RIGHT)</li>
<li>both &lt;table-expr&gt;</li>
</td></tr>
<tr><td> Natural join</td><td>NATURAL</td><td>No join-predicates are allowed,
<br> an equi-join is done for all
<br>name matching columns in both &lt;table-expr&gt;
<tr><td rowspan=3> Collateral join</td><td>LATERAL</td><td>if the second &lt;table-expr&gt; is a sub-query
<br> it may references columns from the first &lt;table-expr&gt;
<br> in its &lt;filter-predicates&gt;</td></tr>
<tr><td>CROSS APPLY</td><td>The first &lt;table-expr&gt; may reference columns
<br> from the second &lt;table-expr&gt;
<br> in its &lt;filter-predicates&gt;</td></tr>
<tr><td>OUTER APPLY</td><td>get all rows from the first &lt;table-expr&gt;
<br>and only those from the second &lt;table-expr&gt; 
<br>matching the join-predicates<br>for the row-set of the first &lt;table-expr&gt;</td></tr>
</table>

### USING()  Keyword

## Implementation by SGBD Vendors

| Keywords | ANSI/ISO | DB2 LUW | DB2 zOS| H2 | MSSQL | MySQL | MariaDB | PGSQL | Oracle |
| :---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |
| \[INNER] JOIN | SQL-92 | V2 | V2 | V1 | 7.0 (1998) | V4 | V5 | V6 | V7 |
| LEFT \[OUTER] JOIN | SQL-92 | V4 (1994) | | V1 | 6.5 (1996) | N.S. | N.S. | V6 | V7 |
| RIGHT \[OUTER] JOIN | SQL-92 | V4 (1994) | | V1 | 6.5 (1996) | N.S. | N.S. | V6 | V7 |
| FULL \[OUTER] JOIN | SQL-92 | V4 (1994) | | 1.4.200 (2016) | 6.5 (1996) |  N.S. | N.S. | 7.1 (2001) | 9i (2001) |
| CROSS JOIN | SQL-92 | V9 |  V10 | V1 | 7.0 (1998) | V4 | V5 | V6 | V7 |
| NATURAL \[JOIN] | SQL:1999 | N.S. | N.S. | V1 | N.S. | 5.0.12 (2005) | V5 | V6 | 9i (2011) |
| LATERAL | SQL:2011 | TABLE<sup>1</sup> | V6<sup>1</sup> (1998)  | 1.4.200 (2016) | N.S. | 8.0.14 (2018) | 10.3.3 (2018) | 8.0.10 (2018) | 12c (2013) |
| CROSS APPLY | N.S. | N.S. | N.S. | N.S. | 9.0 (2005) | N.S. | N.S. | N.S. | 12c (2013) |
| OUTER APPLY | N.S. | N.S. | N.S. | N.S. | 9.0 (2005) | N.S. | N.S. | N.S. | 12c (2013) |

<sup>1</sup> LATERAL is synonym for TABLE keyword. DB z/OS only supports TABLE keyword.
</br>N.S. Not Supported

*References*
</br>ISO/IEC 9075‑2:1999 (“SQL/Foundation” part of SQL:1999) see Clause 7.7 “\<joined table>” and Clause 7.5 “\<from clause>”.
</br>https://docs.actian.com/vector/5.0/index.html#page/SQLLang/ANSI_2fISO_Join_Syntax.htm
</br>https://conferences.gse.org.uk/2021/presentations/2AD.pdf
