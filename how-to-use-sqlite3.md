# How to use sqlite3?

This is the basics of sqlite3.

```
# create a db
sqlite3 test.db

# list db
.databases

# create a table
CREATE TABLE items(id int, size int);

# list table
.tables

# describe table
.schema items

# insert
INSERT INTO items VALUES(0, 10);
INSERT INTO items VALUES(1, 20);

# turn on table header
.headers on

# check the settings
.show

# select
SELECT * FROM items;

# delete
DELETE FROM items WHERE id=0;

# update
UPDATE items SET size=200 WHERE id=1;

# quit
.quit
.exit

# dump the db
sqlite3 test.db .dump > test.sql

# open the db again
sqlite3 test.db

# drop table
DROP TABLE items;Í

# check the table
.tables

# quit again
.quit

# restore the db
sqlite3 test.db < test.sql
```
