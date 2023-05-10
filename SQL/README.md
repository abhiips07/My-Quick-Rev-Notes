> Note: Mainly syntax of MySQL

## Important Points
- SQL keywords are NOT case sensitive: `select` is the same as `SELECT`
- Column Name with space [Contact Person]
- SQL requires single quotes around text values (most database systems will also allow double quotes). However, numeric fields should not be enclosed in quotes
- We will have to use the `IS NULL` and `IS NOT NULL` operators for null comparison
- Input DATE as #07/01/1996# or '1996-07-01'
- Group or aggregate functions should not be combined to single values or functions or ERROR is raised
- Single `=` is used for equalTo and `<>` or `!=` for not equalTO
- > Order of writing: `SELECT > WHERE > GROUP BY > Group by FUNCTIONS > HAVING > ORFER BY`


### Comments
```MySQL
--single line
/* Multiline */
```
