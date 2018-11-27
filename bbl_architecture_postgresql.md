# Source

[Architectures Postgresql by Dimitri Fontaine](https://tapoueh.org/images/confs/BBL-Orness-Meetup-2018.pdf)

# tl;dr

+ A quick reminder of how and why PostgreSQL follow ACID definition (Atomic, Consistent, Isolated and Durable), Atomic because everything can be done inside a transaction and [rollback](https://www.postgresql.org/docs/current/sql-rollback.html), Consistent because relations follow a strict [schema](https://www.postgresql.org/docs/current/ddl-schemas.html) with [constraint](https://www.postgresql.org/docs/current/ddl-constraints.html), isolation can be provided at diverse [levels](https://www.postgresql.org/docs/9.1/transaction-iso.html) and durable by ack after storing on disk


+ If you are not able to automatically restore backup they become useless (here is an article about how they handle it at [Leboncoin](https://medium.com/leboncoin-engineering-blog/managing-postgresql-backup-and-replication-for-very-large-databases-61fb36e815a0)

+ Don't forget that when replicating operations you also replicate the `DROP TABLE` and `TRUNCATE` queries so hot swapping Standy for Primary when it crashes is not always possible.

+ There are lots of really great examples comparing client-side code in python VS advanced SQL queries most of which are from the book ["Mastering PostgreSQL"](https://masteringpostgresql.com/)

+ You have the possibility to alter individual [transaction property](https://www.postgresql.org/docs/current/sql-set-transaction.html) in PostgreSQL, for example, you may want to add harsher constraints on financial transactions that are over a certain sum using a [triggers](https://www.postgresql.eu/events/pgdayparis2018/sessions/session/1841/slides/76/triggers_pdfa.pdf) 

+ One abstruse feature of PostgreSQL is [LATERAL JOIN](https://medium.com/kkempin/postgresqls-lateral-join-bfd6bd0199df)

+ When doing an alter on a table column you can modify the actual content with the command `USING` that allow to apply a function (like replace, substring, etc), also you can combine multiple alters in the same query

+ Never forgot that PostgreSQL comes with powerful calendar operations to compare and manipulate dates like `cal.itermonthdates` and you can use `generate_series` with them

+ PostgreSQL also implements windows functions that you can see in action [here](https://www.citusdata.com/blog/2018/06/01/fun-with-sql-window-functions-in-postgresql/)

+ Next, you have some tooling for dev with python [AnoSQL](https://github.com/honza/anosql) to define SQL function in .sql files, [RegreSQL](https://github.com/dimitri/regresql) for testing regression in SQL queries, Geolocation with [ip4r](https://tapoueh.org/blog/2018/08/geolocation-with-postgresql/)

# Afterword

Really great insight of the responsibility of a DBA "we are responsible to provide a service AND ensure data integrity" and concrete use case for some lesser known features in PostgreSQL
