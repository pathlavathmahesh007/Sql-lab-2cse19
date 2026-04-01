# MESS Table
```sql

CREATE TABLE MESS (
    Mess_ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Type VARCHAR(30),
    Charge DECIMAL(10,2),
    Timing VARCHAR(30)
);
```


---

## Student

```sql
3️⃣ STUDENT Table

CREATE TABLE STUDENT (
    Student_ID INT PRIMARY KEY,
    Name VARCHAR(50),
    Roll_No VARCHAR(20),
    Phone VARCHAR(15),
    Hostel_ID INT,
    Mess_ID INT,
    FOREIGN KEY (Hostel_ID) REFERENCES HOSTEL(Hostel_ID),
    FOREIGN KEY (Mess_ID) REFERENCES MESS(Mess_ID)
);
```

---
## Bill

```sql
4️⃣ BILL Table
CREATE TABLE BILL (
    Bill_ID INT PRIMARY KEY,
    Date DATE,
    Amount DECIMAL(10,2),
    Status VARCHAR(20),
    Student_ID INT,
    FOREIGN KEY (Student_ID) REFERENCES STUDENT(Student_ID)
);
```

---

## Transaction

5️⃣ TRANSACTION Table
```sql
CREATE TABLE TRANSACTION (
    Trans_ID INT PRIMARY KEY,
    Date DATE,
    Mode VARCHAR(20),
    Amount DECIMAL(10,2),
    Bill_ID INT,
    FOREIGN KEY (Bill_ID) REFERENCES BILL(Bill_ID)
);
```