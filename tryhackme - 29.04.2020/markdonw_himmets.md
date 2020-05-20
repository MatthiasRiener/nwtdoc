Dieses File war ursprünglich ein .docx File

sudo openvpn - -config openvpnfile

Passwort für Tryhackme.com YHLy6Zvb%CQyinF

**Nmap ip | tee nmap-standard** scannt hosts

**Nmap - -script vul -p PORTS IP | tee nmap-vuln** gibt hosts aus, welche hosts wo verwundbar sind

![](src/1.png)

![](src/2.png)

![](src/3.png)

**Mashine is volnerable to ms17-010**

![](src/4.png)

![](src/5.png)

**Rhost – remote host- der host, der angegriffen wird über die vm**

**Nach dem Befehl „run&quot; ist man der Windowsconsole**

![](src/6.png)

**Nice**

**Mit Controll Z wird Windows in den Hintergrund gegeben**

![](src/7.png)

**Session upgraden**

![](src/8.png)

![](src/9.png)

**System ist nun in Session**

**Mit sessions -i 2 kann man mit der session interagieren**

**Mit ps kann man sich alle prozesse anzeigen lassen**

![](src/10.png)

**Prozess 1288 hat richtigen eigenschaften für migrate**

**Mit hashdump werden Passwörter ausgegeben**

**Das Passwort von Jon schreiben wir uns in die datei jon.hash**

![](src/11.png)

**Mit**![](src/12.png) **wird der Hash auf klassische Passwörter überprüft. Die Datei mit klassichen Passwörtern heißt rockyou.txt**

![](src/13.png)