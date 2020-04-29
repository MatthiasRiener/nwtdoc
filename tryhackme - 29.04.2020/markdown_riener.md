# 29.04.2020 - Mitschrift
## Rechtliches zu Hacking

Beim unerlaubten Eindringen in Computernetzwerke droht eine Haftstrafe von bis zu 3 Jahren. Dies bezieht sich auch auf die Störung der Funktionsfähigkeit eines Computersystem.

## Zugriff auf eine Computersystem
Wer sich zu einem Computersystem, über das er keine Verfügung hat, einen Zugang verschafft, dem drohen bis zu 6 Monaten Haft oder einer Geldstrafe. 

Wer die Tat auf ein Computersystem, welches ein Teil einer kritischen Infrastruktur ist, begeht, dem drohen bis zu zwei Jahren Haft.

Wer die Tat im Rahmen einer kriminellen Vereinigung begeht, dem drohen bis zu drei Jahren Haft. 

## Datenbeschädigung
Wer andere durch eine Datenzerstörung schädigt, dem drohen bis zu sechs Monaten Haft oder eine Geldstrafe. 

Wenn die Strafe über 5000 Euro hoch ist, drohen einem bis zu zwei Jahre Haft.

Wer einen Schaden über 300 000 Euro herführt, eine kritische Infrastruktur beeinträchtigt, oder die Tat als Mitglied einer kriminelle Vereinigung begeht, dem drohen bis zu 5 Jahre Haft.

## Störung der Funktionsfähigkeit
Stört man die Funktionsfähigkeit eines Computers durch einen Angriff, so drohen einem bis zu sechs Monate Haft oder eine Geldstrafe. 

Führt man einer länger andauernde Störung herbei, so droht eine Freiheitsstrafe von bis zu zwei Jahren.

Wer einen Schaden über 300 000 Euro herführt, eine kritische Infrastruktur beeinträchtigt, oder die Tat als Mitglied einer kriminelle Vereinigung begeht, dem drohen bis zu 5 Jahre Haft.

## Missbrauch von Daten
Wer im Zusammenhang der Beschaffung der Daten einen Missbrauch der Zugangsdaten herführt, dem Drohen bis zu sechs Monate oder eine Geldstrafe. 

## Zustimmung
Ich, Matthias Riener, wurde über die rechtlichen Rahmenbedingungen und Konsequenzen aufgeklärt, und nehme diese im Falle einer Straftat auf mich.


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