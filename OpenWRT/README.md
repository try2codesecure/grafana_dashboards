### OpenWRT Dashboard

![OpenWRT](../OpenWRT/openwrt.png "OpenWRT Dashboard")

Grafana Url --> https://grafana.com/grafana/dashboards/11147

HowTo --> https://www.cloudrocket.at/posts/monitor-openwrt-nodes-with-prometheus/

Prometheus source, for node_exporter

Monitor for OpenWRT routers

based on node exporter full

Only requires the default job_name: node, add as many targets as you need in '/etc/prometheus/prometheus.yml'.


```
  - job_name: OpenWRT
    static_configs:
      - targets: ['localhost:9100']
```

The following lua scripts has to be installen on yout openwrt router:

```
prometheus-node-exporter-lua
prometheus-node-exporter-lua-nat_traffic
prometheus-node-exporter-lua-netstat
prometheus-node-exporter-lua-openwrt
prometheus-node-exporter-lua-wifi
prometheus-node-exporter-lua-wifi_stations
```

If you don't get number of Wifistations and details
```
opkg remove wpad-basic-wolfssl
opkg install wpad-wolfssl
reboot
```

Notes:

tested with prometheus-node-exporter-lua scripts version 2019.08.14-1





