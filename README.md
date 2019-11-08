# grafana_dashboards
collection of grafana dashboards


### OpenWRT Dashboard

Prometheus source, for node_exporter

Monitor for OpenWRT routers

based on node exporter full

Only requires the default job_name: node, add as many targets as you need in '/etc/prometheus/prometheus.yml'.


```
  - job_name: OpenWRT
    static_configs:
      - targets: ['localhost:9100']
```

The following lua scripts has to be installed on your OpenWRT router:

```
prometheus-node-exporter-lua
prometheus-node-exporter-lua-nat_traffic
prometheus-node-exporter-lua-netstat
prometheus-node-exporter-lua-openwrt
prometheus-node-exporter-lua-wifi
prometheus-node-exporter-lua-wifi_stations

```

Notes:

tested with prometheus-node-exporter-lua scripts version 2019.08.14-1

