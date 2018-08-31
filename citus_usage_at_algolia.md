# Source

[With Citus, Algolia Speeds Up Search Analytics & Eradicates Database Management Headaches](https://www.citusdata.com/customers/algolia)

# tl;dr

+ Previous elasticsearch solution didn't handle huge traffic spike (~1B search operation by day), making it scale up wasn't impossible but required to much resource from Algolia at that time.

+ Look for scalability for new solution, rejected BigQuery of Google because of pricing model that make it hard to estimate cost and being too slow.

+ Redshift isn't a good option for doing sub-second aggregation regarding cost.

+ Clickhouse wasn't available on the cloud.

+ Citus allow to perform TopN and HyperLogLog operation on a distributed database via extension, a proof of concept was done with Citus team
> Benchmark tests showed that the Citus database would be capable of ingesting up to seven million rows per second.  
> Citus Cloud enables Algolia to ingest 5-10B rows per day—and growing.  
> Ninety-five percent of the queries made to our Citus database receive responses in less than 800 milliseconds.  

+ Only one cluster in the US now, plan to open another in Europe

+ Current process : raw events > aggregation job (5minutes) > rollup table > aggregation job (daily) > update rollup.  
So Citus store only the rollup, help speed up query and lower cost
