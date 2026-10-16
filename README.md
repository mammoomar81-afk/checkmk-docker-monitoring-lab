
# Checkmk Docker Monitoring Lab

## Projektbeschreibung

In diesem Projekt baue ich eine Linux-basierte Monitoring-Umgebung mit Ubuntu Server, Checkmk und Docker auf.

Ziel ist es, den Zustand des Linux-Servers und seiner Docker-Container zu überwachen. Zusätzlich wird die HTTP-Erreichbarkeit eines Nginx-Webservers geprüft.

## Technische Umgebung

- **Betriebssystem:** Ubuntu Server 22.04.5 LTS
- **Monitoring:** Checkmk Community 2.5.0p14
- **Container-Plattform:** Docker
- **Webserver:** Nginx (`nginx:alpine`)
- **Virtualisierung:** Oracle VirtualBox
- **Netzwerk:** NAT und Host-only-Netzwerk

## Umgesetzte Funktionen

- Installation und Konfiguration von Docker
- Betrieb eines Nginx-Webservers in einem Docker-Container
- Installation des Checkmk-Agent-Plugins für Docker
- Überwachung des Docker-Daemons und der Container
- Überwachung der Speicherbelegung von Docker-Images und Containern
- HTTP-Verfügbarkeitsprüfung des Nginx-Webservers
- Überwachung von CPU, Arbeitsspeicher, Dateisystemen und Netzwerkschnittstellen

## Aktueller Projektstatus

Die grundlegende Monitoring-Umgebung ist eingerichtet.

Checkmk erkennt den Docker-Daemon und zwei Container. Der Nginx-Container läuft und die HTTP-Prüfung liefert den Status `200 OK`.

Der Container `hello-world` wurde erfolgreich ausgeführt und anschließend regulär beendet.

## Geplante Erweiterungen

- Kontrollierter Ausfalltest des Nginx-Containers
- Überprüfung der Alarmierung in Checkmk
- Dokumentation der Fehlerbehebung und Wiederherstellung
- Ergänzung von Screenshots und Konfigurationsbeispielen

## Lernziele

- Linux-Serveradministration
- Docker und Containerverwaltung
- IT-Monitoring mit Checkmk
- Netzwerkdiagnose und Fehleranalyse
- Technische Dokumentation im Bereich Systemintegration

## Autor

Mammoomar

GitHub: [@mammoomar81-afk](https://github.com/mammoomar81-afk)
