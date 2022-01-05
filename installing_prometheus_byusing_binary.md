### Installing Prometheus 
# downloding binary file
prereqisites
* Linux Server
* wget
# prerequisites package downloding using apt-get package manager
```
sudo apt-get update
sudo apt-get install wget -y
```
# downloding package
[referal link](https://prometheus.io/download/)
downloding tar file
```
wget https://github.com/prometheus/prometheus/releases/download/v2.32.1/prometheus-2.32.1.linux-amd64.tar.gz
```
untar the file
```
tar -xvf prometheus-2.32.1.linux-amd64.tar.gz
```
start the server
```
prometheus
```