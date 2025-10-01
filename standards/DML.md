
| Feature | Syntax elements | MSSQL | Oracle | PGSQL | MySql | MariaDb |
|:--- | :--- | :---: |:---: |:---: |:---: |:---: |
| | [ WITH `common_table_expression` [ ,...n ] ] |
| | SELECT `select_list` [ INTO new_table ]      |
| | [ FROM table_source ]                        |
| | [ WHERE search_condition ]
| | [ GROUP BY group_by_expression ]
| | [ HAVING search_condition ]
| | [ WINDOW window_expression ]
| | [ ORDER BY order_expression [ ASC \| DESC ] ]


<pre>
[ WITH `common_table_expression` [ ,...n ] ]  
DELETE   
    [ TOP ( expression ) [ PERCENT ] ]   
    [ FROM ]   
    { { table_alias  
      | `object`
      | rowset_function_limited   
      [ WITH ( table_hint_limited [ ...n ] ) ] }   
      | @table_variable  
    }  
    [ `OUTPUT Clause` ]  
    [ FROM table_source [ ,...n ] ]   
    [ WHERE { `search_condition`   
            | { [ CURRENT OF   
                   { { [ GLOBAL ] cursor_name }   
                       | cursor_variable_name   
                   }   
                ]  
              }  
            }   
    ]   
    [ OPTION ( `Query Hint` [ ,...n ] ) ]   
[; ]  
</pre>

<pre>
`object` ::=  
{   
    [ server_name.database_name.schema_name.   
      | database_name. [ schema_name ] .   
      | schema_name.  
    ]  
    table_or_view_name   
}  
</pre>
