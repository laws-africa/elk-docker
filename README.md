# Laws.Africa ELK

Configuration files for Laws.Africa ELK stack, using Elasticsearch (E), Logstash (L), Kibana (K) and Elastic APM. Adapted from https://github.com/elastic/stack-docker. An overview of the APM setup is available at https://www.elastic.co/guide/en/apm/get-started/current/overview.html

This runs:

* Elasticsearch, listening on :9200
* APM server, listening on :8200
* Kibana, listening on :5601

The DNS entry `elk.int.laws.africa` should be set to the AWS-internal IP address of this instance.

AWS firewalls prevent any of these from being accessed from outside the network.
