# Laws.Africa ELK

Configuration files for Laws.Africa ELK stack, using Elasticsearch (E), Logstash (L), Kibana (K) and Elastic APM.

The base ELK stack is https://elk-docker.readthedocs.io/ with APM added to it.

All three services run on the same host. ELK all run in the same container, and APM runs in a separate container.
