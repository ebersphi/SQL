


| Feature | `select_list` |  MSSQL | Oracle | PGSQL | MySql | MariaDb |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: |
| | [ ALL \| DISTINCT ]  | 2000 |
| | [ TOP ( expression ) [ PERCENT ] [ WITH TIES ] ] | 2000 |  n.a. | n.a. | | | 
| | {                                                 | 2000 | 
| core | &emsp;  *                                            | x | x | x | x | x | 
| | &emsp;  \| { table_name \| view_name \| table_alias }.* | 2000 |   
| | &emsp;  \| {                                           | 2000 | 
| | &emsp;&emsp;    [ { table_name \| view_name \| table_alias }. ]  | 2000 | 
| | &emsp;&emsp;&emsp;           { column_name \| $IDENTITY \| $ROWGUID }  | 2000 |  
| | &emsp;&emsp;      \| udt_column_name [ { . \| :: } { { property_name \| field_name }    | 2000 | 
| | &emsp;&emsp;&emsp;        \| method_name ( argument [ ,...n] ) } ]   | 2000 | 
| | &emsp;&emsp;     \| expression                                    | 2000 | 
| | &emsp;     }                                                  | 2000 | 
| | &emsp;    [ [ AS ] column_alias ]                           | 2000 | 
| | &emsp; \| column_alias = expression                        | 2000 | 
| | } [ ,...n ]                                              | 2000 |   


`select_list` ::=   
&emsp;    {   
&emsp;&emsp;      *   
&emsp;&emsp;      | { table_name | view_name | table_alias }.*   
&emsp;&emsp;      | {  
&emsp;&emsp;          [ { table_name | view_name | table_alias }. ]  
&emsp;&emsp;&emsp;               { column_name | \$IDENTITY | \$ROWGUID }   
&emsp;&emsp;          | udt_column_name [ { . | :: } { { property_name | field_name }   
&emsp;&emsp;&emsp;            | method_name ( argument [ ,...n] ) } ]  
&emsp;&emsp;          | expression  
&emsp;&emsp;         }  
&emsp;&emsp;        [ [ AS ] column_alias ]   
&emsp;&emsp;      | column_alias = expression   
&emsp;    } [ ,...n ]   


|   | ORDER BY | ORDER BY order_by_expression [ COLLATE collation_name ][ ASC\|DESC ][ , ...n ][`offset_fetch` ] | 2000 |
