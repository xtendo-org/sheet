## Command line

```sh
createuser -d -s -r
```

- `-d`: user can create database
- `-s`: user is superuser
- `-r`: user can create roles

```sql
ALTER TABLE "article" ADD COLUMN "password" character varying(80) NULL;
```

`psql`:

- `\l`: list all databases
- `\dt`: list all tables in the current database
- `\connect dbname`: switch database
- `\d+ tablename`: describe the table schema

## List databases

```sql
SELECT datname FROM pg_database
WHERE datistemplate = false;
```

### List tables in the current database

```sql
SELECT table_schema,table_name
FROM information_schema.tables
ORDER BY table_schema,table_name;
```

## Dump

- dump: `pg_dump -d dbname -f filename.dump`
- undump: `pg_restore -d dbname -j 8 filename.dump` (`-j`: number of concurrent jobs)

## Set password

```sql
ALTER ROLE psusername WITH PASSWORD 'password';
```

## `INSERT` with `RETURNING`

```sql
INSERT INTO tablename (column1, column2) VALUES ('Smith', 'John') RETURNING id;
```

## `ALTER COLUMN`

Remove the `NOT NULL` constraint:

```sql
ALTER TABLE person ALTER COLUMN phone DROP NOT NULL;
```

Change column name:

```sql
ALTER TABLE <tablename> RENAME <oldcolumn> TO <newcolumn>;
```

Change column type:

```sql
ALTER TABLE <tablename> ALTER COLUMN <columnname> TYPE <newtype>;
```
