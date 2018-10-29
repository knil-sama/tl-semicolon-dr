# Source

[Article on confluent by Gwen Shapira](https://www.confluent.io/blog/apache-kafka-kubernetes-could-you-should-you)

# tl;dr

+ Main issue that you should understant is that kafka is a stateful service and kubernetes is a stateless service  

+ Brokers need to be access directly (no load balancers) => how to insure network ip/dns are shared in the cluster and for consumer/producer  

+ Persistent storage can't be done on kubernetes currently need to rely on cloud (esb) or physical machine => Can be done with some effort but should be made easier soon [in kubernetes](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)  

+ Confluent provides some tooling to help make the transition [easier](https://github.com/confluentinc/cp-ansible) and [recommendations](https://www.confluent.io/resources/recommendations-for-deploying-apache-kafka-on-kubernetes) but it will still require a consequent effort even with a dedicated kubernetes team  

+ Once you have make it work on kubernetes scaling would be faster than on physical server but the path to make it work correctly would take some time  

+ Even knowing all this in advance you shouldn't try to run kafka as your first kubernetes project it will take you too much time to understand both at the same time  

# Afterword

This article resume lot of the issue we run into when setting up our own kafka cluster on kubernetes, I would add to this than vpc access and monitoring should be one of your big priority in our case datadog wasn't working as expected and the combo (jvmx + prometheus + grafana) help us tremendously to figure out what happen, also apart from broker, connector and zookeper are more easier to deploy on kubernetes due to them having part of their state distributed on broker
