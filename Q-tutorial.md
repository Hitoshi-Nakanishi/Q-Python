# ATOMS
## Numeric values
- **integer data**
  * int: `a: 42` or `a: 42i`
  * short: `b:-123h`   
  * long: `c:10000000j`
- **floating point data**
  * float: `pi: 3.14159` or `float1: 1f` <br>
     it's at least 15 decimal digits of precision and called **double** in other languages.
  * real: `r:1.4142e`
     it's at least 6 decimal digits of precision and called **float** in other languages.
  * scientific notation: `f:1.23e-10` or `f:1.23e-10e`
- **binary data** <br>
  *q* is more like C than its descendents, binary types are considered to be **positive integeres**. <br>
  they can participate in arithmetic expressions or comparisions.
  * boolean: `bit:0b`
  * byte: `byte:0x2a`

## Character values
- **char**: `ch:"q"`, `ch:"\""`, `ch:"\n"` <br>
  a char holds an individual ASCII character and is stored in one byte. <br>
  it corresponds to a SQL CHAR. <br>
- **symbol**: ``s1:\`abcd`` <br>
  A symbol holds a sequence of characters as a single unit, but it not a string. <br>
  In *q* there is an analogue of strings, namely **a list of char**.

## Temporal data
*q* extends the basic SQL date and time data types to facilitate temporal arithmetric, which is minimal in SQL and clumsy in verbose languages.
- **date**: `d:2017.06.07` <br>
  A date value stores the count of days from Jan 1, 2000 <br>
  ```int$2000.02.01`` returns 31
- **time**: ``t:10:00:59.000``
- **datetime**: ``dt:2017.06.07T10:00:59.000``
- **month**: ``mon:2017.06m``
- **minute**: `mm:10:00`
- **secound**: `sec:10:00:59` <br>
  we do find `12:34:56=12:34:56.000` returns `1b`
The individual field values are all extracted as int.
```q
d:2017.06.07
d.year  -> 2017
d.mm    -> 7
d.dd    -> 6

fmm:{[x] `mm$x}
fmm 2017.06.07  -> 6
```

- infinities and NaN
  * positive float infinity: `0w`
  + NaN, or not a number: `0n`
- null values
  * `0b`, `0x00`, `0N`, `0Nj` <br>
  






