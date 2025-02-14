29/01/25 14:06
Fag: [[IDATG2204]]
Tags: [[NTNU]]
___
# oblig 1 - sql and relational algebra

query = request of information
## Part 1 - algebra queries
### q1
π Loan.loan_number(σ(Loan.loan_amount<20000(Loan)) 
### q2
π customer.name, customer.email,customer.City, customer.Mobile_Phone,Branch.Name(Customer⨝Branch.City = Branch.City (Branch))

### q3
![[Pasted image 20250203155644.png]]

Depositor.Account_number SUM(Depositor.Amount) (Depositor)
### q4
Retrieve all the customers having their account in “active” state and balance more than
$10000

π Account.Customer_id(σ(Account.Status = 'Active' AND Account.Balance > 10000) (Account))


## Part 2 SQL queries
### q1
```bash
SELECT * FROM customer WHERE NOT (city = 'Gjøvik');
```

### q2
```bash
SELECT * FROM customer WHERE email LIKE '%.no';
```

### q3
```bash
SELECT * FROM loans WHERE loan_period = 3;

eller

SELECT customer.name, loan.*
FROM loan 
JOIN customer ON customer.customer_id = loan.customer_id
WHERE loan_period = 3;
```

### q4
```bash
SELECT customer.*
FROM customer 
LEFT JOIN loan ON customer.customer_id = loan.customer_id
WHERE loan.customer_id IS NULL;
```

### q5
```bash
SELECT *
FROM customer
ORDER by birth_date DESC
LIMIT 3;
```

### q6
```bash
SELECT account_number, COUNT(transaction_id) as total_transactions, SUM(amount) as total_sum 
FROM depositor
WHERE date >= '2020-01-01' AND date < '2021-01-01'
GROUP BY account_number;
```

### q7
```bash
INSERT INTO customer(name,customer_id,gender,birth_date,city,address,postal_code,home_phone,mobile_phone,email)
values('Ryan Ishus', 10016,'M','1991-01-10','Trondheim','Bakkegata 15',7049,75432103,45464783,'ryan00@realmail.no');

INSERT INTO account(Account_number,Customer_id,Branch_code,Balance,Opening_date,Status)
values('acc1001',10016,'b2',1000,'2021-01-18','Inactive');
```

### q8
```bash
UPDATE account
SET Status = 'Active'
WHERE customer_id = 10016;
```

### q9
```bash
DELETE FROM loan
WHERE loan_periode IS NULL;
```


# Referanse
