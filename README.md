# Grafana實作練習


### Grafana 環境安裝

*Ubuntu 20.04*

1.  sudo apt-get install -y adduser libfontconfig1

2.  wget https://dl.grafana.com/enterprise/release/grafana-enterprise_9.0.0_amd64.deb

3.  sudo dpkg -i grafana-enterprise_9.0.0_amd64.deb

4.  sudo systemctl enable --now grafana-server

5.  systemctl status grafana-server.service (確認有無啟動)
