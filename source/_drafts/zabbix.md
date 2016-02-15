title: Zabbix
tags:
---

## Grafana

```
docker run -d -v /var/lib/grafana --name grafana-xxl-storage busybox:latest

docker run \
  -d \
  -p 3000:3000 \
  --name grafana-xxl \
  --volumes-from grafana-xxl-storage \
  monitoringartist/grafana-xxl

```


# References
- <https://github.com/alexanderzobnin/grafana-zabbix>
- [基于Zabbix + Docker开发的监控系统](https://segmentfault.com/a/1190000002561058)
