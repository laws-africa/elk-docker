# Laws.Africa Metrics Processing Stack

Configuration files for Laws.Africa ELK stack, using Elasticsearch (E), Logstash (L), Kibana (K) and Elastic APM. Adapted from https://github.com/elastic/stack-docker. An overview of the APM setup is available at https://www.elastic.co/guide/en/apm/get-started/current/overview.html

This sets up a collection of services to process metrics and display them in a Kibana dashboard.

This instance is not accessible from the outside world. Access to Kibana is through a [secure nginx proxy](https://github.com/laws-africa/kibana-proxy).

## Networking

This runs:

* Elasticsearch, listening on :9200
* APM server, listening on :8200
* Kibana, listening on :5601

The DNS entry `elk.int.laws.africa` should be set to the AWS-internal IP address of this instance.

AWS firewalls prevent any of these from being accessed from outside the network.
