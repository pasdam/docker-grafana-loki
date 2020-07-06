# docker-grafana-loki

This repository contains a docker-compose manifest to deploy a simple system to
play around with [Loki](https://github.com/grafana/loki) and
[Grafana](https://grafana.com/) for log management.

## Setup

Create a file `test.log` in the folder `promtail`, it will be used to publish
logs.

## Access to Grafana

Grafana will be accessible at [localhost:3000](http://localhost:3000), the
credentials are the default ones: username `admin`, password `admin`.

## Publish logs

To publish a log simply add a line to `promtail/test.log`. If the log is in the
json format:

```json
{"timestamp": "0001", "message": "some-message-01", "level": "info", "trace_id": "traceId-01", "span_id": "spanId-01"}
```

the field `level` will be considered as a tag, and can be used to query logs in
Grafana.
