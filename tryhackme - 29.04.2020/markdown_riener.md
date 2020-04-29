# 29.04.2020 - Mitschrift
## Rechtliches zu Hacking

Beim unerlaubten Eindringen in Computernetzwerke droht eine Haftstrafe von bis zu 3 Jahren. Dies bezieht sich auch auf die Störung der Funktionsfähigkeit eines Computersystem.

### Rechtsgrundlagen
- [118a Strafgesetzbuch (StGB)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10002296&Paragraf=118a)
- [126a - 126c Strafegesetzbuch (StGB)](https://www.ris.bka.gv.at/Ergebnis.wxe?Abfrage=Bundesnormen&Kundmachungsorgan=&Index=&Titel=StGB&Gesetzesnummer=&VonArtikel=&BisArtikel=&VonParagraf=126a&BisParagraf=126c&)


---
## Sonnleitner Video

Zum Testen wie im Video muss man sich auf [tryhackme](https://tryhackme.com) registrieren.
Als nächstes muss eine OpenVPN Verbindung mit tryhackme aufgebaut werden, um später in verschiedenen Räumen arbeiten zu können.

---
## Connection aufbauen

Auf [tryhackme.com/access](https://tryhackme.com/access) kann das fertige OpenVPN Konfigurationsfile gedownloadet werden. 

Mit dem Befehl kann eine VPN Verbindung aufgebaut werden:
```
sudo openvpn MatthiasRiener.opvn &
  => Connection Erfolgreich
``` 
Nun kann man auf der Access-Page die Connection Informationen einsehen.
![Connection details](./src_riener/network_connection.png)

## Connection testing
```
ip a

=> unter der Auflistung sollte auch eine Verbindung mit *tun* sein.
  => tun, OpenVPN tunnel Verbindung => erfolgreich
```
 
 ## Network Scanning
 ```
nmap ip | tte nmap-standard
  => 1000 meist verwendeten ports scannen und mit tee weitergeleitet
```
## Genaueres Scanning
```
nmap --script vuln -p 135,139,445 10.10.211.133 | tee nmap-vuln
 => Genauerer Schwachstellenscan für die Ports 135,139,445
    Die Ports 135,139,445 weisen darauf, dass es sich um Ports handelt, die unter Windows verwendet werdenn.
```