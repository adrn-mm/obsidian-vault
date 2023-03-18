#SQL #DataEngineering 
# SQL
## Basic Commands
- `SELECT`
- `INSERT`
- `UPDATE`
- `DELETE`
r
# TSQL
Transact-SQL is an extension version of SQL from Microsoft SQL Server. TSQL has several command types:
- DDL (Data Definition Language)
	Database's scheme and description. The commands are `CREATE`, `ALTER`, `DROP`.
- DML (Data Manipulation Language)
	To query and manipulate the data. The commands are `SELECT`, `INSERT`, `UPDATE`.
- DCL (Data Control Language)
	About user access permission to the database. The commands are `GRANT`, `REVOKE`.

## Schema & Why We Need to Normalize the Database First
Most of the time, our data is from multiple tables. Also, we often query the data from more than one table, so the first thing we do as data engineers is normalize the data to transform these tables into only one table. The critical thing is to choose the right name for each table in the schema.

## Transaction Control
- asynchronous process $\rightarrow$ success and failed process in one system
- the concept
![[transaction control concept 2023-02-09 22.00.04.excalidraw]]
- implementation
	- Batch processing $\rightarrow$ relational data in tables in one or multiple databases
	- Distributed Transaction $\rightarrow$ relational data in different server databases.
- ACID properties
	- atomicity $\rightarrow$ groups of separate process is one process
	- consistency $\rightarrow$ if process is failed, the transaction results don't change the database
	- isolation $\rightarrow$ each transaction has their own limit and area
	- durability $\rightarrow$ if the transaction is success, the results are going to be saved and processed in the database.
- Statements
	- `BEGIN TRANSACTION` $\rightarrow$ transaction started
	- `COMMIT` $\rightarrow$ change in transaction
	- `ROLLBACK` $\rightarrow$ failed transaction.
````ad-example
```sql
BEGIN TRANSACTION
--- add data
INSERT INTO (personid, name, company)
VALUES(001, 'adrian', 'IYKRA')

--- set error code if error happened whed data was added
SET @inserr = @@error
IF @inserr > @maxerr
SET @maxerr = @inserr

--- if error happened then transaction is aborted
IF @maxerr <> 0
BEGIN ROLLBACK
PRINT 'Transaction rolled back'
END
ELSE
BEGIN COMMIT
PRINT 'Transaction commited'
END
```
````

# TSQL Functions
## Aggregate Functions
Do the calculations on several values and then return a value.
- `SUM`
- `AVG`
- `COUNT`
- `MIN`
- `MAX`

## Scalar Functions
To return a singular value from the input values. 
- `LCASE`  $\Rightarrow$ to lowercase
- `UCASE` $\Rightarrow$ to uppercase
- `LEN` $\Rightarrow$ length from the string input
- `MID` $\Rightarrow$ extracting substring
- `ROUND` $\Rightarrow$ rounded to the decimal value

```ad-note
Bagian yang ini yang belum familiar adalah yang tentang `procedure`
```