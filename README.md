# LAB prostředí - Docker

## Komponenty
  * [Docker](https://www.docker.com/)
  * [NGINX](https://www.nginx.com/)
  * [Prometheus](https://prometheus.io/)
  * [Grafana](https://grafana.com/)
<br>

![containers](lab.drawio.png)

## Funkce

Na NGINX OSS web serverech je publikována jednoduchá aplikace, která má na všech WS stejný index.html, ale rozdílné obrázky. Každý NGINX OSS publikuje statistiky, které jsou vyčítány nginx-exporter kontejnerem a předávány do Prometheusu. Dále node-exporter vyčítá data o stroji, kde běží a cadvisor detailní informace o kontejnerech. Veškerá data se shromažďují v Prometheusu, odkud je vyčítá a zobrazuje Grafana.

## Prerekvizity
  * Docker
  * Docker-compose

## Použití

Klon repozitáře:
```
git clone https://github.com/jiridoubek/lab-env
```

Nebo stažení a rozbalení:
```
curl https://github.com/jiridoubek/lab-env/archive/master.zip
uzip master.zip
```

Start projektu:
```
docker-compose up
```
## Ubuntu from scratch
### Docker-CE
```
sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | 

sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io

sudo usermod -aG docker your-user
```
logout \
login
### Docker-compose
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.26.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose --version
```

### Ansible
```
sudo apt install python3-pip

sudo pip3 install ansible
```
## ARM

202008 - nginx prometheus exporter je v docker hubu zkompilovaný jen pro amd64. Pokud je potřeba spustit na jiné architektuře:
```
git clone https://github.com/nginxinc/nginx-prometheus-exporter.git
cd nginx-prometheus-exporter/
make container
```

---

## TODO
  * grafana dashboards
  * github
  * jenkins
  * nginx https

