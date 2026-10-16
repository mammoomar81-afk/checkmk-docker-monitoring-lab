Fehleranalyse und Wiederherstellung
Ziel des Tests
Mit diesem Test wird überprüft, ob Checkmk den Ausfall eines Nginx-Webservers erkennt und die erfolgreiche Wiederherstellung der HTTP-Erreichbarkeit anzeigt.

Testumgebung
Monitoring: Checkmk Community 2.5.0p14
Betriebssystem: Ubuntu Server 22.04.5 LTS
Container: Docker
Webserver: Nginx (nginx:alpine)
HTTP-Port: 8080
Durchführung
1. Webserver stoppen
Der Nginx-Container wurde kontrolliert gestoppt:

sudo docker stop webserver
2. Fehlererkennung durch Checkmk
Checkmk erkannte, dass der Webserver nicht mehr über HTTP erreichbar war.

Service: HTTP Docker Nginx HTTP
Status: CRIT
Fehlermeldung: Connection refused
Ursache: Der HTTP-Endpunkt auf Port 8080 war nicht erreichbar.
3. Webserver wieder starten
Der Container wurde anschließend wieder gestartet:

sudo docker start webserver
Die HTTP-Erreichbarkeit wurde überprüft:

curl -I http://192.168.10.10:8080/
4. Ergebnis der Wiederherstellung
Checkmk zeigte nach der Wiederherstellung wieder den Status OK an.

Die HTTP-Prüfung lieferte die Antwort HTTP/1.1 200 OK.

Ergebnis
Der Test war erfolgreich. Checkmk erkannte den kontrollierten Ausfall des Nginx-Webservers und zeigte nach dem Neustart die erfolgreiche Wiederherstellung an.

Damit wurde die grundlegende HTTP-Überwachung einschließlich Fehlererkennung und Wiederherstellung erfolgreich getestet.

Gelernte Kompetenzen
Docker-Container kontrolliert stoppen und starten
HTTP-Erreichbarkeit mit curl überprüfen
Monitoring-Status CRIT und OK interpretieren
Fehlermeldungen analysieren
Fehlerbehebung und Testergebnisse technisch dokumentieren
