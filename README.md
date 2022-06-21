# Grafana實作練習

*2022/6/20*

* [Grafana 環境安裝](#grafanaenv)

* [Elasticsearch 環境安裝](#elaenv)

* [Logstash 環境安裝](#logstashenv)

* [Kibana 環境安裝](#kibanaenv)

<h2 id="grafanaenv">Grafana 環境安裝</h2>

*配備 4 Cpus以上 Linux 版本 Ubuntu 20.04*

1.  `sudo apt-get install -y adduser libfontconfig1`

2.  `wget https://dl.grafana.com/oss/release/grafana_9.0.0_amd64.deb`

3.  `sudo dpkg -i grafana_9.0.0_amd64.deb`

4.  `sudo systemctl enable --now grafana-server`

5.  `systemctl status grafana-server.service (確認有無啟動)`

6. `如是用雲端虛擬機，則需另在去防火牆規則中新增 3000/tcp port (eg. GCP 要去虛擬私有雲網路中的防火牆設定)`

![img](img/GCP_firewall.png)

<h2 id="elaenv">Elasticsearch 環境安裝</h2>

1.  `sudo apt update ; sudo apt-get update`

2.  `sudo apt install apt-transport-https openjdk-11-jdk -y`

3.  `java --version (確認有無顯示JAVA版本)`

4.  `sudo nano /etc/environment` 在第二行加入 `JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64"`

5.  `source /etc/environment`

6.  `echo $JAVA_HOME (確認設定是否正確)`

7.  `wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg`

8.  `echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-8.x.list`

9.  `sudo apt-get update`

10. `sudo apt-get install elasticsearch -y`

11.  `sudo systemctl start elasticsearch`

12.  `sudo systemctl status elasticsearch`

13.  `sudo nano /etc/elasticsearch/elasticsearch.yml` 取消註解並變更 network.host:0.0.0.0 與 discovery.seed_hosts: [ ] 

14.  `sudo systemctl restart elasticsearch`

15.  `sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -i -u elastic (按 y 後，改 elastic 密碼)`

16.  `curl -k -u elastic:密碼 -XGET "https://localhost:9200" (確認有無成功)`

17.  `在瀏覽器中輸入 https://IP:9200/`

18.  補充：`如是用雲端虛擬機，則需另在去防火牆規則中新增 9200/tcp port (eg. GCP 要去虛擬私有雲網路中的防火牆設定)`

<h2 id="logstashenv">Logstash 環境安裝</h2>

1.  `wget https://artifacts.elastic.co/downloads/logstash/logstash-8.2.3-amd64.deb`

2.  `sudo dpkg -i logstash-8.2.3-amd64.deb`

3.  `sudo systemctl start logstash`

4.  `sudo systemctl status logstash`

5.  `sudo systemctl stop logstash (先關掉之後再用)`

<h2 id="kibanaenv">Kibana 環境安裝</h2>

1.  `wget https://artifacts.elastic.co/downloads/kibana/kibana-8.2.3-amd64.deb`

2.  `sudo dpkg -i kibana-8.2.3-amd64.deb`

3.  `sudo sh /usr/share/elasticsearch/bin/elasticsearch-certutil ca --pem` 之後按enter

4.  `sudo -s (進入root模式，ctrl+d 可退出)`

5.  `cp /usr/share/elasticsearch/elastic-stack-ca.zip /etc/kibana`

6.  `cd /etc/kibana`

7.  `sudo apt-get install unzip -y`

8.  `unzip elastic-stack-ca.zip`

9.  `cp /etc/elasticsearch/certs/http_ca.crt /etc/kibana/ca`

10.  `chgrp kibana /etc/kibana/ca/*`

11.  `chown kibana /etc/kibana/ca/*`

12.  `/usr/share/elasticsearch/bin/elasticsearch-reset-password -i -u kibana_system (按 y 後，改 kibana 密碼)`

13.  `sudo nano /etc/kibana/kibana.yml (直接將下面程式碼貼在最上層)`

    server.host: "0.0.0.0"
    elasticsearch.username: "kibana_system"
    elasticsearch.password: "自己設定的密碼(步驟12)"
    server.ssl.enabled: true
    server.ssl.certificate: /etc/kibana/ca/ca.crt
    server.ssl.key: /etc/kibana/ca/ca.key
    elasticsearch.hosts: ["https://自己ip:9200"]
    elasticsearch.ssl.certificateAuthorities: [ "/etc/kibana/ca/http_ca.crt" ]
    elasticsearch.ssl.verificationMode: none


14.  `sudo systemctl start grafana-server`

15.  `sudo systemctl restart kibana (有時無法開啟要重啟 kibana)`

16.  `在瀏覽器中輸入 https://自己ip:5601`

17.  補充：`如是用雲端虛擬機，則需另在去防火牆規則中新增 5601/tcp port (eg. GCP 要去虛擬私有雲網路中的防火牆設定)`















