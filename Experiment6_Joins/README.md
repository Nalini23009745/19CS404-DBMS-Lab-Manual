# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**

![image](https://github.com/user-attachments/assets/73e635ff-0503-48e2-a13c-f5c35255ec5f)

```
SELECT c.cust_name
FROM customer AS c
LEFT JOIN orders AS o ON c.customer_id = o.customer_id;
```
**Output:**

![image](https://github.com/user-attachments/assets/51943d92-8bfd-4e63-a193-dd2abc6762c3)


**Question 2**
---
![image](https://github.com/user-attachments/assets/d74cb230-a010-4ac0-a9ad-ffb09685c8fe)

```
SELECT o.ord_no, o.purch_amt, o.ord_date, c.cust_name, c.city AS customer_city, c.grade, s.name AS salesman_name, s.city AS salesman_city, s.commission
FROM orders AS o
JOIN customer AS c ON o.customer_id = c.customer_id
JOIN salesman AS s ON o.salesman_id = s.salesman_id;
```
**Output:**

![image](https://github.com/user-attachments/assets/1eee2cc6-8bca-41b7-a6da-885f168dc876)


**Question 3**
---
![image](https://github.com/user-attachments/assets/7e77e3df-2ef8-43e3-ac2f-2aef8fe6b5eb)

```
SELECT s.name AS "Salesman", c.cust_name, c.city
FROM salesman s, customer c
WHERE s.city = c.city;
```

**Output:**

![image](https://github.com/user-attachments/assets/269e6828-fb1e-4655-bcc8-83c35bfc3023)


**Question 4**
---
![image](https://github.com/user-attachments/assets/5b59f74d-47fe-436e-9cbe-a743a49672bd)

```
SELECT p.first_name AS patient_name
FROM patients p
INNER JOIN test_results t ON p.patient_id = t.patient_id
WHERE t.test_name = 'Blood Pressure';
```
**Output:**

![image](https://github.com/user-attachments/assets/c7124b7f-c30d-4073-a77c-c8b7f1b9bd8c)


**Question 5**
---
![image](https://github.com/user-attachments/assets/706c79a1-5694-45d2-8528-2bb9347c93f5)

```
SELECT c.cust_name AS 'Customer Name', c.city, s.name AS Salesman, s.commission
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id;
```
**Output:**

![image](https://github.com/user-attachments/assets/a6c42171-688b-4c59-a566-96c09943e019)


**Question 6**
---
![image](https://github.com/user-attachments/assets/fdb3529a-de31-436a-bf7f-a7dd7cd5fb42)

```
SELECT p.patient_id, p.first_name, p.last_name, p.date_of_birth, p.admission_date, p.discharge_date, 
       p.doctor_id, d.first_name AS doctor_name
FROM patients p
JOIN doctors d ON p.doctor_id = d.doctor_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/792483a4-66ff-49ce-bbf0-0a7a45009d0e)


**Question 7**
---
![image](https://github.com/user-attachments/assets/fc84b5dd-cc66-4692-b876-1a8c223ad921)

```
SELECT p.first_name AS patient_name, d.specialization AS Doctor_speciali
FROM PATIENTS p
JOIN DOCTORS d ON p.doctor_id=d.doctor_id
WHERE p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```
**Output:**

![image](https://github.com/user-attachments/assets/9496e434-b7c2-43b8-ba2c-f5c5f0c420d1)


**Question 8**
---
![image](https://github.com/user-attachments/assets/68d002ed-11a0-4f05-b5e9-c596c20f0a6c)
```
SELECT c.cust_name AS 'Customer Name', c.city, s.name AS Salesman, s.city, S.commission
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
WHERE c.city!=s.city AND s.commission>0.12;
```
**Output:**

![image](https://github.com/user-attachments/assets/6ef07fc3-0dae-4999-bf79-646622caab8a)


**Question 9**
---
![image](https://github.com/user-attachments/assets/28d76ac5-8abe-4400-917e-6d069a81b53b)

```
SELECT c.*
FROM CUSTOMER c
LEFT JOIN ORDERS o ON c.customer_id=o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';
```

**Output:**

![image](https://github.com/user-attachments/assets/39d22726-8f00-4b11-9945-e9b3eed75752)


**Question 10**
---
![image](https://github.com/user-attachments/assets/5594a303-1fa9-4640-90c7-32b093ac973c)

```
SELECT o.ord_no, o.ord_date, o.purch_amt, c.cust_name AS 'Customer Name', c.grade, s.name AS Salesman, s.commission
FROM orders o
JOIN customer c ON o.customer_id=c.customer_id 
JOIN salesman s ON c.salesman_id=s.salesman_id;
```
**Output:**

![image](https://github.com/user-attachments/assets/0f5d53e7-2ee1-43b0-9341-354d8b89b310)




## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
