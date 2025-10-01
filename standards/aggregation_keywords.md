

| Feature | Keyword | Implementation | MSSQL | Oracle | PGSQL | MySql | MariaDb |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: | :---: |
|   | APPROX_COUNT_DISTINCT | approx_count_distinct(expression) -> bigint  | 2019 |  |  |  |  |
|   | GROUPING | grouping( <column_expression> ) -> 0 ou 1 | 2000 |
|   | GROUPING_ID | grouping_id(<column_expression> [ , ...n ] ) -> int | 2000 |
|   | OVER | OVER ( [ `PARTITION BY clause` ] [ `ORDER BY clause` ] [ `ROW or RANGE clause` ] ) | 2000 |







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
$~~${   `window frame preceding` \
$~~~~$  | `window frame between` \
$~~$} ;;

MSSQL : `window frame between` ::= \
  BETWEEN `window frame bound` AND `Window frame bound` ;;

MSSQL : `window frame bound` ::= \
$~~$ {   `window frame preceding` \
$~~~~$  | `window frame following` \
$~~$} ;;

MSSQL : `window frame preceding` ::= \
$~~${\
$~~~~$    UNBOUNDED PRECEDING\
$~~~~$ | `unsigned_value_specification` PRECEDING\
$~~~~$ | CURRENT ROW\
$~~$} ;;

MSSQL : `window frame following` ::=\
{\
$~~$    UNBOUNDED FOLLOWING\
$~~$  | `unsigned_value_specification` FOLLOWING\
$~~$  | CURRENT ROW\
} ;;

MSSQL : `unsigned value specification` ::= {  `unsigned integer literal` } ;;
