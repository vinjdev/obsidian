16/09/24 14:00
Fag: [[PROG2053]]
Tags: [[NTNU]]
___

# lecture 5 - Javascript 2
## asynchronous javascript
```javascript
const name = "ahmet";
const greeting = "helloe $(name)";
console.log(greeting)
```
![[Pasted image 20240916142012.png]]

this is the same

allows for program to sstart long running task without waiting for them to finish

this is to execute multiple task at once. can do one and one at a time
it wil FREEZE

asyncchronous = dont wait
syncrounous = does it sequanlally, so waits

### callbacks
function passed as argument to another function

### promises
object that handles complition of an asyncrounus task

### async / await
special keyworld
![[Pasted image 20240916142816.png]]

waits for functinn to complete
![[Pasted image 20240916142847.png]]

reponse await

### asynchronous javascript event loop
allows for asuncronous despite being single threaded



## accessing elements javascript
```javascript
document.getElementById("valu").innerHTML;
document.getElementById("valu").value;
document.getElementByTagName("p");
document.quarySelector(".menu");


```

## regular expersssion

![[Pasted image 20240916152801.png]]

check if the varibale exsist

## AJAX
load content without updating the page
asynchronous request
![[Pasted image 20240916153757.png]]

using new XMLHttpRequest()




# Referanse
