
# Preamble

This compose file is meant as a quick way to try out and play with DalmainterDB, not as a production deployment!

# Provided Features
 
## Ingres

There are multiple ways to input data into this DalmatinerDB:

* 8086 - InfluxDB HTTP
* 2003 - Grafite
* 4242 - OpenTSDB
* 9999 - BSD Syslog
* 1234 - Prometheus Writer

## Egres

There are two primary ways to get data out of DalmatinerDB

* 8080 - Dalmatiner Frontend
* 3030 - Grafana 3.1.1 (With dalmatiner Plugin)

## Hostnames

* coordinator - initial db node
* db - additional database node(s)
* fe - the frontend(s)
* pg - postgres for dimensional indexing
* grafana - the grafana ui


# Grafana

This compose file comes with a Grafana container with the DalmatinerDB plugin pre-installed. It is however required to still add the datasource.

Go to [Grafana](http://localhost:3000) and log in with `admin` / `admin`. Go to `Datasrouces` and add a `DalmatinerDB` datasource with `http://fe:8080/` as a URL in `proxy` mode.