# AdoptSQLite
Repository for easy SQLite adoption. Ditch your "JSON file" and PickleDB :)

# Python Quickstart

Excellent resource: https://docs.python.org/3/library/sqlite3.html

```py
import sqlite3

db_file_name='examble.db'

con = sqlite3.connect(db_file_name) # Connects to database, which simply means opening the single file

cur = con.cursor() # Createst a Cursor object,
# which is able to execute SQL statements: https://docs.python.org/3/library/sqlite3.html#sqlite3.Cursor

cur.execute('''CREATE TABLE IF NOT EXISTS json_strings (
              id integer primary key AUTOINCREMENT,
              time_stamp datetime,
              json_string text
              );''')
# Creates a basic table consisting of automatically sequential ID, timestamp and json string column (or attribute)

cur.execute("insert into json_strings values(null,(select DATETIME("now")), ?)", your_json_string);


for row in cur.execute('SELECT * FROM json_strings'):
        print(row)

```

# Easy GUI exploration
 DBeaver https://dbeaver.io/download/
 
 or
 
 DB Browser https://sqlitebrowser.org/dl/
