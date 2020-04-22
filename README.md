# Golang With Prometheus and Grafana Example

## Getting Started
### Download Prometheus
https://prometheus.io/docs/prometheus/latest/getting_started/

### Download Grafana
https://grafana.com/grafana/download
```cassandraql
brew update
brew install grafana
brew services start grafana
```
## Prometheus Metrics
### Counters
#### Use Cases
- request count
- tasks completed
```cassandraql
rate(request_count[5m])
```
### Gauges 
#### Use Cases
- memory usage
- queue size
- number of requests in progress
```cassandraql
avg_over_time(queue_size[5m])
```

### Histogram
#### Use Cases
- request duration
- response size
```
rate(request_duration_sum[5m])/rate(request_duration_count[5m])
```

### Summary
#### Use Cases
- request duration
- response size

## Import Prometheus Into Grafana
https://prometheus.io/docs/visualization/grafana/

## Running Docker Prometheus
```
docker pull prom/prometheus
docker run --name prometheus -d -p 9090:9090 -v ./prometheus prom/prometheus:latest

```

