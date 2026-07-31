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
vim /etc/systemd/system/prometheus.service

## run systemctl commands
systemctl enable prometheus
systemctl start prometheus
systemctl status prometheus

## check the netstat port - 9090 should be opened
<prometheus-public-ip>:9090

## Attach the roles and policy to the prometheus server for scraping the nodes and also update in the prometheus.yml file about dynamic scraping

### Node exporter installtion in the nodes
## manual installation folder
cd /opt/

## Download the node exporter
curl -o https://github.com/prometheus/node_exporter/releases/download/v1.12.1/node_exporter-1.12.1.linux-amd64.tar.gz

## extract the node exporter
tar -xf node_exporter-1.12.1.linux-amd64.tar.gz

## create the link file
ln -s node_exporter-1.12.1.linux-amd64 node_exporter

## Create the node_exporter service its in th folder
vim /etc/systemd/system/node_exporter.service

## run systemctl commands
systemctl enable node_exporter
systemctl start node_exporter
systemctl status node_exporter

## mention the AWS tags in nodes
check the tags in prometheus.yml

### Grafana Installation
wget -q -O gpg.key https://rpm.grafana.com/gpg.key
if not working use below command
curl -o -q -O gpg.key https://rpm.grafana.com/gpg.key