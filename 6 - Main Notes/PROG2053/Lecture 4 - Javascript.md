jk09/09/24 16:10
Fag: [[PROG2053]]
Tags: [[NTNU]]
___

# Lecture 4 - Javascript
javascript - no need to compile, runs one anything with a  

can be inserted anywhere into html

![[Pasted image 20240909162624.png]]


javascript has 8 datatypes
![[Pasted image 20240909163739.png]]

javascipt types are *DYNAMIC*

## arithmetic

![[Pasted image 20240909164028.png]]

## assignment
![[Pasted image 20240909164051.png]]

## comparison
![[Pasted image 20240909164130.png]]

## ???
![[Pasted image 20240909164147.png]]


## logical and type
![[Pasted image 20240909164302.png]]

![[Pasted image 20240909164308.png]]


## control flow
![[Pasted image 20240909164543.png]]
c style

## switch
![[Pasted image 20240909164851.png]]


## loops
![[Pasted image 20240909165028.png]]

instead of the type (int etc..). use let

## functions
![[Pasted image 20240909165122.png]]

## ARROW FUNCTION - unique to javascript
![[Pasted image 20240909165502.png]]

## Arrays 
![[Pasted image 20240909180058.png]]

list can grow and shrink in size

![[Pasted image 20240909182436.png]]

can remove and add like python

### methodes on arrays
![[Pasted image 20240909182517.png]]

![[Pasted image 20240909182552.png]]

## matrix
![[Pasted image 20240909183031.png]]


## objects (struct, but data is defined, no blueprint)

![[Pasted image 20240909183048.png]]

almost everything is an object

![[Pasted image 20240909183155.png]]
two ways to make an object

![[Pasted image 20240909183235.png]]

![[Pasted image 20240909183247.png]]
objects also have constructors

## accesing properites with objects
![[Pasted image 20240909183625.png]]

```javascript
const person {
age: 50
}

person["age"]
// will access age

```

![[Pasted image 20240909184009.png]]

Functions(methodes) are defined different in objects

```javascript
console.log(person.fullname) // retkurns definition
console.log(person.fullname()) // exec function
```

## getters and setters
![[Pasted image 20240909184235.png]]

![[Pasted image 20240909184730.png]]

*access as a property* and not as an function
set is for changing a property in object

getters are a return value

![[Pasted image 20240909184933.png]]

Cannot add a property from outside definition

## display 
![[Pasted image 20240909185025.png]]

can make it a list with keys and values

## destrcuturing
for exctracting values to variables

![[Pasted image 20240909185145.png]]

```javascript
const { name,age,email } = person
// object with all those properties
// can be made into 3 disting variabbles
```

## reference not value
*copying an object* to a vaiable *WILL change* the main object

![[Pasted image 20240909185254.png]]

## Classes
object for simple data structures
classes for reusable components

![[Pasted image 20240909185511.png]]


```javascript
class Person {

	constructor(name,age) {
		this.name = name;
		this.age = age;
	}
	greet() {
		console.log("$(this.name) is $(this.age) years old.");
	}
}

// always use NEW to make a class
const person1 = new Person("jon", 30);
person1.greet();

```
## inheritence
![[Pasted image 20240909185750.png]]

use of *extend* keyword

methodes with same name, will be overwritten

## static methodes
![[Pasted image 20240909185930.png]]

helper functions






# Referanse
