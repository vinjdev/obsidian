03/02/25 09:27
Fag: [[PROG2051]]
Tags: [[NTNU]]
___
# lecture 4 - Suppport Vector Machines

## Outline
![[Pasted image 20250203093241.png]]

## What are support vector machines
supervised machine learning algorithms for
- regrssion tasks
- classifications - prediect a cateory or class

- effective in high dimenional spaces
- where dimensions is grater than number of samples
- good in traning stage

## Linear Machine
regular function for linear function is machine learning
Y = mx + c
m is slope and c is intercept

regular functions for generic equation
ax + by + c = 0
a = 0 line is horizontal
b = 0 line is vertical


## Decision boundry
for different configuration of parameters, there exists infinite solutions

SVM - will always look for the *optimal* solutions
- max the distance between line or plane or hyperplane
- if no points near decisions boundary, certain classification decision
	- *ONE INTUITION*

key attributes
![[Pasted image 20250203105927.png]]


### concept of margin
its a lineaar classefier
- its thickier, will be thicker until it hits one of the two datapoints
![[Pasted image 20250203112521.png]]

support vectors are the datapoint the margin is pushing against

![[Pasted image 20250203112700.png]]

*the simples kind of SVM*

## linear classifer
seperate classes in the feature space

either bigger than 0 or less then
- 1 or 0

![[Pasted image 20250203112816.png]]

## 3 important facts
w is perpendicualr to the line

distance from point to a line 1 / length of w

distance bewteen lines margin 2 / length of w

### w perpendiucalrity
![[Pasted image 20250203113400.png]]

## linear svm mathematically - not important, as math is very heavy

try to classify all the traning data
![[Pasted image 20250203114025.png]]

![[Pasted image 20250203114034.png]]




# Referanse
