# Grafana實作練習


### Grafana 環境安裝

*2022/6/20*

*配備 4 Cpus以上 Linux 版本 Ubuntu 20.04*

1.  `sudo apt-get install -y adduser libfontconfig1`

2.  `wget https://dl.grafana.com/oss/release/grafana_9.0.0_amd64.deb`

3.  `sudo dpkg -i grafana_9.0.0_amd64.deb`

4.  `sudo systemctl enable --now grafana-server`

5.  `systemctl status grafana-server.service (確認有無啟動)`

6. `如是用雲端虛擬機，則需另在去防火牆規則中新增 3000/tcp port (eg. GCP 要去虛擬私有雲網路中的防火牆設定)`

![img](img/GCP_firewall.png)

### ELK 環境安裝

#### Elasticsearch

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

13.  `sudo nano /etc/elasticsearch/elasticsearch.yml` 變更 network.host:0.0.0.0 與 discovery.seed_hosts: [ ] 

14.  `sudo systemctl restart elasticsearch`

15.  `sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -i -u elastic (變更elastic密碼)`

16.  `curl -k -u elastic:密碼 -XGET "https://localhost:9200" (確認有無成功)`

17.  `在瀏覽器中輸入 https://IP:9200/`

#### Logstash

#### Kibana

















