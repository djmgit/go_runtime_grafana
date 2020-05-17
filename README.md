# go_runtime_grafana

This repository provides a Grafana dashboard, exported as JSON, for monitoring GOLang runtime of applications in a DC based
setup where a given application is deployed on a cluster of servers in a given Data center (on prem or cloud). This dashboard
groups together servers by the services being run on them, and services by the DC they are being served from.

It is possible to select one or multiple DC, and one or multiple hosts for a given service to compare metrics cross hosts and
cross DC.

This requires runtime metrics to be exported by the application using prometheus client library for GOLang

## Exporting GOLang metrices

Given below is a simple, tiny code snippet for enabling your application to expose prometheus metrics at ```/metrics```
endpoint

```
package main

import (
        "net/http"
        "github.com/prometheus/client_golang/prometheus/promhttp"
)


func main() {

        http.Handle("/metrics/", promhttp.Handler())
        http.ListenAndServe(":8888", nil)
}

```

This will expose Go runtime metrics at ```http://127.0.0.1:8888/metrics```

You can send custom metrics to. You can find out more about instrumenting your GOLang app with Prometheus at ther
offician <a href="https://prometheus.io/docs/guides/go-application/">documentation</a>.

## Adding a target in Prometheus 
