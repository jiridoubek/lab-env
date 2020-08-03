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

## Použití

Klon repozitáře:<br>
<code>
git clone https://github.com/jiridoubek/lab-env
</code>
<br><br>
Nebo stažení a rozbalení:<br>
<code>
curl https://github.com/jiridoubek/lab-env/archive/master.zip<br>
uzip master.zip
</code>





