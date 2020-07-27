# Prometheus-Grafana

Link below shows how to setup EC2 instances to be monitored using Prometheus

* https://github.com/devesh15951/EC2-Prometheus

## Lets get started with Grafana Visualization from Prometheus

Note- (I've used the same instance that hosts prometheus, to install Grafana.)

Make sure to open port 3000(for Grafana) and 9090(for Prometheus).

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

Open the link to verify Grafana is installed
```
http://<YourGrafanaInstanceIP>:3000
````

## Let's create simple dashboard on Grafana to monitor instances from Prometheus

The initial username and password is "admin" for Grafana.

* Import Dashboard
1. Go to `Add your first data source`, click `prometheus` and configure address of server (http://localhost:9090). This will add source.
2. Click on import
3. Enter 405 or 1860 as the Grafana id. These are two different dashboards freely available online.
4. Give a unique name and select source as prometheus.
5. Your dashboard is ready.
