# Installation und Konfiguration

## 1. Testumgebung

Das Projekt läuft in einer virtuellen Maschine mit Ubuntu Server.

| Komponente | Konfiguration |
|---|---|
| Betriebssystem | Ubuntu Server 22.04.5 LTS |
| Virtualisierung | Oracle VirtualBox |
| Checkmk | Community 2.5.0p14 |
| Docker | Installiert |
| Monitoring-IP | 192.168.10.10 |
| Checkmk-Weboberfläche | Port 5000 |
| Nginx-Webserver | Port 8080 |

## 2. Docker überprüfen

Installierte Docker-Version anzeigen:

```bash
docker --version
```

Laufende Container anzeigen:

```bash
sudo docker ps
```

Alle Container einschließlich gestoppter Container anzeigen:

```bash
sudo docker ps -a
```

## 3. Nginx testen

Die HTTP-Erreichbarkeit des Webservers kann mit folgendem Befehl geprüft werden:

```bash
curl -I http://192.168.10.10:8080/
```

Eine erfolgreiche Antwort enthält beispielsweise:

```text
HTTP/1.1 200 OK
Server: nginx
```

## 4. Checkmk-Docker-Plugin

Das Docker-Plugin wurde im Agent-Plugin-Verzeichnis installiert:

```text
/usr/lib/check_mk_agent/plugins/mk_docker.py
```

Die Docker-Daten des Agenten können folgendermaßen geprüft werden:

```bash
sudo check_mk_agent | grep '^<<<docker'
```

## 5. Ergebnis

Checkmk erkennt den Docker-Daemon und die vorhandenen Container. Die HTTP-Prüfung des Nginx-Webservers meldet HTTP 200 OK.

Hinweis: Die beschriebenen Tests wurden in der lokalen virtuellen Laborumgebung durchgeführt.
