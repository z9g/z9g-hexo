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

## Aliyun Mirror

```
docker-machine ssh dev
sudo su
echo "EXTRA_ARGS=\"--registry-mirror=https://ykxv5kpi.mirror.aliyuncs.com\"" >> /var/lib/boot2docker/profile
exit
docker-machine restart dev
```

or

```
# 创建一台安装有Docker环境的Linux虚拟机，指定机器名称为default，同时配置Docker加速器地址。 
docker-machine create --engine-registry-mirror=https://ykxv5kpi.mirror.aliyuncs.com -d virtualbox default  

# 查看机器的环境配置，并配置到本地。然后通过Docker客户端访问Docker服务。 
docker-machine env default 
eval "$(docker-machine env default)" 
docker info
```

## CentOS7 firewarlld

```
https://docs.docker.com/v1.6/installation/centos/#installing-docker-centos-7
http://www.lxy520.net/2015/09/24/centos-7-docker-qi-dong-bao/

service iptables status
iptables --list
service iptables stop

systemctl status firewalld
firewall-cmd --list-all
firewall-cmd --list-ports
firewall-cmd --permanent --list-ports
firewall-cmd --zone=public --permanent --list-ports
less /usr/lib/firewalld/services/http.xml
firewall-cmd --state
firewall-cmd --get-zones
firewall-cmd --get-services
firewall-cmd --query-service http
firewall-cmd --add-servie=http
firewall-cmd --add-service=http
firewall-cmd --query-service http
firewall-cmd --remove-service=http
firewall-cmd --query-service http
firewall-cmd --query-service https
firewall-cmd --query-service http

firewall-cmd --permanent --zone=trusted --change-interface=docker0
firewall-cmd --permanent --zone=trusted --add-port=4243/tcp
firewall-cmd --reload

简单粗暴:
systemctl stop firewalld
systemctl stop docker
systemctl start docker
```

# References
- <http://console.d.aliyun.com/index2.html/?spm=0.0.0.0.A1b8t7#/docker/booster>
