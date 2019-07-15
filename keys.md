Describe foreign_key and primary_key. How are they useful?

Primary key : 1. a key that is unique for each record.
              2. must contain UNIQUE values, and cannot contain NULL values.
              3. a table can have only ONE primary key.


Foreign key : 1. a key used to link two tables together.
              2. refers to the PRIMARY KEY in another table.



Differences between primary and foreign keys and how they are useful. 

              1. a primary key in the original table, or parent table, can be targeted 
                 by multiple foreign keys from other “child” tables.


```
GroupTable > ID is Primary key 

ID   NAME    AGE 

1    Munira   00
2    Eman     00
3    Azzam    00
4    Khalid   00



OrdersTable  > ID is foreign key 

OrderID  OrderNumber  groupTable_ID

11       293823        1
23       230929        2
12       283743        3
08       291383        4

```