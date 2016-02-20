title: ELK
tags:
---

## filebeat

```
curl -L -O https://download.elastic.co/beats/filebeat/filebeat_1.1.1_amd64.deb
sudo dpkg -i filebeat_1.1.1_amd64.deb
cat /etc/filebeat/filebeat.yml
sudo service filebeat restart
filebeat -e -c filebeat.yml -d "*"
```

## logstash

```
bin/plugin install logstash-input-beats
```

## Install ELK on Aliyun Ubuntu 14.04

```
# Java
apt-get install software-properties-common
add-apt-repository -y ppa:webupd8team/java
sudo apt-get update
sudo apt-get -y install oracle-java8-installer

# ElasticSearch
wget -qO - https://packages.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
echo "deb http://packages.elastic.co/elasticsearch/2.x/debian stable main" | sudo tee -a /etc/apt/sources.list.d/elasticsearch-2.x.list
sudo apt-get update
sudo apt-get -y install elasticsearch
sudo vi /etc/elasticsearch/elasticsearch.yml
	network.host: localhost
sudo service elasticsearch restart
sudo update-rc.d elasticsearch defaults 95 10

# Kibana
echo "deb http://packages.elastic.co/kibana/4.4/debian stable main" | sudo tee -a /etc/apt/sources.list.d/kibana-4.4.x.list
sudo apt-get update
sudo apt-get -y install kibana
sudo vi /opt/kibana/config/kibana.yml
	server.host: "localhost"
sudo update-rc.d kibana defaults 96 9
sudo service kibana start

# Logstash
echo 'deb http://packages.elastic.co/logstash/2.2/debian stable main' | sudo tee /etc/apt/sources.list.d/logstash-2.2.x.list
sudo apt-get update
sudo apt-get install logstash
service logstash configtest
service logstash restart
update-rc.d logstash defaults 96 9

# Nginx
sudo apt-get install nginx apache2-utils
sudo htpasswd -c /etc/nginx/htpasswd.users kibanaadmin
sudo vi /etc/nginx/sites-available/default
server {
    listen 80;

    server_name example.com;

    auth_basic "Restricted Access";
    auth_basic_user_file /etc/nginx/htpasswd.users;

    location / {
        proxy_pass http://localhost:5601;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;        
    }
}
sudo service nginx restart


# Kinbana Dashboard
cd ~
curl -L -O https://download.elastic.co/beats/dashboards/beats-dashboards-1.1.0.zip

# Filebeat Index Template in ES
cd ~
curl -O https://gist.githubusercontent.com/thisismitch/3429023e8438cc25b86c/raw/d8c479e2a1adcea8b1fe86570e42abab0f10f364/filebeat-index-template.json
curl -XPUT 'http://localhost:9200/_template/filebeat?pretty' -d@filebeat-index-template.json
```

## Debug
- <http://grokdebug.herokuapp.com/>


# References
- [使用ELK(Elasticsearch + Logstash + Kibana) 搭建日志集中分析平台实践](https://wsgzao.github.io/post/elk/)
- [日志收集架构－ELK](http://blog.kazaff.me/2015/06/05/%E6%97%A5%E5%BF%97%E6%94%B6%E9%9B%86%E6%9E%B6%E6%9E%84--ELK/)
- [Running our own ELK stack with Docker and Rancher](http://rancher.com/running-our-own-elk-stack-with-docker-and-rancher/)
- [NGINX Log Analysis with Elasticsearch, Logstash, and Kibana](http://logz.io/blog/nginx-log-analysis/)
- [ELK in Docker 安装、配置和效果展示](https://blog.sectong.com/blog/elk_in_docker.html)
- [How To Install Elasticsearch 1.7, Logstash 1.5, and Kibana 4.1 (ELK Stack) on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-1-7-logstash-1-5-and-kibana-4-1-elk-stack-on-ubuntu-14-04)
- [ELKstack 中文指南](https://www.gitbook.com/book/chenryn/kibana-guide-cn/details)
- [How To Install Elasticsearch, Logstash, and Kibana (ELK Stack) on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-install-elasticsearch-logstash-and-kibana-elk-stack-on-ubuntu-14-04)
- [How to install oracle-java8-installer faster](https://maowtm.org/articles/oracle-java-installer-downloads-sucks/)
- [Adding Logstash Filters To Improve Centralized Logging](https://www.digitalocean.com/community/tutorials/adding-logstash-filters-to-improve-centralized-logging)
