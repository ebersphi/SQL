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

