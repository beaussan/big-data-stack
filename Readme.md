# Big data docker compose

This docker compose is to start a small dev environement to work with hbase, elastic, kibana and spark.

To get started, you need docker and docker compose.


## Start the project

To start the project, you need 2 thing : create a web network and start the docker stack.

```bash
docker network create web
```

Then : 

```bash
docker-commpose up -d
```

You can then go to the following urls to access differents part this project :

- [http://hbase.docker.localhost/](http://hbase.docker.localhost/) : hbase web ui
- [http://spark.docker.localhost/](http://spark.docker.localhost/) : spark web uis

- [http://elastic.docker.localhost/](http://elastic.docker.localhost/) : elastic serach endpoint
- [http://kibana.docker.localhost/](http://kibana.docker.localhost/) : kibana web ui

- [http://hue.docker.localhost/](http://hue.docker.localhost/) : hue web ui

- [http://traefik.docker.localhost/](http://traefik.docker.localhost/) : the reverse proxy

Monitoring stack :

- [http://grafana.docker.localhost/](http://grafana.docker.localhost/) : the grafana web ui with dashboard (admin/foobar)
- [http://prometheus.docker.localhost/](http://prometheus.docker.localhost/) : prometheus, the log agregator
- [http://node-exporter.docker.localhost/](http://node-exporter.docker.localhost/) : get metrics for containers
- [http://alertmanager.docker.localhost/](http://alertmanager.docker.localhost/) : send alert to a slack, to be configured
- [http://cadvisor.docker.localhost/](http://cadvisor.docker.localhost/) : get metrics from host




## Known Issues :warning:

I have noticed when running elasticserach **5.0+** version on a linux host you need to increase the memory map areas with the following command

```bash
sudo sysctl -w vm.max_map_count=262144
```
