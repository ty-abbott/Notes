'''
# Import module 
import sqlite3 

# Connecting to sqlite 
conn = sqlite3.connect('geek.db') 

# Creating a cursor object using the 
# cursor() method 
cursor = conn.cursor() 

# Creating table 
table ="""CREATE TABLE STUDENT(NAME VARCHAR(255), CLASS VARCHAR(255), 
SECTION VARCHAR(255));"""
cursor.execute(table) 

# Queries to INSERT records. 
cursor.execute( 
'''INSERT INTO STUDENT (CLASS, SECTION, NAME) VALUES ('7th', 'A', 'Raju')''') 

cursor.execute( 
'''INSERT INTO STUDENT (SECTION, NAME, CLASS) VALUES ('B', 'Shyam', '8th')''') 

cursor.execute( 
'''INSERT INTO STUDENT (NAME, CLASS, SECTION ) VALUES ('Baburao', '9th', 'C')''') 

# Display data inserted 
print("Data Inserted in the table: ") 
data=cursor.execute('''SELECT * FROM STUDENT''') 
for row in data: 
	print(row) 

# Commit your changes in 
# the database	 
conn.commit() 

# Closing the connection 
conn.close()
'''

It is also really critical to make the values to add a tuple for example 

'''
statement = '''INSERT into tasks (description) VALUES (?)'''

cursor.execute(statement, (value,))
