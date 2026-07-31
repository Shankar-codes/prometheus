## Prometheus Installation
Website: https://prometheus.io/download/

https://github.com/prometheus/prometheus/releases/download/v3.5.5/prometheus-3.5.5.linux-amd64.tar.gz

## download it from prometheus website
wget https://github.com/prometheus/prometheus/releases/download/v3.5.5/prometheus-3.5.5.linux-amd64.tar.gz

## Extract the prometheus
tar -xf prometheus-3.5.5.linux-amd64.tar.gz

## create the link file
ln -s prometheus-3.5.5.linux-amd64 prometheus

## Create the prometheus service its in th folder
vim /ect/systemd/system/prometheus.service

## run systemctl commanda
systemctl enable prometheus
systemctl start prometheus
systemctl status prometheus

## check the netstat port - 9090 should be opened
<prometheus-public-ip>:9090

## Attach the roles and policy to the prometheus server for scraping the nodes and also update in the prometheus.yml file about dynamic scraping

