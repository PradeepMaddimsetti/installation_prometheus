# installing and  creating prometheus as a service
# Installing Prometheus 
## downloding binary file
prereqisites
* Linux Server
* wget
## prerequisites package downloding using apt-get package manager
```
sudo apt-get update
sudo apt-get install wget -y
```
## downloding package
[referal link](https://prometheus.io/download/)
change the path to /tmp
```
cd /tmp
```
downloding tar file
```
wget https://github.com/prometheus/prometheus/releases/download/v2.32.1/prometheus-2.32.1.linux-amd64.tar.gz
```
untar the file
```
tar -xvf prometheus-2.32.1.linux-amd64.tar.gz
```
create a folder prometheus on /usr/local/bin/
```
mkdir /usr/local/bin/prometheus

```
copy the files to the /usr/local/bin/prometheus
```
cp -r . /usr/local/bin/prometheus
```
then create a service file
```
echo "[Unit]
Description=Prometheus Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/prometheus/prometheus --config.file=/usr/local/bin/prometheus/prometheus.yml

[Install]
WantedBy=multi-user.target" | cat >/etc/systemd/system/prometheus.service 
```
or
```
cat <<EOF > /etc/systemd/system/prometheus.service
[Unit]
Description=Prometheus Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/local/bin/prometheus/prometheus --config.file=/usr/local/bin/prometheus/prometheus.yml

[Install]
WantedBy=multi-user.target
EOF
```

