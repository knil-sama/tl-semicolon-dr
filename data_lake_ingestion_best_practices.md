# Source

[Medium by David Worms](https://medium.com/@wdavidw/data-lake-ingestion-best-practices-3fddf30e11f5)

# tl;dr

1. You usually have too few data engineer to let them be working in a inefficient setting

2. Most of the productivity rule in IT apply, reusability, planification and communication are a MUST not a SHOULD


3. Decoupling storage from processing (:100:); if you can, use Avro as common format (working in batch and streaming process)


4. Use a SINGLE schema registry, that can and MUST be accessible for everybody with evolution of schema propagated to ingestion

	1. The schema can carry additional information for example to facilitate mapping to JSON or a database.=> I didn't agreed at all with this, the more infos you put that are not strictly related to the schema the more cumbersome it get


5. Advocate for a pub-sub system to trigger and schedule ingestion (in opposition to cronjob and watcher)

# Sumary

Good article not too technical but tacle lot of architectural issues
