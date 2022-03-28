# SQL Syntax differences
List of differences between different SQL syntaxes like (Redshift, BigQuery, Presto, etc.)

## Date functions

Epoch to timestamp

``` sql 
-- BigQuery
TIMESTAMP_SECONDS(field)

-- Presto 
from_unixtime(field) 

-- Redshift
timestamp 'epoch' + field * interval '1 second' 

-- Snowflake
to_timestamp(field)
``` 

Convert timezone

``` sql 
-- Presto 
at_timezone(field,to_timezone) 

-- Redshift
convert_timezone(to_timezone,field) 
``` 

DATEADD() function

``` sql 
-- Presto 
date_add('datepart',interval,field)

-- Redshift
dateadd(datepart, interval,field) 
``` 



## JSON functions

Extract text from JSON

``` sql 
-- Presto 
JSON_EXTRACT_SCALAR(field, '$["path"]')

-- Redshift
JSON_EXTRACT_PATH_TEXT(field, 'path')
``` 
