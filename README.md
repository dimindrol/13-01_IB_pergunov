# Домашнее задание к занятию "Уязвимости и атаки на информационные системы" - Пергунов Д.В

### Задание 1



<details>

<summary>1. Просканировали Хост с помощью команды NMAP  </summary>

```
pergunovdv@debian:~$ nmap -A 192.168.0.2  
Starting Nmap 7.93 ( https://nmap.org ) at 2024-07-18 19:59 +05  
Nmap scan report for 192.168.0.2  
Host is up (0.016s latency).  
Not shown: 977 closed tcp ports (conn-refused)  
PORT     STATE SERVICE     VERSION  
21/tcp   open  ftp         vsftpd 2.3.4  
| ftp-syst:   
|   STAT:   
| FTP server status:  
|      Connected to 192.168.0.5  
|      Logged in as ftp  
|      TYPE: ASCII  
|      No session bandwidth limit  
|      Session timeout in seconds is 300  
|      Control connection is plain text  
|      Data connections will be plain text  
|      vsFTPd 2.3.4 - secure, fast, stable  
|_End of status  
|_ftp-anon: Anonymous FTP login allowed (FTP code 230)  
22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)  
| ssh-hostkey:   
|   1024 600fcfe1c05f6a74d69024fac4d56ccd (DSA)  
|_  2048 5656240f211ddea72bae61b1243de8f3 (RSA)  
23/tcp   open  telnet      Linux telnetd  
25/tcp   open  smtp        Postfix smtpd  
|_ssl-date: 2024-07-18T14:50:04+00:00; -9m32s from scanner time.  
|_smtp-commands: metasploitable.localdomain, PIPELINING, SIZE 10240000, VRFY, ETRN, STARTTLS, ENHANCEDSTATUSCODES, 8BITMIME, DSN  
| sslv2:   
|   SSLv2 supported  
|   ciphers:   
|     SSL2_RC2_128_CBC_WITH_MD5  
|     SSL2_RC2_128_CBC_EXPORT40_WITH_MD5  
|     SSL2_RC4_128_EXPORT40_WITH_MD5  
|     SSL2_DES_64_CBC_WITH_MD5  
|     SSL2_RC4_128_WITH_MD5  
|_    SSL2_DES_192_EDE3_CBC_WITH_MD5  
53/tcp   open  domain      ISC BIND 9.4.2  
| dns-nsid:   
|_  bind.version: 9.4.2  
80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)  
|_http-server-header: Apache/2.2.8 (Ubuntu) DAV/2  
|_http-title: Metasploitable2 - Linux  
111/tcp  open  rpcbind     2 (RPC #100000)  
| rpcinfo:   
|   program version    port/proto  service  
|   100000  2            111/tcp   rpcbind  
|   100000  2            111/udp   rpcbind  
|   100003  2,3,4       2049/tcp   nfs  
|   100003  2,3,4       2049/udp   nfs  
|   100005  1,2,3      34707/udp   mountd  
|   100005  1,2,3      46616/tcp   mountd  
|   100021  1,3,4      44038/udp   nlockmgr  
|   100021  1,3,4      48397/tcp   nlockmgr  
|   100024  1          47794/tcp   status  
|_  100024  1          59917/udp   status  
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)  
445/tcp  open  netbios-ssn Samba smbd 3.0.20-Debian (workgroup: WORKGROUP)  
512/tcp  open  exec        netkit-rsh rexecd  
513/tcp  open  login  
514/tcp  open  tcpwrapped  
1099/tcp open  java-rmi    GNU Classpath grmiregistry  
1524/tcp open  bindshell   Metasploitable root shell  
2049/tcp open  nfs         2-4 (RPC #100003)  
2121/tcp open  ftp         ProFTPD 1.3.1  
3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5  
| mysql-info:   
|   Protocol: 10  
|   Version: 5.0.51a-3ubuntu5  
|   Thread ID: 9  
|   Capabilities flags: 43564  
|   Some Capabilities: ConnectWithDatabase, SupportsCompression, Support41Auth, LongColumnFlag, SupportsTransactions, SwitchToSSLAfterHandshake, Speaks41ProtocolNew  
|   Status: Autocommit  
|_  Salt: <\;RkCK2U7Rvz$>MJk[h  
5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7  
|_ssl-date: 2024-07-18T14:50:04+00:00; -9m32s from scanner time.  
5900/tcp open  vnc         VNC (protocol 3.3)  
| vnc-info:   
|   Protocol version: 3.3  
|   Security types:   
|_    VNC Authentication (2)  
6000/tcp open  X11         (access denied)  
6667/tcp open  irc         UnrealIRCd  
| irc-info:   
|   users: 1  
|   servers: 1  
|   lusers: 1  
|   lservers: 0  
|   server: irc.Metasploitable.LAN  
|   version: Unreal3.2.8.1. irc.Metasploitable.LAN   
|   uptime: 0 days, 0:07:27  
|   source ident: nmap  
|   source host: 562C9222.F0D9233E.FFFA6D49.IP  
|_  error: Closing Link: pftoslzrm[192.168.0.5] (Quit: pftoslzrm)  
8009/tcp open  ajp13       Apache Jserv (Protocol v1.3)  
|_ajp-methods: Failed to get a valid response for the OPTION request  
8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1  
|_http-server-header: Apache-Coyote/1.1  
|_http-favicon: Apache Tomcat  
|_http-title: Apache Tomcat/5.5  
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel  

Host script results:  
| smb-security-mode:   
|   account_used: guest  
|   authentication_level: user  
|   challenge_response: supported  
|_  message_signing: disabled (dangerous, but default)  
| smb-os-discovery:   
|   OS: Unix (Samba 3.0.20-Debian)  
|   Computer name: metasploitable  
|   NetBIOS computer name:   
|   Domain name: localdomain  
|   FQDN: metasploitable.localdomain  
|_  System time: 2024-07-18T10:50:01-04:00  
|_clock-skew: mean: 50m31s, deviation: 2h00m02s, median: -9m32s  
|_nbstat: NetBIOS name: METASPLOITABLE, NetBIOS user: <unknown>, NetBIOS MAC: 000000000000 (Xerox)  
|_smb2-time: Protocol negotiation failed (SMB2)  

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .  
Nmap done: 1 IP address (1 host up) scanned in 24.17 seconds  
```
</details>


<details>
<summary>2. Следующие сетевые службы разрешены:</summary>

```
21/tcp   open  ftp         vsftpd 2.3.4  
22/tcp   open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)  
23/tcp   open  telnet      Linux telnetd  
25/tcp   open  smtp        Postfix smtpd 
53/tcp   open  domain      ISC BIND 9.4.2 
80/tcp   open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)  
111/tcp  open  rpcbind     2 (RPC #100000)
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)  
445/tcp  open  netbios-ssn Samba smbd 3.0.20-Debian (workgroup: WORKGROUP)  
512/tcp  open  exec        netkit-rsh rexecd  
513/tcp  open  login  
514/tcp  open  tcpwrapped  
1099/tcp open  java-rmi    GNU Classpath grmiregistry  
1524/tcp open  bindshell   Metasploitable root shell  
2049/tcp open  nfs         2-4 (RPC #100003)  
2121/tcp open  ftp         ProFTPD 1.3.1  
3306/tcp open  mysql       MySQL 5.0.51a-3ubuntu5 
5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7  
5900/tcp open  vnc         VNC (protocol 3.3) 
6000/tcp open  X11         (access denied)  
6667/tcp open  irc         UnrealIRCd 
8009/tcp open  ajp13       Apache Jserv (Protocol v1.3) 
8180/tcp open  http        Apache Tomcat/Coyote JSP engine 1.1 
```

</details>


<details>
<summary>3. Уязвимости и ссылки на них:</summary>
139/tcp  open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)  

Проблема касается серверного компонента "integer overflow in nttrans reply". Уязвимость возникает из-за неправильной обработки целочисленных значений при чтении списка расширенных атрибутов (EA list) из входящего сетевого буфера. Когда серверный демон Samba читает этот список, существует возможность произойти переполнению целочисленного значения (integer overflow), что ведет к удаленному отказу в обслуживании (DoS) или даже к выполнению произвольного кода.  
[Samba 3.5.22/3.6.17/4.0.8 - nttrans Reply Integer Overflow](https://www.exploit-db.com/exploits/27778)  
1099/tcp open  java-rmi    GNU Classpath grmiregistry   
Уязвимость позволяет удаленно выполнять код.    
[OpenNMS - Java Object Unserialization Remote Code Execution (Metasploit)](https://www.exploit-db.com/exploits/40610)    
5432/tcp open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7    
Уязвимость PostgreSQL 8.3.6 в обработке кодировок при конвертации удаленной отказ в обслуживании (DoS) является проблемой безопасности, затрагивающей систему управления базами данных PostgreSQL. Эта уязвимость позволяет злоумышленнику удаленно вызвать отказ в обслуживании сервера PostgreSQL, отправляя специально сформированные запросы, связанные с конвертацией кодировок.  
[PostgreSQL 8.3.6 - Conversion Encoding Remote Denial of Service)](https://www.exploit-db.com/exploits/32849)   
</details>



### Задание 2

Проведем сканирование Metasploitable в режимах SYN, FIN, Xmas, UDP.

<details>
<summary>1.Сканирование в режиме TCP SYN </summary>

```
sudo nmap -sS 192.168.0.2
Starting Nmap 7.93 ( https://nmap.org ) at 2024-07-19 18:17 +05
Nmap scan report for 192.168.0.2
Host is up (0.0074s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE SERVICE
21/tcp   open  ftp
22/tcp   open  ssh
23/tcp   open  telnet
25/tcp   open  smtp
53/tcp   open  domain
80/tcp   open  http
111/tcp  open  rpcbind
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
512/tcp  open  exec
513/tcp  open  login
514/tcp  open  shell
1099/tcp open  rmiregistry
1524/tcp open  ingreslock
2049/tcp open  nfs
2121/tcp open  ccproxy-ftp
3306/tcp open  mysql
5432/tcp open  postgresql
5900/tcp open  vnc
6000/tcp open  X11
6667/tcp open  irc
8009/tcp open  ajp13
8180/tcp open  unknown
MAC Address: 08:00:27:18:EE:BD (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 7.02 seconds
```

<details>
<summary>ДАМП Tshark</summary>

```
 1521 6.813962806  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9010 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1522 6.814018727  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1093 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1523 6.814074749  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8084 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1524 6.814130210  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 49175 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1525 6.814186260  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1259 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1526 6.814249992  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 85 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1527 6.814307083  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9485 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1528 6.814363383  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3000 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1529 6.816591600  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2161 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1530 6.816862155  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2033 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1531 6.817128520  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 109 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1532 6.817395264  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7402 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1533 6.817659749  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8652 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1534 6.817924782  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 544 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1535 6.818189857  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8022 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1536 6.818455122  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1096 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1537 6.818742757  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 15000 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1538 6.819146243  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 38292 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1539 6.819410148  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1123 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1540 6.819675422  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9101 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1541 6.819940136  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9898 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1542 6.820204201  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9091 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1543 6.820507216  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 636 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1544 6.820794291  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 50389 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1545 6.821060805  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6112 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1546 6.821373980  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 33 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1547 6.821654975  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 616 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1548 6.821925629  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 40193 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1549 6.822196793  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6566 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1550 6.822468228  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2126 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1551 6.822893796  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 514 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1552 6.823164869  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3006 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1553 6.823434204  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 12000 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1554 6.823703749  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 52869 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1555 6.823973613  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1863 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1556 6.824243968  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9002 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1557 6.824697566  192.168.0.2 → 192.168.0.5  TCP 60 1088 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1558 6.824697776  192.168.0.2 → 192.168.0.5  TCP 60 4998 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1559 6.824697846  192.168.0.2 → 192.168.0.5  TCP 60 5859 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1560 6.824995020  192.168.0.2 → 192.168.0.5  TCP 60 89 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1561 6.824995230  192.168.0.2 → 192.168.0.5  TCP 60 1147 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1562 6.824995300  192.168.0.2 → 192.168.0.5  TCP 60 5810 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1563 6.825290746  192.168.0.2 → 192.168.0.5  TCP 60 3493 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1564 6.825290966  192.168.0.2 → 192.168.0.5  TCP 60 1334 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1565 6.825291036  192.168.0.2 → 192.168.0.5  TCP 60 32771 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1566 6.825291106  192.168.0.2 → 192.168.0.5  TCP 60 2013 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1567 6.825585920  192.168.0.2 → 192.168.0.5  TCP 60 8010 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1568 6.825586130  192.168.0.2 → 192.168.0.5  TCP 60 8181 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1569 6.825586200  192.168.0.2 → 192.168.0.5  TCP 60 2366 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1570 6.825879986  192.168.0.2 → 192.168.0.5  TCP 60 9594 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1571 6.825880196  192.168.0.2 → 192.168.0.5  TCP 60 5987 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1572 6.825880266  192.168.0.2 → 192.168.0.5  TCP 60 1001 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1573 6.826174121  192.168.0.2 → 192.168.0.5  TCP 60 1169 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1574 6.826174341  192.168.0.2 → 192.168.0.5  TCP 60 1036 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1575 6.826174410  192.168.0.2 → 192.168.0.5  TCP 60 1149 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1576 6.826174480  192.168.0.2 → 192.168.0.5  TCP 60 1047 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1577 6.826468436  192.168.0.2 → 192.168.0.5  TCP 60 60443 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1578 6.826468656  192.168.0.2 → 192.168.0.5  TCP 60 9917 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1579 6.826468726  192.168.0.2 → 192.168.0.5  TCP 60 32776 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1580 6.826911402  192.168.0.2 → 192.168.0.5  TCP 60 16012 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1581 6.826911603  192.168.0.2 → 192.168.0.5  TCP 60 3268 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1582 6.826911673  192.168.0.2 → 192.168.0.5  TCP 60 15004 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1583 6.826911743  192.168.0.2 → 192.168.0.5  TCP 60 5907 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1584 6.826911812  192.168.0.2 → 192.168.0.5  TCP 60 1063 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1585 6.827209728  192.168.0.2 → 192.168.0.5  TCP 60 3007 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1586 6.827209948  192.168.0.2 → 192.168.0.5  TCP 60 911 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1587 6.827210018  192.168.0.2 → 192.168.0.5  TCP 60 42 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1588 6.827210088  192.168.0.2 → 192.168.0.5  TCP 60 1600 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1589 6.827503722  192.168.0.2 → 192.168.0.5  TCP 60 10024 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1590 6.827503922  192.168.0.2 → 192.168.0.5  TCP 60 212 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1591 6.827503992  192.168.0.2 → 192.168.0.5  TCP 60 1461 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1592 6.827797078  192.168.0.2 → 192.168.0.5  TCP 60 1092 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1593 6.827797288  192.168.0.2 → 192.168.0.5  TCP 60 2381 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1594 6.827797358  192.168.0.2 → 192.168.0.5  TCP 60 1914 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1595 6.827797428  192.168.0.2 → 192.168.0.5  TCP 60 2190 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1596 6.828090993  192.168.0.2 → 192.168.0.5  TCP 60 1138 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1597 6.828091202  192.168.0.2 → 192.168.0.5  TCP 60 9593 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1598 6.828091273  192.168.0.2 → 192.168.0.5  TCP 60 7938 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1599 6.828384487  192.168.0.2 → 192.168.0.5  TCP 60 9010 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1600 6.828384707  192.168.0.2 → 192.168.0.5  TCP 60 1093 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1601 6.828384777  192.168.0.2 → 192.168.0.5  TCP 60 8084 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1602 6.828679552  192.168.0.2 → 192.168.0.5  TCP 60 49175 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1603 6.828679773  192.168.0.2 → 192.168.0.5  TCP 60 1259 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1604 6.828679842  192.168.0.2 → 192.168.0.5  TCP 60 85 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1605 6.828679912  192.168.0.2 → 192.168.0.5  TCP 60 9485 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1606 6.828974867  192.168.0.2 → 192.168.0.5  TCP 60 3000 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1607 6.828975077  192.168.0.2 → 192.168.0.5  TCP 60 2161 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1608 6.828975147  192.168.0.2 → 192.168.0.5  TCP 60 2033 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1609 6.829321534  192.168.0.2 → 192.168.0.5  TCP 60 109 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1610 6.829321814  192.168.0.2 → 192.168.0.5  TCP 60 7402 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1611 6.829321884  192.168.0.2 → 192.168.0.5  TCP 60 8652 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1612 6.829321953  192.168.0.2 → 192.168.0.5  TCP 60 544 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1613 6.829620198  192.168.0.2 → 192.168.0.5  TCP 60 8022 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1614 6.829620408  192.168.0.2 → 192.168.0.5  TCP 60 1096 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1615 6.829620478  192.168.0.2 → 192.168.0.5  TCP 60 15000 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1616 6.829913613  192.168.0.2 → 192.168.0.5  TCP 60 38292 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1617 6.829913824  192.168.0.2 → 192.168.0.5  TCP 60 1123 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1618 6.829913894  192.168.0.2 → 192.168.0.5  TCP 60 9101 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1619 6.829913963  192.168.0.2 → 192.168.0.5  TCP 60 9898 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1620 6.830210288  192.168.0.2 → 192.168.0.5  TCP 60 9091 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1621 6.830210498  192.168.0.2 → 192.168.0.5  TCP 60 636 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1622 6.830210568  192.168.0.2 → 192.168.0.5  TCP 60 50389 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1623 6.830498202  192.168.0.2 → 192.168.0.5  TCP 60 6112 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1624 6.830498413  192.168.0.2 → 192.168.0.5  TCP 60 33 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1625 6.830498483  192.168.0.2 → 192.168.0.5  TCP 60 616 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1626 6.830765757  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8100 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1627 6.830828389  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7443 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1628 6.830886119  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 32768 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1629 6.830944520  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6689 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1630 6.830979261  192.168.0.2 → 192.168.0.5  TCP 60 40193 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1631 6.830979471  192.168.0.2 → 192.168.0.5  TCP 60 6566 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1632 6.830979551  192.168.0.2 → 192.168.0.5  TCP 60 2126 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1633 6.830979611  192.168.0.2 → 192.168.0.5  TCP 60 514 → 48606 [SYN, ACK] Seq=0 Ack=1 Win=5840 Len=0 MSS=1460
 1634 6.830979691  192.168.0.2 → 192.168.0.5  TCP 60 3006 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1635 6.830979761  192.168.0.2 → 192.168.0.5  TCP 60 12000 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1636 6.830993301  192.168.0.5 → 192.168.0.2  TCP 54 48606 → 514 [RST] Seq=1 Win=0 Len=0
 1637 6.831051643  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2034 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1638 6.831350137  192.168.0.2 → 192.168.0.5  TCP 60 52869 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1639 6.831350347  192.168.0.2 → 192.168.0.5  TCP 60 1863 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1640 6.831350417  192.168.0.2 → 192.168.0.5  TCP 60 9002 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1641 6.831350487  192.168.0.2 → 192.168.0.5  TCP 60 8100 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1642 6.831645152  192.168.0.2 → 192.168.0.5  TCP 60 7443 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1643 6.831645361  192.168.0.2 → 192.168.0.5  TCP 60 32768 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1644 6.831645472  192.168.0.2 → 192.168.0.5  TCP 60 6689 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1645 6.831986758  192.168.0.2 → 192.168.0.5  TCP 60 2034 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1646 6.832118050  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7937 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1647 6.832180611  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 10003 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1648 6.832236621  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9503 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1649 6.832351194  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1046 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1650 6.832408234  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 13 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1651 6.832465946  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5100 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1652 6.832522637  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 800 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1653 6.832579968  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 70 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1654 6.832636289  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6779 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1655 6.832693329  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7777 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1656 6.832727181  192.168.0.2 → 192.168.0.5  TCP 60 7937 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1657 6.832727390  192.168.0.2 → 192.168.0.5  TCP 60 10003 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1658 6.832727460  192.168.0.2 → 192.168.0.5  TCP 60 9503 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1659 6.832749681  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1687 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1660 6.832805851  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6100 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1661 6.832862042  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7002 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1662 6.832918213  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6502 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1663 6.832975115  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2382 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1664 6.833018754  192.168.0.2 → 192.168.0.5  TCP 60 1046 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1665 6.833018975  192.168.0.2 → 192.168.0.5  TCP 60 13 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1666 6.833019044  192.168.0.2 → 192.168.0.5  TCP 60 5100 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1667 6.833031925  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2191 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1668 6.833087656  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8085 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1669 6.833144066  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 10778 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1670 6.833200897  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 50636 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1671 6.833257489  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8193 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1672 6.833309881  192.168.0.2 → 192.168.0.5  TCP 60 800 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1673 6.833310090  192.168.0.2 → 192.168.0.5  TCP 60 70 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1674 6.833310160  192.168.0.2 → 192.168.0.5  TCP 60 6779 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1675 6.833314260  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5560 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1676 6.833371161  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1688 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1677 6.833428391  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5051 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1678 6.833480953  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1533 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1679 6.833537684  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9944 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1680 6.833601225  192.168.0.2 → 192.168.0.5  TCP 60 7777 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1681 6.833601445  192.168.0.2 → 192.168.0.5  TCP 60 1687 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1682 6.833601515  192.168.0.2 → 192.168.0.5  TCP 60 6100 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1683 6.833594394  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6669 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1684 6.833650675  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1084 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1685 6.833707516  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 49167 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1686 6.833764018  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 54328 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1687 6.833820819  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 280 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1688 6.833893400  192.168.0.2 → 192.168.0.5  TCP 60 7002 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1689 6.833893610  192.168.0.2 → 192.168.0.5  TCP 60 6502 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1690 6.833893680  192.168.0.2 → 192.168.0.5  TCP 60 2382 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1691 6.833893750  192.168.0.2 → 192.168.0.5  TCP 60 2191 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1692 6.833876619  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8009 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1693 6.833934330  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3580 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1694 6.833990422  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 21571 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1695 6.834046742  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4002 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1696 6.834103263  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 34572 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1697 6.834160133  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3889 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1698 6.834189355  192.168.0.2 → 192.168.0.5  TCP 60 8085 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1699 6.834189564  192.168.0.2 → 192.168.0.5  TCP 60 10778 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1700 6.834189634  192.168.0.2 → 192.168.0.5  TCP 60 50636 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1701 6.834215695  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6789 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1702 6.834272056  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 45100 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1703 6.834329616  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2065 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1704 6.834386517  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3546 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1705 6.834443549  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8290 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1706 6.834480819  192.168.0.2 → 192.168.0.5  TCP 60 8193 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1707 6.834481039  192.168.0.2 → 192.168.0.5  TCP 60 5560 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1708 6.834481109  192.168.0.2 → 192.168.0.5  TCP 60 1688 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1709 6.834500010  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1165 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1710 6.834669722  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 27352 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1711 6.834727673  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1027 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1712 6.834787374  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1055 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1713 6.834844015  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1714 6.834905517  192.168.0.2 → 192.168.0.5  TCP 60 5051 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1715 6.834905737  192.168.0.2 → 192.168.0.5  TCP 60 1533 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1716 6.834905817  192.168.0.2 → 192.168.0.5  TCP 60 9944 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1717 6.834905887  192.168.0.2 → 192.168.0.5  TCP 60 6669 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1718 6.834905967  192.168.0.2 → 192.168.0.5  TCP 60 1084 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1719 6.834900316  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1082 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1720 6.834956708  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 16001 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1721 6.835013278  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4006 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1722 6.835069349  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1272 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1723 6.835212171  192.168.0.2 → 192.168.0.5  TCP 60 49167 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1724 6.835212382  192.168.0.2 → 192.168.0.5  TCP 60 54328 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1725 6.835212451  192.168.0.2 → 192.168.0.5  TCP 60 280 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1726 6.835508957  192.168.0.2 → 192.168.0.5  TCP 60 8009 → 48606 [SYN, ACK] Seq=0 Ack=1 Win=5840 Len=0 MSS=1460
 1727 6.835509167  192.168.0.2 → 192.168.0.5  TCP 60 3580 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1728 6.835509247  192.168.0.2 → 192.168.0.5  TCP 60 21571 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1729 6.835509317  192.168.0.2 → 192.168.0.5  TCP 60 4002 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1730 6.835567148  192.168.0.5 → 192.168.0.2  TCP 54 48606 → 8009 [RST] Seq=1 Win=0 Len=0
 1731 6.835900153  192.168.0.2 → 192.168.0.5  TCP 60 34572 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1732 6.835900363  192.168.0.2 → 192.168.0.5  TCP 60 3889 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1733 6.835900433  192.168.0.2 → 192.168.0.5  TCP 60 6789 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1734 6.835900503  192.168.0.2 → 192.168.0.5  TCP 60 45100 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1735 6.836255569  192.168.0.2 → 192.168.0.5  TCP 60 2065 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1736 6.836255799  192.168.0.2 → 192.168.0.5  TCP 60 3546 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1737 6.836255889  192.168.0.2 → 192.168.0.5  TCP 60 8290 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1738 6.836255959  192.168.0.2 → 192.168.0.5  TCP 60 1165 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1739 6.836771858  192.168.0.2 → 192.168.0.5  TCP 60 27352 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1740 6.836772077  192.168.0.2 → 192.168.0.5  TCP 60 1027 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1741 6.836772148  192.168.0.2 → 192.168.0.5  TCP 60 1055 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1742 6.836772218  192.168.0.2 → 192.168.0.5  TCP 60 3 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1743 6.836772287  192.168.0.2 → 192.168.0.5  TCP 60 1082 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1744 6.836772357  192.168.0.2 → 192.168.0.5  TCP 60 16001 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1745 6.837113873  192.168.0.2 → 192.168.0.5  TCP 60 4006 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1746 6.837114084  192.168.0.2 → 192.168.0.5  TCP 60 1272 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1747 6.837210635  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1032 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1748 6.837273816  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2179 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1749 6.837330807  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 49156 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1750 6.837492810  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8008 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1751 6.837550831  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9102 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1752 6.837615732  192.168.0.2 → 192.168.0.5  TCP 60 1032 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1753 6.837607702  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7920 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1754 6.837664003  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 65389 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1755 6.837720244  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 16113 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1756 6.837776715  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2170 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1757 6.837832855  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5730 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1758 6.837908506  192.168.0.2 → 192.168.0.5  TCP 60 2179 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1759 6.837908706  192.168.0.2 → 192.168.0.5  TCP 60 49156 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1760 6.837908777  192.168.0.2 → 192.168.0.5  TCP 60 8008 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1761 6.837908847  192.168.0.2 → 192.168.0.5  TCP 60 9102 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1762 6.837888817  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8500 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1763 6.837945748  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8600 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1764 6.838001628  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 548 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1765 6.838056309  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8300 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1766 6.838111681  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1556 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1767 6.838168481  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 61532 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1768 6.838203742  192.168.0.2 → 192.168.0.5  TCP 60 7920 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1769 6.838203952  192.168.0.2 → 192.168.0.5  TCP 60 65389 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1770 6.838204022  192.168.0.2 → 192.168.0.5  TCP 60 16113 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1771 6.838223902  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5000 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1772 6.838279153  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8011 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1773 6.838335143  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5001 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1774 6.838395595  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 10243 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1775 6.838451476  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1076 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1776 6.838503217  192.168.0.2 → 192.168.0.5  TCP 60 2170 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1777 6.838503426  192.168.0.2 → 192.168.0.5  TCP 60 5730 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1778 6.838503496  192.168.0.2 → 192.168.0.5  TCP 60 8500 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1779 6.838507487  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2608 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1780 6.838682640  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 10621 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1781 6.838739361  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3390 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1782 6.838795102  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9011 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1783 6.838851323  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 981 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1784 6.838907703  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2288 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1785 6.838963784  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9040 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1786 6.839015185  192.168.0.2 → 192.168.0.5  TCP 60 8600 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1787 6.839015395  192.168.0.2 → 192.168.0.5  TCP 60 548 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1788 6.839015465  192.168.0.2 → 192.168.0.5  TCP 60 8300 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1789 6.839015545  192.168.0.2 → 192.168.0.5  TCP 60 1556 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1790 6.839015615  192.168.0.2 → 192.168.0.5  TCP 60 61532 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1791 6.839015685  192.168.0.2 → 192.168.0.5  TCP 60 5000 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1792 6.839020286  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1201 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1793 6.839076047  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1073 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1794 6.839132868  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1217 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1795 6.839188839  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1066 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1796 6.839244749  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 999 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1797 6.839315730  192.168.0.2 → 192.168.0.5  TCP 60 8011 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1798 6.839315941  192.168.0.2 → 192.168.0.5  TCP 60 5001 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1799 6.839316011  192.168.0.2 → 192.168.0.5  TCP 60 10243 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1800 6.839316080  192.168.0.2 → 192.168.0.5  TCP 60 1076 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1801 6.839300360  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5221 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1802 6.839382822  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8031 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1803 6.839439812  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4224 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1804 6.839496104  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7201 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1805 6.839552284  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2121 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1806 6.839610505  192.168.0.2 → 192.168.0.5  TCP 60 2608 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1807 6.839610705  192.168.0.2 → 192.168.0.5  TCP 60 10621 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1808 6.839610775  192.168.0.2 → 192.168.0.5  TCP 60 3390 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1809 6.839607055  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1080 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1810 6.839663116  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5631 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1811 6.839723267  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9080 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1812 6.839779078  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8994 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1813 6.839835719  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1010 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1814 6.839903769  192.168.0.2 → 192.168.0.5  TCP 60 9011 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1815 6.839903981  192.168.0.2 → 192.168.0.5  TCP 60 981 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1816 6.839904051  192.168.0.2 → 192.168.0.5  TCP 60 2288 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1817 6.839904120  192.168.0.2 → 192.168.0.5  TCP 60 9040 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1818 6.839892270  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5666 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1819 6.839971282  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 49157 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1820 6.840028472  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9877 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1821 6.840084623  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3324 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1822 6.840141414  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 416 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1823 6.840196675  192.168.0.2 → 192.168.0.5  TCP 60 1201 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1824 6.840196874  192.168.0.2 → 192.168.0.5  TCP 60 1073 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1825 6.840196945  192.168.0.2 → 192.168.0.5  TCP 60 1217 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1826 6.840197236  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2522 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1827 6.840253136  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9418 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1828 6.840487410  192.168.0.2 → 192.168.0.5  TCP 60 1066 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1829 6.840487619  192.168.0.2 → 192.168.0.5  TCP 60 999 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1830 6.840487689  192.168.0.2 → 192.168.0.5  TCP 60 5221 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1831 6.840821234  192.168.0.2 → 192.168.0.5  TCP 60 8031 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1832 6.840821445  192.168.0.2 → 192.168.0.5  TCP 60 4224 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1833 6.840821515  192.168.0.2 → 192.168.0.5  TCP 60 7201 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1834 6.840821584  192.168.0.2 → 192.168.0.5  TCP 60 2121 → 48606 [SYN, ACK] Seq=0 Ack=1 Win=5840 Len=0 MSS=1460
 1835 6.840880586  192.168.0.5 → 192.168.0.2  TCP 54 48606 → 2121 [RST] Seq=1 Win=0 Len=0
 1836 6.841210832  192.168.0.2 → 192.168.0.5  TCP 60 1080 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1837 6.841211042  192.168.0.2 → 192.168.0.5  TCP 60 5631 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1838 6.841211112  192.168.0.2 → 192.168.0.5  TCP 60 9080 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1839 6.841211182  192.168.0.2 → 192.168.0.5  TCP 60 8994 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1840 6.841552207  192.168.0.2 → 192.168.0.5  TCP 60 1010 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1841 6.841552427  192.168.0.2 → 192.168.0.5  TCP 60 5666 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1842 6.841552497  192.168.0.2 → 192.168.0.5  TCP 60 49157 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1843 6.841552567  192.168.0.2 → 192.168.0.5  TCP 60 9877 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1844 6.841894593  192.168.0.2 → 192.168.0.5  TCP 60 3324 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1845 6.841894794  192.168.0.2 → 192.168.0.5  TCP 60 416 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1846 6.841894864  192.168.0.2 → 192.168.0.5  TCP 60 2522 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1847 6.841894933  192.168.0.2 → 192.168.0.5  TCP 60 9418 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1848 6.842004795  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 10180 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1849 6.842067945  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5225 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1850 6.842124707  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1875 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1851 6.842180689  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 79 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1852 6.842238058  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9111 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1853 6.842293679  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2107 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1854 6.842349741  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6692 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1855 6.842406822  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5431 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1856 6.842462442  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 481 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1857 6.842598565  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4662 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1858 6.842654366  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4899 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1859 6.842710886  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3998 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1860 6.842767038  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5101 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1861 6.842822548  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 987 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1862 6.842879659  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 51103 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1863 6.842935581  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1783 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1864 6.842991872  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 22939 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1865 6.843047743  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2010 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1866 6.843103443  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8654 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1867 6.843158524  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4550 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1868 6.843214425  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 16016 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1869 6.843271006  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 14442 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1870 6.843326417  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9900 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1871 6.843383088  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1974 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1872 6.843439059  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 15660 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1873 6.843495680  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 714 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1874 6.843551381  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2383 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1875 6.843607712  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7019 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1876 6.843664273  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 50002 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1877 6.843719923  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6699 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1878 6.843775995  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 179 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1879 6.843832096  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9998 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1880 6.843887957  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1056 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1881 6.843956978  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 13782 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1882 6.844013448  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3367 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1883 6.844069780  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 31337 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1884 6.844125060  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2869 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1885 6.844180521  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5925 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1886 6.844236362  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2602 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1887 6.844292333  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5718 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1888 6.844348294  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5998 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1889 6.844405435  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 32774 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1890 6.844462096  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6839 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1891 6.844517658  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1057 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1892 6.844573898  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 49155 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1893 6.844630578  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7103 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1894 6.844687741  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5903 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1895 6.844743591  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5910 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1896 6.844799902  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 57294 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1897 6.844862113  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8045 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1898 6.847560498  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 687 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1899 6.847627500  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3971 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1900 6.847685730  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3269 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1901 6.847743151  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3351 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1902 6.847801601  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2725 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1903 6.847859884  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4444 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1904 6.847920084  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3918 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1905 6.847983935  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1007 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1906 6.848072535  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 465 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1907 6.848132397  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7627 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1908 6.848188348  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 20 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1909 6.848244939  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 5904 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1910 6.848300959  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2998 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1911 6.848357601  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1062 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1912 6.848413652  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1121 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1913 6.848469792  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3878 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1914 6.848526664  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 19780 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1915 6.848583355  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 10012 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1916 6.848639566  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1024 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1917 6.848695337  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1087 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1918 6.848751167  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 7100 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1919 6.848807158  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2967 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1920 6.848865470  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 3168 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1921 6.848921130  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 8089 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1922 6.848978581  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2030 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1923 6.849034792  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 648 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1924 6.849092094  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9575 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1925 6.849148064  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 50500 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1926 6.849204445  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 6346 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1927 6.849260205  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1131 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1928 6.849318388  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2021 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1929 6.849377109  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 4242 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1930 6.849432789  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1931 6.849489590  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 543 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1932 6.849545501  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1054 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1933 6.849601542  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9500 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 1934 6.854728858  192.168.0.2 → 192.168.0.5  TCP 60 10180 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1935 6.854729068  192.168.0.2 → 192.168.0.5  TCP 60 5225 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1936 6.854729138  192.168.0.2 → 192.168.0.5  TCP 60 1875 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1937 6.854729208  192.168.0.2 → 192.168.0.5  TCP 60 79 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1938 6.854729278  192.168.0.2 → 192.168.0.5  TCP 60 9111 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1939 6.855221526  192.168.0.2 → 192.168.0.5  TCP 60 2107 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1940 6.855221755  192.168.0.2 → 192.168.0.5  TCP 60 6692 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1941 6.855221825  192.168.0.2 → 192.168.0.5  TCP 60 5431 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1942 6.855221896  192.168.0.2 → 192.168.0.5  TCP 60 481 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1943 6.855221975  192.168.0.2 → 192.168.0.5  TCP 60 4662 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1944 6.855222056  192.168.0.2 → 192.168.0.5  TCP 60 4899 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1945 6.855523361  192.168.0.2 → 192.168.0.5  TCP 60 3998 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1946 6.855523561  192.168.0.2 → 192.168.0.5  TCP 60 5101 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1947 6.855523631  192.168.0.2 → 192.168.0.5  TCP 60 987 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1948 6.855523701  192.168.0.2 → 192.168.0.5  TCP 60 51103 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1949 6.855956958  192.168.0.2 → 192.168.0.5  TCP 60 1783 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1950 6.855957168  192.168.0.2 → 192.168.0.5  TCP 60 22939 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1951 6.855957238  192.168.0.2 → 192.168.0.5  TCP 60 2010 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1952 6.855957308  192.168.0.2 → 192.168.0.5  TCP 60 8654 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1953 6.855957379  192.168.0.2 → 192.168.0.5  TCP 60 4550 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1954 6.856311055  192.168.0.2 → 192.168.0.5  TCP 60 16016 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1955 6.856311264  192.168.0.2 → 192.168.0.5  TCP 60 14442 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1956 6.856311345  192.168.0.2 → 192.168.0.5  TCP 60 9900 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1957 6.856311415  192.168.0.2 → 192.168.0.5  TCP 60 1974 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1958 6.856658890  192.168.0.2 → 192.168.0.5  TCP 60 15660 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1959 6.856659110  192.168.0.2 → 192.168.0.5  TCP 60 714 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1960 6.856659180  192.168.0.2 → 192.168.0.5  TCP 60 2383 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1961 6.856659251  192.168.0.2 → 192.168.0.5  TCP 60 7019 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1962 6.857006446  192.168.0.2 → 192.168.0.5  TCP 60 50002 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1963 6.857006656  192.168.0.2 → 192.168.0.5  TCP 60 6699 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1964 6.857006726  192.168.0.2 → 192.168.0.5  TCP 60 179 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1965 6.857006796  192.168.0.2 → 192.168.0.5  TCP 60 9998 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1966 6.857361602  192.168.0.2 → 192.168.0.5  TCP 60 1056 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1967 6.857361812  192.168.0.2 → 192.168.0.5  TCP 60 13782 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1968 6.857361883  192.168.0.2 → 192.168.0.5  TCP 60 3367 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1969 6.857361952  192.168.0.2 → 192.168.0.5  TCP 60 31337 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1970 6.857710138  192.168.0.2 → 192.168.0.5  TCP 60 2869 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1971 6.857710358  192.168.0.2 → 192.168.0.5  TCP 60 5925 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1972 6.857710469  192.168.0.2 → 192.168.0.5  TCP 60 2602 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1973 6.857710539  192.168.0.2 → 192.168.0.5  TCP 60 5718 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1974 6.858169236  192.168.0.2 → 192.168.0.5  TCP 60 5998 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1975 6.858169436  192.168.0.2 → 192.168.0.5  TCP 60 32774 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1976 6.858169506  192.168.0.2 → 192.168.0.5  TCP 60 6839 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1977 6.858169577  192.168.0.2 → 192.168.0.5  TCP 60 1057 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1978 6.858169646  192.168.0.2 → 192.168.0.5  TCP 60 49155 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1979 6.858720655  192.168.0.2 → 192.168.0.5  TCP 60 7103 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1980 6.858720875  192.168.0.2 → 192.168.0.5  TCP 60 5903 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1981 6.858720945  192.168.0.2 → 192.168.0.5  TCP 60 5910 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1982 6.858721055  192.168.0.2 → 192.168.0.5  TCP 60 57294 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1983 6.859085571  192.168.0.2 → 192.168.0.5  TCP 60 8045 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1984 6.859085781  192.168.0.2 → 192.168.0.5  TCP 60 687 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1985 6.859085861  192.168.0.2 → 192.168.0.5  TCP 60 3971 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1986 6.859085931  192.168.0.2 → 192.168.0.5  TCP 60 3269 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1987 6.859086001  192.168.0.2 → 192.168.0.5  TCP 60 3351 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1988 6.859086081  192.168.0.2 → 192.168.0.5  TCP 60 2725 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1989 6.859086151  192.168.0.2 → 192.168.0.5  TCP 60 4444 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1990 6.859464017  192.168.0.2 → 192.168.0.5  TCP 60 3918 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1991 6.859464227  192.168.0.2 → 192.168.0.5  TCP 60 1007 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1992 6.859464297  192.168.0.2 → 192.168.0.5  TCP 60 465 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1993 6.859464407  192.168.0.2 → 192.168.0.5  TCP 60 7627 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1994 6.859803002  192.168.0.2 → 192.168.0.5  TCP 60 20 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1995 6.859803212  192.168.0.2 → 192.168.0.5  TCP 60 5904 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1996 6.859803283  192.168.0.2 → 192.168.0.5  TCP 60 2998 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1997 6.859803353  192.168.0.2 → 192.168.0.5  TCP 60 1062 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1998 6.860146689  192.168.0.2 → 192.168.0.5  TCP 60 1121 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 1999 6.860146898  192.168.0.2 → 192.168.0.5  TCP 60 3878 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2000 6.860146969  192.168.0.2 → 192.168.0.5  TCP 60 19780 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2001 6.860147039  192.168.0.2 → 192.168.0.5  TCP 60 10012 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2002 6.860488774  192.168.0.2 → 192.168.0.5  TCP 60 1024 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2003 6.860488983  192.168.0.2 → 192.168.0.5  TCP 60 1087 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2004 6.860489054  192.168.0.2 → 192.168.0.5  TCP 60 7100 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2005 6.860489124  192.168.0.2 → 192.168.0.5  TCP 60 2967 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2006 6.860831760  192.168.0.2 → 192.168.0.5  TCP 60 3168 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2007 6.860831971  192.168.0.2 → 192.168.0.5  TCP 60 8089 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2008 6.860832040  192.168.0.2 → 192.168.0.5  TCP 60 2030 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2009 6.860832110  192.168.0.2 → 192.168.0.5  TCP 60 648 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2010 6.861175445  192.168.0.2 → 192.168.0.5  TCP 60 9575 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2011 6.861175656  192.168.0.2 → 192.168.0.5  TCP 60 50500 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2012 6.861175726  192.168.0.2 → 192.168.0.5  TCP 60 6346 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2013 6.861175795  192.168.0.2 → 192.168.0.5  TCP 60 1131 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2014 6.861515681  192.168.0.2 → 192.168.0.5  TCP 60 2021 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2015 6.861515902  192.168.0.2 → 192.168.0.5  TCP 60 4242 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2016 6.861515971  192.168.0.2 → 192.168.0.5  TCP 60 9 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2017 6.861516041  192.168.0.2 → 192.168.0.5  TCP 60 543 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2018 6.861856317  192.168.0.2 → 192.168.0.5  TCP 60 1054 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2019 6.861856537  192.168.0.2 → 192.168.0.5  TCP 60 9500 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2020 6.861963578  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 2008 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 2021 6.862026870  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 9878 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 2022 6.862083900  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 1164 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 2023 6.862199703  192.168.0.5 → 192.168.0.2  TCP 58 48606 → 646 [SYN] Seq=0 Win=1024 Len=0 MSS=1460
 2024 6.862569579  192.168.0.2 → 192.168.0.5  TCP 60 2008 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2025 6.862569799  192.168.0.2 → 192.168.0.5  TCP 60 9878 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2026 6.863070968  192.168.0.2 → 192.168.0.5  TCP 60 1164 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2027 6.863071178  192.168.0.2 → 192.168.0.5  TCP 60 646 → 48606 [RST, ACK] Seq=1 Ack=1 Win=0 Len=0
 2028 18.077036866 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 2029 18.077053216 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 2030 52.297707963  192.168.0.2 → 192.168.0.255 BROWSER 286 Host Announcement METASPLOITABLE, Workstation, Server, Print Queue Server, Xenix Server, NT Workstation, NT Server, Potential Browser
^Ctshark: 
2030 packets captured
```
</details>
</details>


