# Weblogic ELK

This repository runs Elasticsearch, Kibana, Logstash and Filebeat as containers on Docker.

## Instructions

I separated Elasticsearch and Kibana from Logstash and Filebeat to easily tests with different configurations, starting the containers faster.

### Run the containers

Execute the commands below to run the containers.

```bash
# Create user-defined network to use between all containers
docker network create weblogic-network

# Start Elasticsearch and Kibana containers
docker-compose -f ./docker-compose-elastic-kibana.yml up -d --build

# Start Logstash and Filebeat containers
docker-compose -f ./docker-compose-logstash-filebeat.yml up -d --build
```

### Check if all it's ok

Access the links below to check if the containers are running.

Logstash - http://localhost:9600/

Elasticsearch - http://localhost:9200/

Kibana - http://localhost:5601/



## Inspiration

This repository was based on listed below.

- https://logz.io/blog/logstash-mutate-filter/
- https://www.elastic.co/pt/blog/a-practical-introduction-to-logstash
- https://sharing.luminis.eu/blog/robust-logstash-configuration/
- https://github.com/carlgira/weblogic-elk
- https://github.com/justmeandopensource/elk
- https://github.com/elastic/examples
- https://github.com/jettro/docker-elk-blog
- https://github.com/deviantony/docker-elk
- https://github.com/waldemarnt/elk-compose
