24/01/25 08:34
Fag: [[IDATG2204]]
Tags: [[NTNU]]
___
# week 4 - SQL

run: lampp start
sudo /opt/lampp/lampp start

HUSK Å KJØR start_mysqlAndMariaDB.sh eller stop
utifra om jeg skal ha adminboard eller terminal

```bash
sudo systemctl stop mariadb
sudo systemctl stop mysql

sudo systemctl start mariadb
sudo systemctl start mysql
```


adminboard:
http://localhost
http://localhost/phpmyadmin


troubleshoot
```bash
sudo tail -f /opt/lampp/logs/error_log
```

sql
sudo /opt/lampp/bin/mysql -u root

## make database
choose the danish UTF
then create

## intro SQL and select
sql is a declarative language
- describes what the result should be

sql select statements have a fixed structure

*select and from are mandatory*
can set condition
may want to *group* (can be condition on groups)
set order

*SELECT * FROM define what table to quary*

use car.* 
- this selects the car table with all attribute, good for multiple tables

![[Pasted image 20250205130537.png]]




# Referanse
