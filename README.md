# Prometheus-Grafana

Link below shows how to setup EC2 instances to be monitored using Prometheus

* https://github.com/devesh15951/EC2-Prometheus

## Lets get started with Grafana Visualization from Prometheus

Note- (I've used the same instance that hosts prometheus, to install grafana.)

When logged in as root, create grafana.repo
```
vi /etc/yum.repos.d/grafana.repo
````
Add the following to the file
```
[grafana]
name=grafana
baseurl=https://packages.grafana.com/enterprise/rpm
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://packages.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
````

Install Grafana
```
sudo yum install grafana
````

Start Grafana service and verify that the service is running
```
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl status grafana-server
````
