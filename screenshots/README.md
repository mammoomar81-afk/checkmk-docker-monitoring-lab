# Screenshots – Checkmk Docker Monitoring Lab

## 1. Checkmk Host-Übersicht
Zeigt die überwachten Hosts und den Status ihrer Dienste.

Datei: `01-checkmk-host-overview.png`

## 2. Nginx HTTP – OK
Zeigt die erfolgreiche HTTP-Prüfung des Nginx-Webservers mit Status `200 OK`.

Datei: `02-nginx-http-check-ok.png`

## 3. Nginx HTTP – CRIT
Der Nginx-Container wurde kontrolliert gestoppt. Checkmk erkennt den Ausfall und meldet `CRIT` mit `Connection refused`.

Datei: `03-nginx-http-check-crit.png`

## 4. Nginx HTTP – Wiederherstellung
Nach dem Neustart des Nginx-Containers wird die HTTP-Erreichbarkeit erneut geprüft. Erwarteter Status: `OK`, HTTP `200 OK`.

Datei: `04-nginx-http-check-recovery.png`
