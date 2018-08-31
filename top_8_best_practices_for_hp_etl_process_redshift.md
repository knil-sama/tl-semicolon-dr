# Source

[AWS article](https://aws.amazon.com/fr/blogs/big-data/top-8-best-practices-for-high-performance-etl-processing-using-amazon-redshift/)

# tl;dr

+ Try to use a single copy command so Redshift can try to paralelize operation, for same reason split large file into X even size files where X is a multiple of Redshift "slice" (node * slice by instance)

+ Use Redshift workload management (WLM) by setting a queue for etl job with few slots so the COMMIT will not crippled performance, and a reporting queue that handle more big and long running query.

+ Cleanup regularly by DROP/TRUNCATE of temp table and use of VACUUM command to reclaim lost space (don't forget to prevent access on table during VACUUM due to lock, also can take a LONG time)

+ If can group all your etl transaction into one commit to not hung the base.

+ For loading really big bulk of data different strategy exists like create temporry staging table with CREATE TEMPORARY TABLE that will be dropped after usage and for add new row to data use ALTER table APPEND

+

# Afterword

Use COMMIT with parsimony, I got back more than 25% of a Redshift memory after a complete VACUUM :astonished: so don't forget it.
