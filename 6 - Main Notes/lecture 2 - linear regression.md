20/01/25 17:50
Fag: [[PROG2051]]
Tags: [[NTNU]]
___
# lecture - 2
![[Pasted image 20250120175227.png]]

## regression analysis
relationship between *dependent* variable and one or more *independent variables*

we find out which variables have impact on output
we find what factors matters the most
![[Pasted image 20250120175431.png]]

## coreelation vs regression

coreelation
finds mutual relatinship bewteen variables

predicts dependent value based at least one independent variable
![[Pasted image 20250120183246.png]]
coreelation is not effect

regression
key attributes
![[Pasted image 20250120183400.png]]
independent variables (input ) and the dependent variables output

how can we predict values with this??

![[Pasted image 20250120183513.png]]

different relationships
linear vs curves

![[Pasted image 20250120183538.png]]

![[Pasted image 20250120183545.png]]

## univariate regression or simple linear regression
![[Pasted image 20250120183650.png]]

![[Pasted image 20250120183702.png]]
this is the parameters
called *model parameters coefficients*
Bo is the avarage value of Y when X is 0

## exmample
houseing
![[Pasted image 20250120183840.png]]

Y the depent value 
X the squere meters (used to estimate price)

![[Pasted image 20250120183924.png]]
the total sum and the regression sum

total sum = regression sum + error sum

![[Pasted image 20250120184534.png]]
![[Pasted image 20250120183945.png]]

![[Pasted image 20250120184004.png]]
this is the average value of the dependt value

Yi is th real value from the REAL data

![[Pasted image 20250120184041.png]]
this is the predicted value from every xi

#### coefficient of determination (r²)
is called r squred denoted as r²
its the *portion of total variation in Y which is decided by X*

![[Pasted image 20250127154049.png]]

the value is alway between 0 and 1

Graphicaly r² values will have a perfect relationship
*WHEN r^2 = 1* 
![[Pasted image 20250127154832.png]]
100% variation in Y is explaiend by variation of X

*WHEN r² = 0*
![[Pasted image 20250127154948.png]]
some values are explained

![[Pasted image 20250127154958.png]]
when Y values is not increasing, there is no corealtion

#### standard deviation (SD)
this variation will show *vanlige AVVIK*
around the regression line
![[Pasted image 20250127205007.png]]


![[Pasted image 20250127205031.png]]
forskjellen på små og store avvik

## when does linear regression work well??
when relationship between X and Y is linear
![[Pasted image 20250127205123.png]]
#### what if bad result??
how to look for *other parameters* to incorporate in regression model
- there are other factors that decide price of house

## multvariate linrear regression
![[Pasted image 20250127205319.png]]
vs regular
![[Pasted image 20250127205504.png]]
way more parameters to be used

the degree of how polynomial the line should be is dependent on the underlying data

### loss function - make the model more accurate
![[Pasted image 20250127210214.png]]
decides how good the model is, makes a prediction with a set of parameters. Has its own curve and own gradients
- the slope of curve decides how to update the parameters to make the model more accurate

##### for multi variate regression
![[Pasted image 20250127210534.png]]
has more parameteers

##### the square difference loss
![[Pasted image 20250127210601.png]]

### Gradient descent
opimization algorithm for machine learning and deep learning algorithms

![[Pasted image 20250127210727.png]]

always check for the *minimum/maxium direction from that point*

![[Pasted image 20250127211231.png]]

## Learning rate
![[Pasted image 20250127211307.png]]

## TYPES OF REGRESSION SUMMARY
![[Pasted image 20250127211350.png]]







# Referanse
