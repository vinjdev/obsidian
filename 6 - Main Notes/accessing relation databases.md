29/01/25 09:40
Fag: [[PROG2005]]
Tags: [[NTNU]]
___
# accessing relation databases

first setup a database

```bash
sudo mysql -u root
```

here make a database
and load a sql file into it

```bash
create database name_of_db
use name_of_db
source path
```

go get .
will import all the modules inside the go file automaticlay

in sql
```bash
select * from name_of_db_in_sql
```
![[Pasted image 20250129094557.png]]

```go
```
var db *sql.DB

func main() {
    // Capture connection properties.
    cfg := mysql.Config{
        User:   os.Getenv("DBUSER"),
        Passwd: os.Getenv("DBPASS"),
        Net:    "tcp",
        Addr:   "127.0.0.1:3306",
        DBName: "recordings",
    }
    // Get a database handle.
    var err error
    db, err = sql.Open("mysql", cfg.FormatDSN())
    if err != nil {
        log.Fatal(err)
    }
    pingErr := db.Ping()
    if pingErr != nil {
        log.Fatal(pingErr)
    }
    fmt.Println("Connected!")
}
```
```

```go
```

import (
    "database/sql"
    "fmt"
    "log"
    "os"
    "github.com/go-sql-driver/mysql"
)
```
```

really simple getting started script

need those imports, remember do: go get .

### IMPORTANT TO SET PERMISSION
*i get an error on arch here:*
i need to set DBUSER to be something
```bash
export DBUSER=some_name
export DBPASS=some_passw
```

then login into sql
grant permission
flush to apply

```bash
mysql -u root -p
GRANT ALL PRIVILEGES ON recordings.* TO 'some_name'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```





# Referanse
