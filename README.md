# go_runtime_grafana

This repository provides a Grafana dashboard, exported as JSON, for monitoring GOLang runtime of applications in a DC based
setup where a given application is deployed on a cluster of servers in a given Data center (on prem or cloud). This dashboard
groups together servers by the services being run on them, and services by the DC they are being served from.

It is possible to select one or multiple DC, and one or multiple hosts for a given service to compare metrics cross hosts and
cross DC.

This requires runtime metrics to be exported by the application using prometheus client library for GOLang

## Exporting GOLang metrices


## Adding a target in Prometheus 
