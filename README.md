# mysql_joins_tables

SELECT 
    CONSTRAINT_SCHEMA as 'Database',
    CONSTRAINT_NAME,
    TABLE_SCHEMA,
    TABLE_NAME,    
    REFERENCED_TABLE_NAME,
    COLUMN_NAME,
    REFERENCED_COLUMN_NAME
FROM
    information_schema.key_column_usage
WHERE
    constraint_schema not in('sakila','sys','world')
        AND column_name = column_name
        and referenced_table_name is not null
        order by table_name asc;
