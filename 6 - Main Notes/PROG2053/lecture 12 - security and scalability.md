19/12/24 15:00
Fag: [[PROG2053]]
Tags: [[NTNU]]
___
# lecture 12 - security and scalability

## why security matters
ensure 

### implications
data theft 

loss of thrust

financial loss

compilance violations

busniess continuity

### commons attacks
SQL injections
cross site scripting
denial of service attacks
session hijacking
broken authentication and session managment
cross site request forgery

## secruity best practices in node js
envirotment management

dependency management

## envirment managment
development
testing staging
production

dotenv

![[Pasted image 20241219152343.png]]

## express security essentials


### Helmet

Helmet is middleware for node.js help with HTTP headers

these headers protect you application against common web vuleranbilities

using helmet

### conf helmet




### rate limiting
controls the number of request a client can make to a server

benefits DDoS protections and brute force protections and resource conservation

### using rate limiting

![[Pasted image 20241219153512.png]]

### sanitizing inputs
prevents malicious code form exeuting on the server or client

### session mangement
session 
cookies

secure flag
httponly flag
samesite flag
secret key

cookie expiry
rolling session

### cross origin resource sharing



# Referanse
