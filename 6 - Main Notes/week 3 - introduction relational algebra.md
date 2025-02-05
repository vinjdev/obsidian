16/01/25 09:21
Fag: [[IDATG2204]]
Tags: [[NTNU]]
___
# week 3 - introduction relational algebra

*Unary operations*
relation based on one input realtion

projection

relationship is known as a entity

Relatonal query does *not* SQL syntax

predicate operation - conditional statement

# class exercises

### q1
projcetion of this will remove all the numbers resulting in only the names left

### q2

it will remove the county no attribute


# VIDEOS
## relational model
![[Pasted image 20250129143814.png]]
the elements in a realational data structure

![[Pasted image 20250131085607.png]]

## relational algebra
relation algebra is very important to have a better understanding of sql

### unary operations
Projections
![[Pasted image 20250204165711.png]]
use pi for symoblize
input relation is some sort of relationship that decices which row is ouputet

make a new subset of colums, the row is as big as what we project
![[Pasted image 20250204170331.png]]

*selections*
contains a subset of tuple for input relaitons based on a condition
![[Pasted image 20250204170428.png]]
![[Pasted image 20250204170511.png]]
check if make attribute is equal to mazda in car tabel
selection will give ALL the attribues, therefor COMBINE it with projections for the right information

for two conditions:
![[Pasted image 20250204170809.png]]
condition is regular conditions check in c and c++

![[Pasted image 20250204170856.png]]
set is for checking if its one of these three

Combining those two
![[Pasted image 20250204171031.png]]
can also decompose (basicly make a variable)

![[Pasted image 20250204171100.png]]
R is a relations variable that is passed into the projection

### set and join
Union is useful

takes two tuple, and removes duplicates
- same number of attributes
- corresponding attrubutes from same domain

![[Pasted image 20250204171326.png]]

useful for if we need all the relations (under one table) under one specific attriubute from different relations


*Cartestin product*
combines tuples from different tables

example
![[Pasted image 20250204175255.png]]
so very simple make a new table with new relation between two different tables

*equjoin (also cartesin product)*
does cartesion product based on a condition
![[Pasted image 20250204175838.png]]
her make a new table with a condition that check if dealer are the same in both tables

*outer join*
![[Pasted image 20250204180333.png]]

checks all tables rows to look for matching rows, if no result, it places NULL
![[Pasted image 20250204182128.png]]

![[Pasted image 20250204182134.png]]
usefull if some rows doesnit exitst but still need table


### Aggregations and grouping
*Aggregation*
holds a attriubute of some operation on a *row* (attriute in a row)
COUNT - teller antall forekomster av *rows*
SUM - teller tall under den specifice rowen
MIN - finds the minimum value in a attribute within a group
MAX - finds the maximum value in a attribute within a group
AVG - finds the average value in a attribute within a group
![[Pasted image 20250204183648.png]]

![[Pasted image 20250204184331.png]]

*Grouping*
![[Pasted image 20250204192250.png]]



# Referanse
