## Review

- Some review::
  - `*`
  - Order by
  - Limit
  - sum(), count(), etc...
  - Like
  - Comparison operators
  - IS / IS NOT NULL
  - IN()
  - INSERT INTO
  - DELETE 
      ````
      DELETE FROM <Table name>
      WHERE <condition>;
      ```
    - Always do a select first
  - `UPDATE <table name> SET <column name> = <new value>`
  - DISTINCT

## ALTER TABLE

- Changes the schema of the table

### Adding columns
```
ALTER TABLE <table name>
ADD COLUMN <column name> <data type>
```
- with foreign key -
```
ALTER TABLE <table name>
ADD COLUMN <column name> <data type> REFERENCES <other table name> [(<primary key column name></primary>)]
```
```
ALTER TABLE <table name>
ADD COLUMN <column name> <data type> 
ADD FOREIGN KEY <column name> REFERENCES <other table name> [(<primary key column name></primary>)]
```

### Alter column data types
```
ALTER TABLE <table name>
ALTER COLUMN <column name>
SET DATA TYPE <data type>
```
- or -
```
ALTER TABLE <table name>
ALTER <column name>
SET DATA TYPE <data type>
```
- or -
```
ALTER TABLE <table name>
ALTER <column name>
TYPE <data type>
```

### Renaming columns
```
ALTER TABLE <table name>
RENAME COLUMN <column name>
TO <new column name>
```
### Drop columns
```
ALTER TABLE <table name>
DROP COLUMN <column name>
```
### Rename table name
```
ALTER TABLE <table name>
RENAME TO <new table name>
```
### Drop table

`DROP TABLE [IF EXISTS] <table name>;`

## RELATIONSHIPS
- one to many relationship
- parent to child relationship
```
CREATE TABLE <table name> (
  <column name> <data type> <constraints>
  <foreign key column name> <data type> REFERENCES <other table name> [(<primary key column name>)]
);
```

### JOINS
```
SELECT <columns that we want to select>
FROM <table 1>
JOIN <table 2> ON <primary key> = <foreign key>;
```
### Nested Subqueries
```
SELECT <column names that we want to select>
FROM <table 1>
WHERE <primary key or something else> IN (<new select statement with table 2 that will result in the foreign key or something else>)
```
```
SELECT <column names that we want to select>
FROM <table 1>
WHERE <query to match> IN (<new select statement with table 2 matches query to match>)
```
### Group By

- with Select statements --- any ungrouped column needs to be with an aggregate function
- will group any values that are the same from the grouped column
```
SELECT <grouped column name>, <any column ungrouped needs to be with an aggregate function>
FROM <table name>
GROUP BY <column name being grouped>
```

### Aliasing
- Use AS or not, either works
