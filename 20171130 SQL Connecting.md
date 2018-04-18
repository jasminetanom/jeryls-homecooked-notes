# Django and flask
web framework for python to websites

# Interacting with SQLite

There are multiple ways of interacting with a SQLite database, including:

    SQLite command line utility
    Python's sqlite3 package
    pandas' SQL Interface
    High-level ORMs (e.g., SQLAlchemy, Django ORM, etc.) object relational mappers

# Commands
CREATE TABLE ...
ALTER TABLE ... ADD COLUMN ...
INSERT INTO ... VALUES ...
UPDATE ... SET ... WHERE ...
SELECT ... FROM ... WHERE ...
SELECT ... FROM ... JOIN ... ON ... > relational
DELETE FROM ... WHERE ..

# iniatiting db (SQLite)
1. ANA prompt
*TABLE*
2. sqlite3 test1.sqlite
3. CREATE TABLE table1 (field1 INTEGER PRIMARY KEY);
4. ALTER TABLE table1 ADD COLUMN field2 VARCHAR(16);
5. ALTER TABLE table1 ADD COLUMN field3 REAL;
6. ALTER TABLE table1 ADD COLUMN field4 TEXT;
7. .schema shows create statement that shows table creation
table name, field, dtypes etc

> [3-6] CREATE TABLE table1 (field1 INTEGER PRIMARY KEY, field2 VARCHAR(16), field3 REAL, field4 TEXT); also can

*DATA*
1. INSERT INTO table1 VALUES (1, 'Henry James', 42, '75 Mission Street, San Francisco, CA');
2. INSERT INTO table1 VALUES (2, 'Carol James', 40, '75 Mission Street, San Francisco, CA');
3. INSERT INTO table1 VALUES (3, 'Jesse James', 12, '75 Mission Street, San Francisco, CA');
INSERT INTO table1 VALUES (*NULL*, 'Julie James', 10, '75 Mission Street, San Francisco, CA');
null increments PK value

# Connecting to remote database
cd to C:\Program Files\PostgreSQL\10\bin

psql -h dsi.c20gkj5cvu3l.us-east-1.rds.amazonaws.com -p 5432 -U dsi_student titanic

# create db using sqlite3
import sqlite3
sqlite_db = './datasets/test_db.sqlite'
conn = sqlite3.connect(sqlite_db) 
c = conn.cursor()

# create tables
c.execute('CREATE TABLE houses (field1 INTEGER PRIMARY KEY, sqft INTEGER, bdrms INTEGER, age INTEGER, price INTEGER);')

## Save (commit) the changes.
conn.commit()a

# Add data
last_sale = (None, 4000, 5, 22, 619000)
c.execute('INSERT INTO houses VALUES (?,?,?,?,?)', last_sale)

### Remember to commit the changes.
conn.commit()

# execute many
recent_sales = [
  (None, 2390, 4, 34, 319000),
  (None, 1870, 3, 14, 289000),
  (None, 1505, 3, 90, 269000),
]

c.executemany('INSERT INTO houses VALUES (?, ?, ?, ?, ?)', recent_sales)

conn.commit()

# Add from csv

from numpy import genfromtxt

## import into nparray of ints, then convert to list of lists
data = (genfromtxt('datasets/housing-data.csv', dtype='i8', 
                    delimiter=',', skip_header=1)).tolist()

## append a None value to beginning of each sub-list
for d in data:
    d.insert(0, None)

## Loop through data, running an INSERT on each record (i.e., sublist).
for d in data:
    c.execute('INSERT INTO houses VALUES (?, ?, ?, ?, ?)', d)

conn.commit()


## Similar syntax as before.
results = c.execute("SELECT * FROM houses WHERE bdrms = 4")

## Here, results is a cursor object — use `.fetchall()` to extract a list.
results.fetchall()


# Pandas
data.to_sql('houses_pandas',             # Name of the table.
            con=conn,                    # The handle to the file that is set up.
            if_exists='replace',         # Overwrite, append, or fail.
            index=False)                 # Add index as column.

df = pd.read_sql('SELECT * FROM houses_pandas LIMIT 10', con=conn)

# aggregate functions
SELECT COUNT(price)
FROM houses_pandas;

SELECT AVG(sqft), MIN(price), MAX(price)
FROM houses_pandas
WHERE bdrms = 2;

# ORDER BY
SELECT column_name1, column_name2  
FROM table_name  
ORDER BY column_name1 ASC, column_name2 DESC;


# Joins using panadas
pd.merge(df_a, df_b, on='col', how='inner / outer / left / righ'tjoi) 

# Pivot tables
pd.pivot_table(df,
			columns=['variable'],
			values='value',
			index=['subject_id'],
			aggfunc=select_item_or nan,
			fill_value=np.nan)

# QUery using SQL
sql = """
SELECT "CategoryID", COUNT(\*) AS "Products Per Category"
FROM products
WHERE "Discontinued" != 1
GROUP BY "CategoryID"
ORDER BY "Products Per Category" DESC
"""

pd.read_sql(sql, con=engine)

sql = """
SELECT 
    o."OrderID", o."CustomerID", od."UnitPrice" * od."Quantity" AS "net_order"
FROM orders o
LEFT JOIN order_details od 
ON 
    o."OrderID" = od."OrderID"

ORDER BY 3 DESC
LIMIT 1
"""
pd.read_sql(sql, con=engine)