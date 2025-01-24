13/01/25 15:08
Fag: [[PROG2006]]
Tags: [[NTNU]]
___
# intro to haskell and starting out

imperative language
giving computer secquence of tasks
- while exec change states

haskell is lazy
- wont execute function and caclute without it being told

haskell is statically typed

functinos are called as a prefix without the ()

*function applications* - they have higher predecnece
- ofc

```haskell
succ 10 + 10
```
succ is the next number
so for 10 its 11, and 11 + 10 = 21

*call function as infix*
```haskell
92 `div` 10 

div 92 10
{-this is a comment-}
```
this is the same

parenthsesis are only used for precedence of order


## weird way of compiling and running code

```haskell
bar x = x + x
```

```bash
ghci
:l baby.hs

bar 10

```
with :l the functions gets loaded as module to be used in the terminal


else is mandatory

```haskell
doubleSmallNumber' x = (if x > 100 then x else x*2) + 1
```
this is valid syntax. ' can make a slight modified version of the function

list are homogenous. cant have different types

adding two lists togther
at the back
```haskell
[1,2,3] ++ [4,5,6]
```

: will put a elemnt at the start of the list
THIS IS WAY FASTER

```haskell
5 : [1,2,3,4]

[5,1,2,3,4]
```

list is jusst. alot of append to a empty list
```bash
2:3:4:[]
```

INDEXING????
```bash
[1,2,3,4,5] !! 3
this return 4????
```

list can be compared
lexicographical order.
sjekker første verdi. er det lik, tar den neste
```bash
[3,2,1]  > [2,1,0]
true
```

Head
henter første verdi
```bash
head [1,2,3]
1
```

Tail
alt bortsett fra head
```bash
tail [1,2,3]
[2,3]
```

last
siste
```bash
last [5,4,1,2]
2
```

init
motsatt av tail
```bash
init [1,2,3,4]
[1,2,3]
```

HEAD TAIL LAST INIT WONT WORK ON EMPTY LIST

length
```bash
length [1,2,3]
3
```

null
check if list is empty or not
```bash
null []
true
```

reverse
```bash
reverse [1,2,3]
[3,2,1]
```

take
extract x many elemts from the beginning
```bash
take 3 [1,2,3,4,5]
[1,2,3]
```

drop
removes the x last element in a list
```bash
drop 3 [1,2,3,4,5]
[3,4,5]
```

maximum
minimum
sum

product
same as sum justt multiplying instead
```bash
product [1,2,3]
6
```

elem
is theat value inside the list?
```bash
4 elem [1,2,3,4]
True
```


instad of writting out a list can do this
```bash
[1..20]
```


```bash
['a'..'z']
```

can use step
```bash
[2,4..20]
[2,4,6,8,10,12,14,16,18,20]
```

backward is weird
```bash
[20,19..1]
```

dont use *floats* in range

infinite list
```bash
take 24 [13,26..]
```
```bash
take 10 (cycle [1,2,3])
```
cycle will go on forever, so it needs to be sliced

Repeat
takes one element makes it infinite
```bash
take 3 (repeat 5)
[5,5,5]
```

### list comprehension
![[Pasted image 20250117112512.png]]
in haskell

1. selve variabel (denne kan gjøre hva som helst med. kan ganges what ever)
2. varibelen får en verdi fra selve listen
3. x antall preidkater etter det

```bash
[x*2 | x <- [1..10]]
```

```bash
<-
```
sjekker om element er i lista

får alle tallene fra 1 til 10, ganga med 2

kan legge på en betignelse
```bash
[x*2 | x <- [1..10], x*2 >= 12]
```


simpel funksjon
```bash
boomBangs xs = [if x < 10 then "boom" else "bang" | x <- xs, odd x]
```

/= this is the not equal operator

own length function
```bash
length' xs = [1 | _ <- xs]
```


tuple 
as python tuples

tuples inside a list needs to be of *same size*

fst takes first value in tuple PAIR
snd take the last value in tuple PAIR


ZIP
takes two list
pair together the same index to make a pair

can zip together a finite list with a infinite list
haskell is lazy so it cuts off
```bash
zip [1,2,3,4,5] [5,5,5,5,5]
[(1,5),(2,5),(3,5),(4,5),(5,5)]
```

# Referanse
