# SQL
- (Structured Query Language)
- ANSI (American National Standards Institute)
  => they all support at least the major commands (such as SELECT, UPDATE, DELETE, INSERT, WHERE)

##Using SQL in Your Web Site
To build a web site that shows data from a database, you will need:

- An RDBMS database program (i.e. MS Access, SQL Server, MySQL)

- To use a server-side scripting language, like PHP or ASP

- To use SQL to get the data you want

- To use HTML / CSS

##RDBMS

- the basis for SQL
- The data in RDBMS is stored in database objects called tables.
- A table is a collection of related data entries and it consists of columns and rows.

#SELECT
###檢視所有資料
```
SELECT * FROM table_name;
```

###檢視特定Column內資料(資料可能重複)
```
SELECT column_name1,column_name2 FROM table_name;
```

###檢視特定column內資料並過濾，data若已出現過則省略(資料不重複)
```
SELECT DISTINCT column_name1,column_name2 
FROM table_name;
```

##WHERE
###檢視 符合特定條件(DATA)的ROWS 中的所有資料
WHERE 有類似 IF 條件式的作用
```
SELECT * FROM Customers
WHERE Country='Mexico';
```
印出 Customers中 所有 Country 為 'Mexico' 之 所有row內 的資料

```
SELECT * FROM Customers
WHERE Country='Germany'
AND City='Berlin';
```
印出 Country='Germany' 且 City='Berlin' 之 所有row 內 的資料

```
SELECT * FROM Customers
WHERE City='Berlin'
OR City='München';
```
印出 Country='Germany' 或 City='München' 之 所有row 內 的資料

```
SELECT * FROM Customers
WHERE Country='Germany'
AND (City='Berlin' OR City='München');
```
印出 Country='Germany' 且 (City='Berlin'或City='München') 之 所有row 內 的資料

WHERE中 等式/不等式 語法
```
The following operators can be used in the WHERE clause:

Operator	Description
=	          Equal
<>	          Not equal. Note: In some versions of SQL this operator may be written as !=
>	          Greater than
<	          Less than
>=	          Greater than or equal
<=	          Less than or equal
BETWEEN	      Between an inclusive range
LIKE	      Search for a pattern
IN	          To specify multiple possible values for a column
AND           AND
OR            OR
```
##ORDER
###選擇特定Column為參考 依字母排序row 並呈現資料
```
SELECT * FROM Customers
ORDER BY Country;
```
印出 以country為基準 依字母所排序 之 所有row 內 的資料 (預設為升冪排序a~z)

```
SELECT * FROM Customers
ORDER BY Country DESC;
```
印出 以country為基準 依字母所排序 之 所有row 內 的資料 (降冪排序z~a)
DESC 指降冪 DESCENDING

- 綜合應用
```
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```
印出 以country為基準 依字母升冪排序 之 所有row 內 的資料
同時在country為相同資料時，以customerName為基準 依字母降冪排序 之 所有row內 的資料

#INSERT INTO
