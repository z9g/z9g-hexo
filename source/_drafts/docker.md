title: Docker.md
tags:
---

# Aliyun Docker

## Install

```
curl -sSL http://acs-public-mirror.oss-cn-hangzhou.aliyuncs.com/docker-engine/internet | sh -
echo "DOCKER_OPTS=\"--registry-mirror=https://ykxv5kpi.mirror.aliyuncs.com\"" | sudo tee -a /etc/default/docker
sudo service docker restart

apt-get update
apt-get install python-pip
pip install docker-compose
```

# References
- <http://console.d.aliyun.com/index2.html/?spm=0.0.0.0.A1b8t7#/docker/booster>
