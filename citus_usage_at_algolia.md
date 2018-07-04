# Source

[With Citus, Algolia Speeds Up Search Analytics & Eradicates Database Management Headaches](https://www.citusdata.com/customers/algolia)

# tl;dr

1. Previous elasticsearch solution didn't handle huge traffic spike (~1B search operation by day), making it scale up wasn't impossible but required to much resource from Algolia at that time.

2. Look for scalability for new solution, rejected BigQuery of Google because of pricing model that make it hard to estimate cost and being too slow.

3. Redshift isn't a good option for doing sub-second aggregation regarding cost.

4. Clickhouse wasn't available on the cloud.

5. Citus allow to perform TopN and HyperLogLog operation on a distributed database via extension, a proof of concept was done with Citus team
# Afterword
