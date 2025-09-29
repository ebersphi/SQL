

cte-table-definition ::= `cte-name` \[ ( `column-names` ) ] AS ( `SELECT-expr` ) ;;

cte-recursive-definition ::=  { RECURSIVE<sup>4</sup> } `cte-name` \[ ( `column-names` )  AS ( `initial-select` UNION ALL `SELECT-expr` ) ;;

cte-declaration ::=  WITH  { `cte-table-definition` |  `cte-recursive-definition` } \[ , ... ] `dml-expression` ;;

cte-name ::= `sql-identifier` ;;

column-names ::= `sql-identifier` \[ , ... ] ;;

dml-expression ::=  `SELECT-expr` |  `UPDATE-expr` |  `MERGE-expr` | `INSERT-expr` |  `DELETE-expr` ;;

initial-select ::= `SELECT-expr` ::

select-expr ::= SELECT `select-clause` \[  
\[ FROM<sup>1</sup> `from-clause` ] 
\[ WHERE `where-clause>` ] 
\[  GROUP BY<sup>2</sup> `group-by-clause` ] 
\[ HAVING `having-clause`] 
\[ ORDER BY<sup>3</sup> `order-by-clause` ] 
    ] ;;


NOTES<br>
  <sup>1</sup> Until Oracle 21c the FROM keyword is required

  <sup>2</sup> HAVING requires GROUP BY for Oracle and PostgreSQL

  <sup>3</sup> ORDER BY cannot appear in subqueries for MSSQL<br>
  <sup>3</sup> ORDER BY is ignored by PostgreSQL 

  <sup>4</sup> The RECURSIVE keyword is mandatorily specific to PostgreSQL<br>
  <sup>4</sup> The RECURSIVE keyword is not used by any other database vendor

## cte-table-definition 

| Syntax | MSSQL | Oracle | Postgresql | MySql | MariaDB |
|:---:|:---:|:---:|:---:|:---:|:---:|
| WITH | WITH |WITH |WITH |WITH |WITH |
| `cte-name` | `cte-name` | `cte-name` | `cte-name` | `cte-name` | `cte-name` |
| ( `column-names` ) | optional | N/A | optional |
| AS | AS | AS | AS | AS | AS |
| ( | ( | ( | ( | ( | ( |
| `SELECT-expr` | 
| ) | ) | ) | ) | ) | ) |
|  `dml-expression` | 
| *  `SELECT-expr` |
| *  `UPDATE-expr` |
| *  `MERGE-expr` |
| *  `INSERT-expr` |
| *  `DELETE-expr` |
