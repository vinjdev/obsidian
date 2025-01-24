14/10/24 14:16
Fag: [[PROG2053]]
Tags: [[NTNU]]
___

# lecture 9 - node.js


![[Pasted image 20241014141905.png]]

![[Pasted image 20241014142147.png]]

request / response sequence:
![[Pasted image 20241014142343.png]]


simple architecture:
![[Pasted image 20241014142441.png]]

# Node js
runs outside of web browser
compiles javascipt code - more efficent

node event loop and callback
![[Pasted image 20241014142731.png]]

threads
![[Pasted image 20241014142755.png]]

blocking
![[Pasted image 20241014142847.png]]

modules
use 
```javascript
var http = require("http")
```
to include modules

http module
create the http protocol for the website
![[Pasted image 20241014143656.png]]

simple server:
![[Pasted image 20241014143731.png]]

*fs* for reading and writing files
![[Pasted image 20241014143823.png]]

*path* module

utililty for file directory path


*url* module
for paring and manipuliating url in a application

### Making my own modules
![[Pasted image 20241014150056.png]]
export modules make them modules

### making a basic server
![[Pasted image 20241014150237.png]]
makes some standard files

import http module. then set a port and a ip address
![[Pasted image 20241014150357.png]]

![[Pasted image 20241014150503.png]]




# Referanse
