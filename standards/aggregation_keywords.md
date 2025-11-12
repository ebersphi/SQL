

| Standard | Feature | Keyword | Implementation | MSSQL | Oracle | PGSQL | MySql | MariaDb |
| :--- | :---: | :---: | :--- | :---: | :---: | :---: | :---: | :---: |
| |   | APPROX_COUNT_DISTINCT | approx_count_distinct(expression) -> bigint  | 2019 |  |  |  |  |
| SQL:1999 | 7.10.4 | GROUPING | grouping( <column_expression> ) -> 0 ou 1 | 2000 |
| SQL:2003 | F.2.14 | GROUPING_ID | grouping_id(<column_expression> [ , ...n ] ) -> int | 2000 |
| SQL:2003 | 10.9  | OVER | OVER ( [ `PARTITION BY clause` ] [ `ORDER BY clause` ] [ `ROW or RANGE clause` ] ) | 2000 |
| SQL:2003 | 10.9.6  | UNBOUNDED | window frame specification | 


#References

| Standard | ISO/IEC Document | Main feature introduced |
| :--- | :--- | :--- |
| SQL:1999	ISO/IEC 9075-2:1999	| Grouping sets, ROLLUP, CUBE |
|SQL:2003	ISO/IEC 9075-2:2003 | window (analytic) functions |
|SQL:2003	ISO/IEC 9075-2:2003 | window frame defintions |

Standard edition: SQL:2003
Document: ISO/IEC 9075-2:2003 (SQL/Foundation)
Clause: 10.9.6

`window frame bound` ::= 
    UNBOUNDED PRECEDING | UNBOUNDED FOLLOWING | `unsigned value specification` PRECEDING | `unsigned value specification` FOLLOWING | CURRENT ROW


MSSQL : `offset_fetch` ::= {\
    OFFSET { integer_constant | offset_row_count_expression } { ROW | ROWS } \
    [ \
      FETCH { FIRST | NEXT } { integer_constant | fetch_row_count_expression } { ROW | ROWS } ONLY \
    ] \
} ;;

MSSQL : `PARTITION BY clause` ::= PARTITION BY value_expression , ... [ n ] ;;

MSSQL : `ORDER BY clause` ::= ORDER BY order_by_expression [ COLLATE collation_name ] [ ASC | DESC ] [ , ...n ] ;;

MSSQL : `ROW or RANGE clause` ::=  { ROWS | RANGE } `window frame extent` ;;

MSSQL : `window frame extent` ::=  \
&emsp;{   `window frame preceding` \
&emsp;| `window frame between` \
&emsp;};;

MSSQL : `window frame between` ::= \
  BETWEEN `window frame bound` AND `Window frame bound` ;;

MSSQL : `window frame bound` ::= \
&emsp; {   `window frame preceding` \
&emsp;&emsp;  | `window frame following` \
&emsp;} ;;

MSSQL : `window frame preceding` ::= \
&emsp;{\
&emsp;&emsp;    UNBOUNDED PRECEDING\
&emsp;&emsp; | `unsigned_value_specification` PRECEDING\
&emsp; | CURRENT ROW\
&emsp;} ;;

MSSQL : `window frame following` ::=\
{\
&emsp;    UNBOUNDED FOLLOWING\
&emsp;  | `unsigned_value_specification` FOLLOWING\
&emsp;  | CURRENT ROW\
} ;;

MSSQL : `unsigned value specification` ::= {  `unsigned integer literal` } ;;
