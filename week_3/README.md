Week 3
======

Data comes in many flavors (so to speak) and how that data is structured
often relates to the amount of information the data contains. We will be
working primarily with structured data, that is to say we will be
working with data that has a high degree of organization. Structured
data is great to work with because it is easy to query, search over,
aggregate, etc. A good example of structured data is a table in Excel.

1 - Data Management
-------------------

### Tables

A data table is essentially an unordered list that contains columns
(attributes) and rows. A column represents a typed data entry (e.g.,
integer, double, character, datetime). A row (record) is a single entry
in the table that has various columns (attributes). You will often hear
us use the term ‘schema’, which basically outlines the table name, its
attributes, and their data types. We will walk thru these concepts using
a subset of the TE\_DIVE data table (the data you’ll be using), as shown
below.

    ## # A tibble: 264,622 x 6
    ##    REF       NEWPTT DS_DATE            DE_DATE              LON   LAT
    ##    <chr>      <dbl> <chr>              <chr>              <dbl> <dbl>
    ##  1 tu55-1-09  97623 13-SEP-09 21:29:40 13-SEP-09 21:30:00 -73.9  38.6
    ##  2 tu55-1-09  97623 13-SEP-09 22:04:00 13-SEP-09 22:10:00 -73.9  38.6
    ##  3 tu55-1-09  97623 14-SEP-09 02:56:40 14-SEP-09 03:08:40 -73.8  38.6
    ##  4 tu55-1-09  97623 14-SEP-09 03:16:40 14-SEP-09 03:30:40 -73.8  38.6
    ##  5 tu55-1-09  97623 14-SEP-09 03:42:06 14-SEP-09 03:56:06 -73.8  38.6
    ##  6 tu55-1-09  97623 14-SEP-09 04:02:00 14-SEP-09 04:14:00 -73.8  38.6
    ##  7 tu55-1-09  97623 14-SEP-09 04:22:00 14-SEP-09 04:36:00 -73.8  38.6
    ##  8 tu55-1-09  97623 14-SEP-09 04:42:40 14-SEP-09 04:56:40 -73.8  38.6
    ##  9 tu55-1-09  97623 14-SEP-09 06:02:20 14-SEP-09 06:18:20 -73.8  38.6
    ## 10 tu55-1-09  97623 14-SEP-09 07:34:40 14-SEP-09 07:50:40 -73.8  38.6
    ## # ... with 264,612 more rows

### SQL

Structured Query Language (SQL) is a standard language for querying and
manipulating data. Essentially, SQL is the language we use to
communicate with a database.

The basic form for a SQL query is as follows:

``` sql
SELECT <columns>
FROM <one or more tables>
WHERE <conditions>
```

There are a lot more bells and whistles to SQL, but you’ll have to
research those on your own.

2 - Connect R to a Database
---------------------------

First, you will need to save the `data` folder that contains the *.csv
and *.accdb files into the `PEP-2020` folder that you setup in [Week
2](../week_2). Now we’ll run some R code:

``` r
## load libraries
library(DBI)

## connect to database
dbs_conn = dbConnect(odbc::odbc(), driver = "Microsoft Access Driver (*.mdb, *.accdb)", dbq = here::here('data', 'te_dive_20200626.accdb')) 

## get dive data
dive = dbGetQuery(conn = dbs_conn, statement = 'select * from TE_DIVE') 

## close database connection
dbDisconnect(dbs_conn)
```
