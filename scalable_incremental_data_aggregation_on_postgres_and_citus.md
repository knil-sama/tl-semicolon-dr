# Source

[Medium by Marco Slot](https://www.citusdata.com/blog/2018/06/14/scalable-incremental-data-aggregation/)

# tl;dr

⋅⋅* Rollup table exists in postgresql

⋅⋅* We assume all events have an identifier which is drawn from a sequence and provide a simple SQL function that enables you to incrementally aggregate ranges of sequence values in a safe, transactional manner. => this is really fucking hard and right now postgresql can't handle it

⋅⋅* Need to wait for in-progress writes to finish by using lock

⋅⋅* This solution really put emphasis on Availability and perfo over consistency

⋅⋅* BRIN index is performant on sequence

⋅⋅* Really put lot of marketing for citus perf but what we saw is still relevant for normal postgresql database

# Afterword

Would like to see this technique but with the new pub sub of postgresql
