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

## Installation

Install [docker](https://docs.docker.com/install/):

1. 'sudo apt-get remove docker docker-engine docker.io containerd runc'
2. 'sudo apt-get update'
3. 'sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common'
4. 'curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -'
5. 'sudo apt-key fingerprint 0EBFCD88'
6. 'sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"'
7. 'sudo apt-get update'
8. 'sudo apt-get install docker-ce docker-ce-cli containerd.io'



Install [docker-compose](https://linuxize.com/post/how-to-install-and-use-docker-compose-on-ubuntu-18-04/):

1. `sudo curl -L "https://github.com/docker/compose/releases/download/1.23.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
2. `sudo chmod +x /usr/local/bin/docker-compose`

Install this package:

1. `git clone https://github.com/laws-africa/elk-docker.git`
2. `cd elk-docker`
5. `docker-compose up -d`
Note that you will likely need to run docker-compose as sudo
