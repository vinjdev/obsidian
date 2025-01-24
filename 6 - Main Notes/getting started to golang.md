13/01/25 15:44
Fag: [[PROG2005]]
Tags: [[NTNU]]
___
# getting started to golang

go mod init example/hello

- makes a simple boilerplate

makes a enviroment for tracking dependencies
handle all imported packages in own code module
- make ur own folder for it




simpelt script
```go
package main

import "fmt"

func main() {
    fmt.Println("hello world");
}
```

```bash
go build main.go && ./main
go run main.go
```


![[Pasted image 20250115094842.png]]

go mod edit -replace theOldRoute= the new route from here
go mod tidy (this will clean up depencenceis in go.mod and go.sum file)


map
map[key]value
key - verdien som skal sammenlignes
value - er hva som skal hentes ut

go build and go install

go build (creates an executable)

go install makes it possible to run the executble 


for å importe andre filer. så må man først ha go.mod filen.
å når man kaller så må man definere routene fra en example nettsiden



# Referanse
