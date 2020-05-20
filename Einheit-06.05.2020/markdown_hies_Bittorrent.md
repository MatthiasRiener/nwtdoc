# **Mitschrift**
#### **Datum: 06.05.2020**
### **Thema: BitTorrent**
---
## Split-Kommand
---
## Orf-Beitrag 
---
## **Main-Part** 

### Downloads
- [Vagrant](https://www.vagrantup.com/downloads.html)
- [Git Repo Metasploitable3](https://github.com/rapid7/metasploitable3.git)
### Anleitung 
- [Anleitung](https://liberty-shell.com/sec/2018/07/08/install-ms3/)


Richtige Anleitung
````
mkdir metasploitable3-workspace
cd metasploitable3-workspace
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/rapid7/metasploitable3/master/Vagrantfile" -OutFile "Vagrantfile"
vagrant up
````
Alles in der Powershell eingeben

## Weiter sind wir nicht am Vormittag gekommen
---
# Nachmittag

1. msfconsole
2. neuer tab
3. ip a
4. ls -l 
5. nmap -sV -sC --script vuln -oN dsofsdf.nmap 
6. db_status
7. workspace -a msp3win
8. db_nmap 192.168.0.130 
9. db_nmap 192.168.0.130  -p 8484, 8585
10. 