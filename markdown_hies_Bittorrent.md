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
  
````
mkdir metasploitable3-workspace
cd metasploitable3-workspace
Invoke-WebRequest -Uri "https://raw.githubusercontent.com/rapid7/metasploitable3/master/Vagrantfile" -OutFile "Vagrantfile"
vagrant up
````
