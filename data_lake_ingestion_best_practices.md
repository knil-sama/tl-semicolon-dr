# Source

[Medium by David Worms](https://medium.com/@wdavidw/data-lake-ingestion-best-practices-3fddf30e11f5)

# tl;dr

+ You usually have too few data engineer to let them be working in a inefficient setting

+ Most of the productivity rule in IT apply, re-usability, planification and communication are a MUST not a SHOULD


+ Decoupling storage from processing (:100:); if you can, use Avro as common format (working in batch and streaming process)


+ Use a SINGLE schema registry, that can and MUST be accessible for everybody with evolution of schema propagated to ingestion

- The schema can carry additional information for example to facilitate mapping to JSON or a database.=> I didn't agreed at all with this, the more info you put that are not strictly related to the schema the more cumbersome it get


+ Advocate for a pub-sub system to trigger and schedule ingestion (in opposition to cronjob and watcher)

# Afterword

Good article not too technical but tackle lot of architectural issues
