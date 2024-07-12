# Twinficient

Set up the docker stack as described in the [docker folder readme file](./docker/README.md).

It is required that you install the [influx CLI](https://docs.influxdata.com/influxdb/cloud/reference/cli/influx/) and run *init-influx.sh* (For now just works on the host machine by accesing localhost). Adjust the server settting in the script, if you are not running Influx on your machine.

To migrate metrics from the SQLite database to InfluxDB follow [these instructions](./telegraf/README.md).

When the docker instances are up and running, import bucket data as described [here](./backup/README.md). You need to provide the data previously and store it in your repository to share it with your collegues.

Check out the template script for importing influx db related components [here](./templates/README.md). 


# Useful tools

The following tools, or part of them, could be useful for your projects.

- shell scripts that are contained in the subfolders
    - expecially the [tool to extract aasx files](./aasx/README.md)
- [docker-stack that](./docker/README.md) could be adapted for your needs
- [data-integration tool](./services/data-integration/README.md)
    - useful for task aggregation
- [digital-twin-initializer](./services/digital-twin-initializer/README.md)
    - useful to define digital twins in a simple format like csv and let them be converted and deployed by the tool
    - it also keeps the csv and the server-side resources in sync
- [basyx-java-clients](./services/basyx-java-clients/) 
    - java client to interact with [V3 digital twin services](https://github.com/admin-shell-io/aas-specs-api) defined by the IDTA
- [validation tool](./scripts/validate-aas/README.md) for aasx files
- [dashboard component](./docker/config/observability/) that are registered in the docker stack
- [telegraf example](./telegraf/README.md) that illustrates how telegraf can also be used to perform data import.


# LICENSE

See the licence notice in this folder.

Check third party licenses in the following java projects:

- [validate-aas](./scripts/validate-aas/THIRD-PARTY.txt)
- [basyx-java-clients](./services/basyx-java-clients/THIRD-PARTY.txt)
- [data-integration](./services/data-integration/THIRD-PARTY.txt)
- [digital-twin-initializer](./services/digital-twin-initializer/THIRD-PARTY.txt)

In the docker stack, the components are just used as services. As a hint, we listed the licenses here:

|Image|Licence|
|---|---|
|portainer/portainer-ce:2.18.2|Zlib|
|nginxproxy/nginx-proxy:1.3.1-alpine|MIT|
|influxdb:2.7.4	Apache-2.0|MIT|
|dfkibasys/aas-registry-dotaas-part2-log-mem|MIT|
|dfkibasys/aas-server|EPL-1.0|
|dfkibasys/ppr-dashboard|EPLv2|
|mongo:7.0.5-jammy|SSPL v1.0|
|eclipsebasyx/aas-registry-log-mongodb|MIT|
|eclipsebasyx/submodel-registry-log-mongodb|MIT|
|eclipsebasyx/aas-environment|MIT|
|eclipsebasyx/aas-gui|MIT|
|grafana/grafana:9.3.16|AGPL-3.0|
|prom/node-exporter:v1.6.0|Apache-2.0|
|gcr.io/cadvisor/cadvisor:v0.47.2|Apache-2.0|
|prom/prometheus:v2.45.0|Apache-2.0|
|grafana/loki:2.8.0|AGPL-3.0|
|grafana/promtail:2.8.0|AGPL-3.0|
 
```
