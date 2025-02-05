17/01/25 11:50
Fag: [[PROG2006]]
Tags: [[NTNU]]
___
# types and type classes

# belive the type

haskell type system dont need to explicilty type
its polymorphic, need to explicitly tell to constrian a function


```bash
:t 
```

will show the type in ghci
![[Pasted image 20250124102557.png]]

works on functions too
![[Pasted image 20250124102917.png]]
this means that function take in list of char, and outputs a list of char

multiparameter function
![[Pasted image 20250124103106.png]]
takes in any type a, which is a *instance of Num typeclass*
everything is input except the last one

#### int
whole numbers

#### integers
also whole numbers just bigger
![[Pasted image 20250124104447.png]]

#### tuples
usees ()

### type variables
![[Pasted image 20250124104707.png]]
a can be whatever type

### typeclasses
everything before => is a *class constraint*

![[Pasted image 20250124105344.png]]
need two values in == 
they are members of the Eq class

all haskall standard types are part of Eq typeclass
- except IO

#### Eq
equlity check
![[Pasted image 20250124110011.png]]

#### Ord
for values that are greater or less than
LT or GT

![[Pasted image 20250124110056.png]]

*Ordering* is its own TYPE
- LT, GT or EQ

#### show
present values as string

#### read
takes string and returns a type

![[Pasted image 20250124110337.png]]

it will crash if it doesnt know what to return
need a *function* or to be part of *class constraint*
or can give it a *type manually*

![[Pasted image 20250124110714.png]]

since haskell is *statically typed*

#### enum
sequentially ordered types
![[Pasted image 20250124111023.png]]

#### Bounded
members of bounded class have a max bound and a min bound
![[Pasted image 20250124111143.png]]

#### Num
members of Num properties to act like numbers
![[Pasted image 20250124111331.png]]

this is way    Int * Interger   works

Everything in Num MUST be friends with *Show and Eq*

#### Integral
is also its own typeclass

#### floating
float and Double



# Referanse
