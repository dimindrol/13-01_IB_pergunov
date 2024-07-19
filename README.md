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
<summary>Дамп Tshark</summary>

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
2030 packets captured
```
</details>
</details>

<details>
<summary>2. TCP FIN-сканирование </summary>

```
sudo nmap -sF 192.168.0.2
Starting Nmap 7.93 ( https://nmap.org ) at 2024-07-19 19:30 +05
Nmap scan report for 192.168.0.2
Host is up (0.0020s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE         SERVICE
21/tcp   open|filtered ftp
22/tcp   open|filtered ssh
23/tcp   open|filtered telnet
25/tcp   open|filtered smtp
53/tcp   open|filtered domain
80/tcp   open|filtered http
111/tcp  open|filtered rpcbind
139/tcp  open|filtered netbios-ssn
445/tcp  open|filtered microsoft-ds
512/tcp  open|filtered exec
513/tcp  open|filtered login
514/tcp  open|filtered shell
1099/tcp open|filtered rmiregistry
1524/tcp open|filtered ingreslock
2049/tcp open|filtered nfs
2121/tcp open|filtered ccproxy-ftp
3306/tcp open|filtered mysql
5432/tcp open|filtered postgresql
5900/tcp open|filtered vnc
6000/tcp open|filtered X11
6667/tcp open|filtered irc
8009/tcp open|filtered ajp13
8180/tcp open|filtered unknown
MAC Address: 08:00:27:18:EE:BD (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 1.69 seconds
```

<details>
<summary>Дамп Tshark</summary>

```
 1494 1.366188596  192.168.0.2 → 192.168.0.5  TCP 60 1036 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1495 1.366529040  192.168.0.2 → 192.168.0.5  TCP 60 8007 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1496 1.366529250  192.168.0.2 → 192.168.0.5  TCP 60 55600 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1497 1.366529321  192.168.0.2 → 192.168.0.5  TCP 60 7496 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1498 1.366529391  192.168.0.2 → 192.168.0.5  TCP 60 1166 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1499 1.366885434  192.168.0.2 → 192.168.0.5  TCP 60 32781 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1500 1.366885655  192.168.0.2 → 192.168.0.5  TCP 60 2004 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1501 1.366885724  192.168.0.2 → 192.168.0.5  TCP 60 7200 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1502 1.366885794  192.168.0.2 → 192.168.0.5  TCP 60 5060 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1503 1.367471422  192.168.0.2 → 192.168.0.5  TCP 60 3301 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1504 1.367471621  192.168.0.2 → 192.168.0.5  TCP 60 1100 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1505 1.367471691  192.168.0.2 → 192.168.0.5  TCP 60 17988 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1506 1.367471762  192.168.0.2 → 192.168.0.5  TCP 60 2005 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1507 1.367471832  192.168.0.2 → 192.168.0.5  TCP 60 1106 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1508 1.367842697  192.168.0.2 → 192.168.0.5  TCP 60 10628 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1509 1.367842917  192.168.0.2 → 192.168.0.5  TCP 60 4444 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1510 1.367842986  192.168.0.2 → 192.168.0.5  TCP 60 50000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1511 1.367843056  192.168.0.2 → 192.168.0.5  TCP 60 3827 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1512 1.367843127  192.168.0.2 → 192.168.0.5  TCP 60 5910 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1513 1.367843197  192.168.0.2 → 192.168.0.5  TCP 60 9002 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1514 1.368253832  192.168.0.2 → 192.168.0.5  TCP 60 1311 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1515 1.368254052  192.168.0.2 → 192.168.0.5  TCP 60 1058 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1516 1.368254122  192.168.0.2 → 192.168.0.5  TCP 60 691 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1517 1.368254191  192.168.0.2 → 192.168.0.5  TCP 60 1801 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1518 1.368254261  192.168.0.2 → 192.168.0.5  TCP 60 2041 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1519 1.368526916  192.168.0.2 → 192.168.0.5  TCP 60 1117 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1520 1.368527125  192.168.0.2 → 192.168.0.5  TCP 60 6547 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1521 1.368527195  192.168.0.2 → 192.168.0.5  TCP 60 1296 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1522 1.368862909  192.168.0.2 → 192.168.0.5  TCP 60 1131 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1523 1.368863129  192.168.0.2 → 192.168.0.5  TCP 60 2196 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1524 1.368863199  192.168.0.2 → 192.168.0.5  TCP 60 2382 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1525 1.369258804  192.168.0.2 → 192.168.0.5  TCP 60 9900 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1526 1.369259014  192.168.0.2 → 192.168.0.5  TCP 60 144 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1527 1.369259084  192.168.0.2 → 192.168.0.5  TCP 60 1272 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1528 1.369259154  192.168.0.2 → 192.168.0.5  TCP 60 1108 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1529 1.369259224  192.168.0.2 → 192.168.0.5  TCP 60 543 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1530 1.369610378  192.168.0.2 → 192.168.0.5  TCP 60 1094 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1531 1.372124650  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8193 [FIN] Seq=1 Win=1024 Len=0
 1532 1.372187500  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 49154 [FIN] Seq=1 Win=1024 Len=0
 1533 1.372242961  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8085 [FIN] Seq=1 Win=1024 Len=0
 1534 1.372299052  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 50002 [FIN] Seq=1 Win=1024 Len=0
 1535 1.372354522  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1043 [FIN] Seq=1 Win=1024 Len=0
 1536 1.372411033  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1594 [FIN] Seq=1 Win=1024 Len=0
 1537 1.372465834  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9575 [FIN] Seq=1 Win=1024 Len=0
 1538 1.372522535  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6001 [FIN] Seq=1 Win=1024 Len=0
 1539 1.372577815  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1024 [FIN] Seq=1 Win=1024 Len=0
 1540 1.372632526  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5950 [FIN] Seq=1 Win=1024 Len=0
 1541 1.372688007  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7911 [FIN] Seq=1 Win=1024 Len=0
 1542 1.372743067  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7004 [FIN] Seq=1 Win=1024 Len=0
 1543 1.372798119  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 27356 [FIN] Seq=1 Win=1024 Len=0
 1544 1.372853509  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2910 [FIN] Seq=1 Win=1024 Len=0
 1545 1.372910250  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5000 [FIN] Seq=1 Win=1024 Len=0
 1546 1.373011540  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2968 [FIN] Seq=1 Win=1024 Len=0
 1547 1.373068261  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6788 [FIN] Seq=1 Win=1024 Len=0
 1548 1.373123952  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2021 [FIN] Seq=1 Win=1024 Len=0
 1549 1.373179332  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3077 [FIN] Seq=1 Win=1024 Len=0
 1550 1.373234523  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 58080 [FIN] Seq=1 Win=1024 Len=0
 1551 1.373289674  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7800 [FIN] Seq=1 Win=1024 Len=0
 1552 1.373345784  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3851 [FIN] Seq=1 Win=1024 Len=0
 1553 1.373401155  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1234 [FIN] Seq=1 Win=1024 Len=0
 1554 1.373457476  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4111 [FIN] Seq=1 Win=1024 Len=0
 1555 1.373512637  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5357 [FIN] Seq=1 Win=1024 Len=0
 1556 1.373569127  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7778 [FIN] Seq=1 Win=1024 Len=0
 1557 1.373624448  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1123 [FIN] Seq=1 Win=1024 Len=0
 1558 1.373679639  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8254 [FIN] Seq=1 Win=1024 Len=0
 1559 1.373734940  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9050 [FIN] Seq=1 Win=1024 Len=0
 1560 1.373790980  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3551 [FIN] Seq=1 Win=1024 Len=0
 1561 1.373845931  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9485 [FIN] Seq=1 Win=1024 Len=0
 1562 1.373901522  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5952 [FIN] Seq=1 Win=1024 Len=0
 1563 1.373980273  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 264 [FIN] Seq=1 Win=1024 Len=0
 1564 1.374036223  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5859 [FIN] Seq=1 Win=1024 Len=0
 1565 1.374092013  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2121 [FIN] Seq=1 Win=1024 Len=0
 1566 1.374148814  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 90 [FIN] Seq=1 Win=1024 Len=0
 1567 1.374203415  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6106 [FIN] Seq=1 Win=1024 Len=0
 1568 1.374258415  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2710 [FIN] Seq=1 Win=1024 Len=0
 1569 1.374313537  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4445 [FIN] Seq=1 Win=1024 Len=0
 1570 1.374369498  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6543 [FIN] Seq=1 Win=1024 Len=0
 1571 1.374424668  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 52848 [FIN] Seq=1 Win=1024 Len=0
 1572 1.374480969  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3325 [FIN] Seq=1 Win=1024 Len=0
 1573 1.374540309  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 700 [FIN] Seq=1 Win=1024 Len=0
 1574 1.374595900  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3000 [FIN] Seq=1 Win=1024 Len=0
 1575 1.374651331  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8009 [FIN] Seq=1 Win=1024 Len=0
 1576 1.374707622  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 15000 [FIN] Seq=1 Win=1024 Len=0
 1577 1.374763282  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9011 [FIN] Seq=1 Win=1024 Len=0
 1578 1.374818413  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1037 [FIN] Seq=1 Win=1024 Len=0
 1579 1.374874064  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4998 [FIN] Seq=1 Win=1024 Len=0
 1580 1.374938874  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 10243 [FIN] Seq=1 Win=1024 Len=0
 1581 1.379474880  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1972 [FIN] Seq=1 Win=1024 Len=0
 1582 1.379536961  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2601 [FIN] Seq=1 Win=1024 Len=0
 1583 1.379592272  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 11111 [FIN] Seq=1 Win=1024 Len=0
 1584 1.379648163  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6699 [FIN] Seq=1 Win=1024 Len=0
 1585 1.379705334  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4000 [FIN] Seq=1 Win=1024 Len=0
 1586 1.379762044  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 222 [FIN] Seq=1 Win=1024 Len=0
 1587 1.379817324  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1145 [FIN] Seq=1 Win=1024 Len=0
 1588 1.379872826  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5001 [FIN] Seq=1 Win=1024 Len=0
 1589 1.379927616  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 27715 [FIN] Seq=1 Win=1024 Len=0
 1590 1.379983607  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 625 [FIN] Seq=1 Win=1024 Len=0
 1591 1.380038797  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 19801 [FIN] Seq=1 Win=1024 Len=0
 1592 1.380093958  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 28201 [FIN] Seq=1 Win=1024 Len=0
 1593 1.380149370  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5221 [FIN] Seq=1 Win=1024 Len=0
 1594 1.380208120  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 125 [FIN] Seq=1 Win=1024 Len=0
 1595 1.380263500  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1233 [FIN] Seq=1 Win=1024 Len=0
 1596 1.382664090  192.168.0.2 → 192.168.0.5  TCP 60 88 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1597 1.382664301  192.168.0.2 → 192.168.0.5  TCP 60 5050 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1598 1.382664371  192.168.0.2 → 192.168.0.5  TCP 60 1328 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1599 1.383006285  192.168.0.2 → 192.168.0.5  TCP 60 10009 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1600 1.383006495  192.168.0.2 → 192.168.0.5  TCP 60 1098 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1601 1.383006564  192.168.0.2 → 192.168.0.5  TCP 60 12000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1602 1.383582272  192.168.0.2 → 192.168.0.5  TCP 60 18988 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1603 1.383582432  192.168.0.2 → 192.168.0.5  TCP 60 5500 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1604 1.383582502  192.168.0.2 → 192.168.0.5  TCP 60 2043 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1605 1.383582572  192.168.0.2 → 192.168.0.5  TCP 60 8800 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1606 1.383582642  192.168.0.2 → 192.168.0.5  TCP 60 19315 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1607 1.383582712  192.168.0.2 → 192.168.0.5  TCP 60 8383 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1608 1.383582782  192.168.0.2 → 192.168.0.5  TCP 60 648 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1609 1.383582861  192.168.0.2 → 192.168.0.5  TCP 60 6969 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1610 1.383964646  192.168.0.2 → 192.168.0.5  TCP 60 8193 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1611 1.383964856  192.168.0.2 → 192.168.0.5  TCP 60 49154 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1612 1.383964926  192.168.0.2 → 192.168.0.5  TCP 60 8085 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1613 1.383964996  192.168.0.2 → 192.168.0.5  TCP 60 50002 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1614 1.384307280  192.168.0.2 → 192.168.0.5  TCP 60 1043 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1615 1.384307500  192.168.0.2 → 192.168.0.5  TCP 60 1594 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1616 1.384307570  192.168.0.2 → 192.168.0.5  TCP 60 9575 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1617 1.384307641  192.168.0.2 → 192.168.0.5  TCP 60 6001 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1618 1.384649014  192.168.0.2 → 192.168.0.5  TCP 60 1024 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1619 1.384649225  192.168.0.2 → 192.168.0.5  TCP 60 5950 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1620 1.384649294  192.168.0.2 → 192.168.0.5  TCP 60 7911 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1621 1.384991369  192.168.0.2 → 192.168.0.5  TCP 60 7004 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1622 1.384991578  192.168.0.2 → 192.168.0.5  TCP 60 27356 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1623 1.384991649  192.168.0.2 → 192.168.0.5  TCP 60 2910 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1624 1.384991719  192.168.0.2 → 192.168.0.5  TCP 60 5000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1625 1.385330433  192.168.0.2 → 192.168.0.5  TCP 60 2968 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1626 1.385330653  192.168.0.2 → 192.168.0.5  TCP 60 6788 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1627 1.385330723  192.168.0.2 → 192.168.0.5  TCP 60 2021 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1628 1.385330793  192.168.0.2 → 192.168.0.5  TCP 60 3077 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1629 1.385657898  192.168.0.2 → 192.168.0.5  TCP 60 58080 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1630 1.385658117  192.168.0.2 → 192.168.0.5  TCP 60 7800 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1631 1.385658188  192.168.0.2 → 192.168.0.5  TCP 60 3851 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1632 1.385658258  192.168.0.2 → 192.168.0.5  TCP 60 1234 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1633 1.385996001  192.168.0.2 → 192.168.0.5  TCP 60 4111 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1634 1.385996212  192.168.0.2 → 192.168.0.5  TCP 60 5357 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1635 1.385996302  192.168.0.2 → 192.168.0.5  TCP 60 7778 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1636 1.385996372  192.168.0.2 → 192.168.0.5  TCP 60 1123 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1637 1.386429308  192.168.0.2 → 192.168.0.5  TCP 60 8254 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1638 1.386429517  192.168.0.2 → 192.168.0.5  TCP 60 9050 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1639 1.386429588  192.168.0.2 → 192.168.0.5  TCP 60 3551 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1640 1.386429658  192.168.0.2 → 192.168.0.5  TCP 60 9485 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1641 1.386429728  192.168.0.2 → 192.168.0.5  TCP 60 5952 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1642 1.386766051  192.168.0.2 → 192.168.0.5  TCP 60 264 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1643 1.386766281  192.168.0.2 → 192.168.0.5  TCP 60 5859 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1644 1.386766350  192.168.0.2 → 192.168.0.5  TCP 60 90 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1645 1.386766420  192.168.0.2 → 192.168.0.5  TCP 60 6106 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1646 1.387101695  192.168.0.2 → 192.168.0.5  TCP 60 2710 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1647 1.387101905  192.168.0.2 → 192.168.0.5  TCP 60 4445 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1648 1.387101975  192.168.0.2 → 192.168.0.5  TCP 60 6543 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1649 1.387579492  192.168.0.2 → 192.168.0.5  TCP 60 52848 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1650 1.387579701  192.168.0.2 → 192.168.0.5  TCP 60 3325 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1651 1.387579782  192.168.0.2 → 192.168.0.5  TCP 60 700 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1652 1.387579852  192.168.0.2 → 192.168.0.5  TCP 60 3000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1653 1.387579922  192.168.0.2 → 192.168.0.5  TCP 60 15000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1654 1.387579991  192.168.0.2 → 192.168.0.5  TCP 60 9011 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1655 1.387964445  192.168.0.2 → 192.168.0.5  TCP 60 1037 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1656 1.387964656  192.168.0.2 → 192.168.0.5  TCP 60 4998 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1657 1.387964726  192.168.0.2 → 192.168.0.5  TCP 60 10243 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1658 1.387964795  192.168.0.2 → 192.168.0.5  TCP 60 1972 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1659 1.388278210  192.168.0.2 → 192.168.0.5  TCP 60 2601 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1660 1.388278430  192.168.0.2 → 192.168.0.5  TCP 60 11111 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1661 1.388278500  192.168.0.2 → 192.168.0.5  TCP 60 6699 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1662 1.388278570  192.168.0.2 → 192.168.0.5  TCP 60 4000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1663 1.388613544  192.168.0.2 → 192.168.0.5  TCP 60 222 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1664 1.388613754  192.168.0.2 → 192.168.0.5  TCP 60 1145 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1665 1.388613824  192.168.0.2 → 192.168.0.5  TCP 60 5001 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1666 1.388948449  192.168.0.2 → 192.168.0.5  TCP 60 27715 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1667 1.388948678  192.168.0.2 → 192.168.0.5  TCP 60 625 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1668 1.388948748  192.168.0.2 → 192.168.0.5  TCP 60 19801 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1669 1.388948819  192.168.0.2 → 192.168.0.5  TCP 60 28201 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1670 1.389283943  192.168.0.2 → 192.168.0.5  TCP 60 5221 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1671 1.389284153  192.168.0.2 → 192.168.0.5  TCP 60 125 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1672 1.389284223  192.168.0.2 → 192.168.0.5  TCP 60 1233 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1673 1.391763603  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 12174 [FIN] Seq=1 Win=1024 Len=0
 1674 1.392031407  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1059 [FIN] Seq=1 Win=1024 Len=0
 1675 1.392255319  192.168.0.2 → 192.168.0.5  TCP 60 12174 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1676 1.392255530  192.168.0.2 → 192.168.0.5  TCP 60 1059 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1677 1.392579413  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 32782 [FIN] Seq=1 Win=1024 Len=0
 1678 1.392843377  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 61900 [FIN] Seq=1 Win=1024 Len=0
 1679 1.393068620  192.168.0.2 → 192.168.0.5  TCP 60 32782 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1680 1.393068829  192.168.0.2 → 192.168.0.5  TCP 60 61900 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1681 1.393392314  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4 [FIN] Seq=1 Win=1024 Len=0
 1682 1.393656687  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5101 [FIN] Seq=1 Win=1024 Len=0
 1683 1.393881950  192.168.0.2 → 192.168.0.5  TCP 60 4 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1684 1.393882170  192.168.0.2 → 192.168.0.5  TCP 60 5101 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1685 1.394205884  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1078 [FIN] Seq=1 Win=1024 Len=0
 1686 1.394471437  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1271 [FIN] Seq=1 Win=1024 Len=0
 1687 1.394696380  192.168.0.2 → 192.168.0.5  TCP 60 1078 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1688 1.394696589  192.168.0.2 → 192.168.0.5  TCP 60 1271 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1689 1.395020064  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 666 [FIN] Seq=1 Win=1024 Len=0
 1690 1.395283087  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5998 [FIN] Seq=1 Win=1024 Len=0
 1691 1.395651782  192.168.0.2 → 192.168.0.5  TCP 60 666 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1692 1.395651991  192.168.0.2 → 192.168.0.5  TCP 60 5998 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1693 1.395919025  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1011 [FIN] Seq=1 Win=1024 Len=0
 1694 1.395975326  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 20000 [FIN] Seq=1 Win=1024 Len=0
 1695 1.396029777  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5200 [FIN] Seq=1 Win=1024 Len=0
 1696 1.396083837  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8200 [FIN] Seq=1 Win=1024 Len=0
 1697 1.396138738  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1032 [FIN] Seq=1 Win=1024 Len=0
 1698 1.396193399  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 20 [FIN] Seq=1 Win=1024 Len=0
 1699 1.396247760  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5051 [FIN] Seq=1 Win=1024 Len=0
 1700 1.396302120  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 40911 [FIN] Seq=1 Win=1024 Len=0
 1701 1.396356711  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8701 [FIN] Seq=1 Win=1024 Len=0
 1702 1.396411392  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5009 [FIN] Seq=1 Win=1024 Len=0
 1703 1.396465802  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1122 [FIN] Seq=1 Win=1024 Len=0
 1704 1.396530194  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 458 [FIN] Seq=1 Win=1024 Len=0
 1705 1.396586884  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5810 [FIN] Seq=1 Win=1024 Len=0
 1706 1.396643425  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1864 [FIN] Seq=1 Win=1024 Len=0
 1707 1.396698415  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8400 [FIN] Seq=1 Win=1024 Len=0
 1708 1.396753796  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5003 [FIN] Seq=1 Win=1024 Len=0
 1709 1.396810226  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5925 [FIN] Seq=1 Win=1024 Len=0
 1710 1.396864988  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4045 [FIN] Seq=1 Win=1024 Len=0
 1711 1.396919608  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7000 [FIN] Seq=1 Win=1024 Len=0
 1712 1.396975348  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 749 [FIN] Seq=1 Win=1024 Len=0
 1713 1.397029720  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1021 [FIN] Seq=1 Win=1024 Len=0
 1714 1.397084149  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 79 [FIN] Seq=1 Win=1024 Len=0
 1715 1.397139340  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3300 [FIN] Seq=1 Win=1024 Len=0
 1716 1.397193851  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1183 [FIN] Seq=1 Win=1024 Len=0
 1717 1.397248521  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 13456 [FIN] Seq=1 Win=1024 Len=0
 1718 1.397304072  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 808 [FIN] Seq=1 Win=1024 Len=0
 1719 1.397358983  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5631 [FIN] Seq=1 Win=1024 Len=0
 1720 1.397413444  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1033 [FIN] Seq=1 Win=1024 Len=0
 1721 1.397468714  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1719 [FIN] Seq=1 Win=1024 Len=0
 1722 1.397524065  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8083 [FIN] Seq=1 Win=1024 Len=0
 1723 1.397578476  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2811 [FIN] Seq=1 Win=1024 Len=0
 1724 1.397632876  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9595 [FIN] Seq=1 Win=1024 Len=0
 1725 1.397687987  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 24444 [FIN] Seq=1 Win=1024 Len=0
 1726 1.397742898  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1805 [FIN] Seq=1 Win=1024 Len=0
 1727 1.397798228  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 617 [FIN] Seq=1 Win=1024 Len=0
 1728 1.397852420  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6789 [FIN] Seq=1 Win=1024 Len=0
 1729 1.397907100  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6779 [FIN] Seq=1 Win=1024 Len=0
 1730 1.397962391  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 32774 [FIN] Seq=1 Win=1024 Len=0
 1731 1.398016701  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1 [FIN] Seq=1 Win=1024 Len=0
 1732 1.398073452  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1113 [FIN] Seq=1 Win=1024 Len=0
 1733 1.398188793  192.168.0.2 → 192.168.0.5  TCP 60 1011 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1734 1.398188963  192.168.0.2 → 192.168.0.5  TCP 60 20000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1735 1.398189034  192.168.0.2 → 192.168.0.5  TCP 60 5200 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1736 1.398189104  192.168.0.2 → 192.168.0.5  TCP 60 8200 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1737 1.398189174  192.168.0.2 → 192.168.0.5  TCP 60 1032 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1738 1.398189243  192.168.0.2 → 192.168.0.5  TCP 60 20 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1739 1.398189313  192.168.0.2 → 192.168.0.5  TCP 60 5051 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1740 1.398189384  192.168.0.2 → 192.168.0.5  TCP 60 40911 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1741 1.398254654  192.168.0.2 → 192.168.0.5  TCP 60 8701 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1742 1.398254825  192.168.0.2 → 192.168.0.5  TCP 60 5009 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1743 1.398254894  192.168.0.2 → 192.168.0.5  TCP 60 1122 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1744 1.398254964  192.168.0.2 → 192.168.0.5  TCP 60 458 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1745 1.398255034  192.168.0.2 → 192.168.0.5  TCP 60 5810 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1746 1.398255104  192.168.0.2 → 192.168.0.5  TCP 60 1864 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1747 1.398255175  192.168.0.2 → 192.168.0.5  TCP 60 8400 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1748 1.398255245  192.168.0.2 → 192.168.0.5  TCP 60 5003 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1749 1.398303635  192.168.0.2 → 192.168.0.5  TCP 60 5925 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1750 1.398303795  192.168.0.2 → 192.168.0.5  TCP 60 4045 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1751 1.398303865  192.168.0.2 → 192.168.0.5  TCP 60 7000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1752 1.398303935  192.168.0.2 → 192.168.0.5  TCP 60 749 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1753 1.398304005  192.168.0.2 → 192.168.0.5  TCP 60 1021 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1754 1.398304075  192.168.0.2 → 192.168.0.5  TCP 60 79 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1755 1.398304145  192.168.0.2 → 192.168.0.5  TCP 60 3300 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1756 1.398304215  192.168.0.2 → 192.168.0.5  TCP 60 1183 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1757 1.398351546  192.168.0.2 → 192.168.0.5  TCP 60 13456 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1758 1.398718260  192.168.0.2 → 192.168.0.5  TCP 60 808 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1759 1.398718470  192.168.0.2 → 192.168.0.5  TCP 60 5631 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1760 1.398718540  192.168.0.2 → 192.168.0.5  TCP 60 1033 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1761 1.398718630  192.168.0.2 → 192.168.0.5  TCP 60 1719 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1762 1.399020755  192.168.0.2 → 192.168.0.5  TCP 60 8083 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1763 1.399020955  192.168.0.2 → 192.168.0.5  TCP 60 2811 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1764 1.399021024  192.168.0.2 → 192.168.0.5  TCP 60 9595 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1765 1.399021115  192.168.0.2 → 192.168.0.5  TCP 60 24444 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1766 1.399357219  192.168.0.2 → 192.168.0.5  TCP 60 1805 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1767 1.399357429  192.168.0.2 → 192.168.0.5  TCP 60 617 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1768 1.399357499  192.168.0.2 → 192.168.0.5  TCP 60 6789 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1769 1.399357569  192.168.0.2 → 192.168.0.5  TCP 60 6779 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1770 1.399819455  192.168.0.2 → 192.168.0.5  TCP 60 32774 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1771 1.399819675  192.168.0.2 → 192.168.0.5  TCP 60 1 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1772 1.399819745  192.168.0.2 → 192.168.0.5  TCP 60 1113 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1773 1.404047658  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2010 [FIN] Seq=1 Win=1024 Len=0
 1774 1.404110298  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 14441 [FIN] Seq=1 Win=1024 Len=0
 1775 1.404167488  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5298 [FIN] Seq=1 Win=1024 Len=0
 1776 1.404224750  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1217 [FIN] Seq=1 Win=1024 Len=0
 1777 1.404282731  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 880 [FIN] Seq=1 Win=1024 Len=0
 1778 1.404357881  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2718 [FIN] Seq=1 Win=1024 Len=0
 1779 1.404415572  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8087 [FIN] Seq=1 Win=1024 Len=0
 1780 1.404473302  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 27000 [FIN] Seq=1 Win=1024 Len=0
 1781 1.404531443  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 51493 [FIN] Seq=1 Win=1024 Len=0
 1782 1.404588594  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 990 [FIN] Seq=1 Win=1024 Len=0
 1783 1.404645295  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 12345 [FIN] Seq=1 Win=1024 Len=0
 1784 1.404702145  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6692 [FIN] Seq=1 Win=1024 Len=0
 1785 1.404759096  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5190 [FIN] Seq=1 Win=1024 Len=0
 1786 1.404816126  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 38292 [FIN] Seq=1 Win=1024 Len=0
 1787 1.404875077  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1580 [FIN] Seq=1 Win=1024 Len=0
 1788 1.404932838  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4279 [FIN] Seq=1 Win=1024 Len=0
 1789 1.405030989  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4321 [FIN] Seq=1 Win=1024 Len=0
 1790 1.405088870  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 179 [FIN] Seq=1 Win=1024 Len=0
 1791 1.405145061  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5907 [FIN] Seq=1 Win=1024 Len=0
 1792 1.405201521  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7676 [FIN] Seq=1 Win=1024 Len=0
 1793 1.405257042  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2020 [FIN] Seq=1 Win=1024 Len=0
 1794 1.405312753  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8002 [FIN] Seq=1 Win=1024 Len=0
 1795 1.405368493  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6792 [FIN] Seq=1 Win=1024 Len=0
 1796 1.405426164  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1164 [FIN] Seq=1 Win=1024 Len=0
 1797 1.405481605  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 548 [FIN] Seq=1 Win=1024 Len=0
 1798 1.405537966  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1213 [FIN] Seq=1 Win=1024 Len=0
 1799 1.405593866  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6567 [FIN] Seq=1 Win=1024 Len=0
 1800 1.405649007  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2909 [FIN] Seq=1 Win=1024 Len=0
 1801 1.405705038  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 18040 [FIN] Seq=1 Win=1024 Len=0
 1802 1.405761089  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2393 [FIN] Seq=1 Win=1024 Len=0
 1803 1.405826279  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 668 [FIN] Seq=1 Win=1024 Len=0
 1804 1.405882570  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5730 [FIN] Seq=1 Win=1024 Len=0
 1805 1.405938300  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3 [FIN] Seq=1 Win=1024 Len=0
 1806 1.405994632  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 555 [FIN] Seq=1 Win=1024 Len=0
 1807 1.406049902  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2099 [FIN] Seq=1 Win=1024 Len=0
 1808 1.406105893  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 10002 [FIN] Seq=1 Win=1024 Len=0
 1809 1.406162553  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1141 [FIN] Seq=1 Win=1024 Len=0
 1810 1.406217984  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7070 [FIN] Seq=1 Win=1024 Len=0
 1811 1.406273915  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1556 [FIN] Seq=1 Win=1024 Len=0
 1812 1.406329836  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3826 [FIN] Seq=1 Win=1024 Len=0
 1813 1.406385206  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5054 [FIN] Seq=1 Win=1024 Len=0
 1814 1.406440827  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 24 [FIN] Seq=1 Win=1024 Len=0
 1815 1.406496938  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5902 [FIN] Seq=1 Win=1024 Len=0
 1816 1.406552659  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 49158 [FIN] Seq=1 Win=1024 Len=0
 1817 1.406608769  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5862 [FIN] Seq=1 Win=1024 Len=0
 1818 1.406664600  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3476 [FIN] Seq=1 Win=1024 Len=0
 1819 1.406720070  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 19350 [FIN] Seq=1 Win=1024 Len=0
 1820 1.406789631  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5280 [FIN] Seq=1 Win=1024 Len=0
 1821 1.406846362  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1084 [FIN] Seq=1 Win=1024 Len=0
 1822 1.406902973  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5666 [FIN] Seq=1 Win=1024 Len=0
 1823 1.410396795  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 1099 [FIN] Seq=1 Win=1024 Len=0
 1824 1.410462046  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 33 [FIN] Seq=1 Win=1024 Len=0
 1825 1.410519716  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 49176 [FIN] Seq=1 Win=1024 Len=0
 1826 1.410581627  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6009 [FIN] Seq=1 Win=1024 Len=0
 1827 1.410639279  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4567 [FIN] Seq=1 Win=1024 Len=0
 1828 1.410697149  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 911 [FIN] Seq=1 Win=1024 Len=0
 1829 1.410754430  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 60020 [FIN] Seq=1 Win=1024 Len=0
 1830 1.410874190  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 16992 [FIN] Seq=1 Win=1024 Len=0
 1831 1.410932692  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1000 [FIN] Seq=1 Win=1024 Len=0
 1832 1.410988633  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 56738 [FIN] Seq=1 Win=1024 Len=0
 1833 1.411044713  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3800 [FIN] Seq=1 Win=1024 Len=0
 1834 1.411101084  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1839 [FIN] Seq=1 Win=1024 Len=0
 1835 1.411156255  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 27355 [FIN] Seq=1 Win=1024 Len=0
 1836 1.411212475  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2038 [FIN] Seq=1 Win=1024 Len=0
 1837 1.411268046  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1500 [FIN] Seq=1 Win=1024 Len=0
 1838 1.411323747  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 900 [FIN] Seq=1 Win=1024 Len=0
 1839 1.411378957  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 48080 [FIN] Seq=1 Win=1024 Len=0
 1840 1.411434798  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7 [FIN] Seq=1 Win=1024 Len=0
 1841 1.411580861  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9071 [FIN] Seq=1 Win=1024 Len=0
 1842 1.411637111  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1524 [FIN] Seq=1 Win=1024 Len=0
 1843 1.411692812  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3703 [FIN] Seq=1 Win=1024 Len=0
 1844 1.411748602  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1148 [FIN] Seq=1 Win=1024 Len=0
 1845 1.411803874  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4001 [FIN] Seq=1 Win=1024 Len=0
 1846 1.411859234  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5087 [FIN] Seq=1 Win=1024 Len=0
 1847 1.411914934  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1107 [FIN] Seq=1 Win=1024 Len=0
 1848 1.411970325  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6667 [FIN] Seq=1 Win=1024 Len=0
 1849 1.412026166  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9220 [FIN] Seq=1 Win=1024 Len=0
 1850 1.412083617  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 873 [FIN] Seq=1 Win=1024 Len=0
 1851 1.412139867  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 10566 [FIN] Seq=1 Win=1024 Len=0
 1852 1.412601384  192.168.0.2 → 192.168.0.5  TCP 60 2010 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1853 1.412601604  192.168.0.2 → 192.168.0.5  TCP 60 14441 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1854 1.412942298  192.168.0.2 → 192.168.0.5  TCP 60 5298 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1855 1.412942498  192.168.0.2 → 192.168.0.5  TCP 60 1217 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1856 1.412942569  192.168.0.2 → 192.168.0.5  TCP 60 880 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1857 1.412942648  192.168.0.2 → 192.168.0.5  TCP 60 2718 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1858 1.413287302  192.168.0.2 → 192.168.0.5  TCP 60 8087 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1859 1.413287513  192.168.0.2 → 192.168.0.5  TCP 60 27000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1860 1.413287582  192.168.0.2 → 192.168.0.5  TCP 60 51493 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1861 1.413622247  192.168.0.2 → 192.168.0.5  TCP 60 990 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1862 1.413622446  192.168.0.2 → 192.168.0.5  TCP 60 12345 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1863 1.413622517  192.168.0.2 → 192.168.0.5  TCP 60 6692 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1864 1.413622587  192.168.0.2 → 192.168.0.5  TCP 60 5190 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1865 1.413622666  192.168.0.2 → 192.168.0.5  TCP 60 38292 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1866 1.413957170  192.168.0.2 → 192.168.0.5  TCP 60 1580 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1867 1.416281179  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 512 [FIN] Seq=1 Win=1024 Len=0
 1868 1.416344600  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3011 [FIN] Seq=1 Win=1024 Len=0
 1869 1.416400510  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3261 [FIN] Seq=1 Win=1024 Len=0
 1870 1.416456271  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 27353 [FIN] Seq=1 Win=1024 Len=0
 1871 1.416512191  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 6646 [FIN] Seq=1 Win=1024 Len=0
 1872 1.416567913  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5678 [FIN] Seq=1 Win=1024 Len=0
 1873 1.416624123  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3071 [FIN] Seq=1 Win=1024 Len=0
 1874 1.416679804  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5679 [FIN] Seq=1 Win=1024 Len=0
 1875 1.416735614  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8873 [FIN] Seq=1 Win=1024 Len=0
 1876 1.416791696  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1053 [FIN] Seq=1 Win=1024 Len=0
 1877 1.416848366  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1028 [FIN] Seq=1 Win=1024 Len=0
 1878 1.416903797  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4443 [FIN] Seq=1 Win=1024 Len=0
 1879 1.416959338  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2701 [FIN] Seq=1 Win=1024 Len=0
 1880 1.417015578  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8081 [FIN] Seq=1 Win=1024 Len=0
 1881 1.417085409  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 593 [FIN] Seq=1 Win=1024 Len=0
 1882 1.417142670  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8008 [FIN] Seq=1 Win=1024 Len=0
 1883 1.420767295  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 5432 [FIN] Seq=1 Win=1024 Len=0
 1884 1.425952420  192.168.0.2 → 192.168.0.5  TCP 60 4279 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1885 1.425952629  192.168.0.2 → 192.168.0.5  TCP 60 4321 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1886 1.425952699  192.168.0.2 → 192.168.0.5  TCP 60 179 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1887 1.426296454  192.168.0.2 → 192.168.0.5  TCP 60 5907 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1888 1.426296663  192.168.0.2 → 192.168.0.5  TCP 60 7676 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1889 1.426296733  192.168.0.2 → 192.168.0.5  TCP 60 2020 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1890 1.426296804  192.168.0.2 → 192.168.0.5  TCP 60 8002 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1891 1.426635248  192.168.0.2 → 192.168.0.5  TCP 60 6792 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1892 1.426635458  192.168.0.2 → 192.168.0.5  TCP 60 1164 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1893 1.426635528  192.168.0.2 → 192.168.0.5  TCP 60 548 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1894 1.427104363  192.168.0.2 → 192.168.0.5  TCP 60 1213 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1895 1.427104583  192.168.0.2 → 192.168.0.5  TCP 60 6567 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1896 1.427104654  192.168.0.2 → 192.168.0.5  TCP 60 2909 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1897 1.427104724  192.168.0.2 → 192.168.0.5  TCP 60 18040 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1898 1.427104794  192.168.0.2 → 192.168.0.5  TCP 60 2393 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1899 1.427104863  192.168.0.2 → 192.168.0.5  TCP 60 668 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1900 1.427804552  192.168.0.2 → 192.168.0.5  TCP 60 5730 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1901 1.427804722  192.168.0.2 → 192.168.0.5  TCP 60 3 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1902 1.427804792  192.168.0.2 → 192.168.0.5  TCP 60 555 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1903 1.427804872  192.168.0.2 → 192.168.0.5  TCP 60 2099 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1904 1.427804942  192.168.0.2 → 192.168.0.5  TCP 60 10002 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1905 1.427805011  192.168.0.2 → 192.168.0.5  TCP 60 1141 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1906 1.427805082  192.168.0.2 → 192.168.0.5  TCP 60 7070 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1907 1.427805152  192.168.0.2 → 192.168.0.5  TCP 60 1556 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1908 1.427901713  192.168.0.2 → 192.168.0.5  TCP 60 3826 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1909 1.428221117  192.168.0.2 → 192.168.0.5  TCP 60 5054 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1910 1.428221327  192.168.0.2 → 192.168.0.5  TCP 60 24 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1911 1.428221396  192.168.0.2 → 192.168.0.5  TCP 60 5902 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1912 1.428221467  192.168.0.2 → 192.168.0.5  TCP 60 49158 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1913 1.428533152  192.168.0.2 → 192.168.0.5  TCP 60 5862 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1914 1.428533361  192.168.0.2 → 192.168.0.5  TCP 60 3476 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1915 1.428533431  192.168.0.2 → 192.168.0.5  TCP 60 19350 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1916 1.428870135  192.168.0.2 → 192.168.0.5  TCP 60 5280 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1917 1.428870346  192.168.0.2 → 192.168.0.5  TCP 60 1084 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1918 1.428870416  192.168.0.2 → 192.168.0.5  TCP 60 5666 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1919 1.428870485  192.168.0.2 → 192.168.0.5  TCP 60 33 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1920 1.429207090  192.168.0.2 → 192.168.0.5  TCP 60 49176 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1921 1.429207310  192.168.0.2 → 192.168.0.5  TCP 60 6009 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1922 1.429207380  192.168.0.2 → 192.168.0.5  TCP 60 4567 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1923 1.429207450  192.168.0.2 → 192.168.0.5  TCP 60 911 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1924 1.429545304  192.168.0.2 → 192.168.0.5  TCP 60 60020 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1925 1.429545524  192.168.0.2 → 192.168.0.5  TCP 60 16992 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1926 1.429545594  192.168.0.2 → 192.168.0.5  TCP 60 1000 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1927 1.429545664  192.168.0.2 → 192.168.0.5  TCP 60 56738 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1928 1.429883419  192.168.0.2 → 192.168.0.5  TCP 60 3800 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1929 1.429883639  192.168.0.2 → 192.168.0.5  TCP 60 1839 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1930 1.429883708  192.168.0.2 → 192.168.0.5  TCP 60 27355 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1931 1.429883778  192.168.0.2 → 192.168.0.5  TCP 60 2038 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1932 1.430221641  192.168.0.2 → 192.168.0.5  TCP 60 1500 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1933 1.430221862  192.168.0.2 → 192.168.0.5  TCP 60 900 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1934 1.430221931  192.168.0.2 → 192.168.0.5  TCP 60 48080 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1935 1.430222001  192.168.0.2 → 192.168.0.5  TCP 60 7 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1936 1.430558286  192.168.0.2 → 192.168.0.5  TCP 60 9071 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1937 1.430558496  192.168.0.2 → 192.168.0.5  TCP 60 3703 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1938 1.430558566  192.168.0.2 → 192.168.0.5  TCP 60 1148 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1939 1.431000622  192.168.0.2 → 192.168.0.5  TCP 60 4001 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1940 1.431000832  192.168.0.2 → 192.168.0.5  TCP 60 5087 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1941 1.431000902  192.168.0.2 → 192.168.0.5  TCP 60 1107 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1942 1.431000972  192.168.0.2 → 192.168.0.5  TCP 60 9220 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1943 1.431001042  192.168.0.2 → 192.168.0.5  TCP 60 873 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1944 1.431338446  192.168.0.2 → 192.168.0.5  TCP 60 10566 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1945 1.431338656  192.168.0.2 → 192.168.0.5  TCP 60 3011 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1946 1.431338726  192.168.0.2 → 192.168.0.5  TCP 60 3261 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1947 1.431338796  192.168.0.2 → 192.168.0.5  TCP 60 27353 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1948 1.431823512  192.168.0.2 → 192.168.0.5  TCP 60 6646 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1949 1.431823712  192.168.0.2 → 192.168.0.5  TCP 60 5678 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1950 1.431823782  192.168.0.2 → 192.168.0.5  TCP 60 3071 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1951 1.431823872  192.168.0.2 → 192.168.0.5  TCP 60 5679 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1952 1.431823942  192.168.0.2 → 192.168.0.5  TCP 60 8873 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1953 1.432208977  192.168.0.2 → 192.168.0.5  TCP 60 1053 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1954 1.432209197  192.168.0.2 → 192.168.0.5  TCP 60 1028 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1955 1.432209267  192.168.0.2 → 192.168.0.5  TCP 60 4443 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1956 1.432209337  192.168.0.2 → 192.168.0.5  TCP 60 2701 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1957 1.432209406  192.168.0.2 → 192.168.0.5  TCP 60 8081 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1958 1.432500600  192.168.0.2 → 192.168.0.5  TCP 60 593 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1959 1.432500820  192.168.0.2 → 192.168.0.5  TCP 60 8008 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1960 1.434880060  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2033 [FIN] Seq=1 Win=1024 Len=0
 1961 1.434942941  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 34573 [FIN] Seq=1 Win=1024 Len=0
 1962 1.434998262  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 9418 [FIN] Seq=1 Win=1024 Len=0
 1963 1.435053532  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1236 [FIN] Seq=1 Win=1024 Len=0
 1964 1.435108843  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1022 [FIN] Seq=1 Win=1024 Len=0
 1965 1.435164504  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 1121 [FIN] Seq=1 Win=1024 Len=0
 1966 1.435219314  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2047 [FIN] Seq=1 Win=1024 Len=0
 1967 1.435275635  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8654 [FIN] Seq=1 Win=1024 Len=0
 1968 1.435330965  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 51103 [FIN] Seq=1 Win=1024 Len=0
 1969 1.435385836  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2869 [FIN] Seq=1 Win=1024 Len=0
 1970 1.435409187  192.168.0.2 → 192.168.0.5  TCP 60 2033 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1971 1.435409397  192.168.0.2 → 192.168.0.5  TCP 60 34573 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1972 1.435599110  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 2009 [FIN] Seq=1 Win=1024 Len=0
 1973 1.435655540  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8031 [FIN] Seq=1 Win=1024 Len=0
 1974 1.435713061  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 3920 [FIN] Seq=1 Win=1024 Len=0
 1975 1.435769371  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 5987 [FIN] Seq=1 Win=1024 Len=0
 1976 1.435825272  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 64680 [FIN] Seq=1 Win=1024 Len=0
 1977 1.435882793  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 8084 [FIN] Seq=1 Win=1024 Len=0
 1978 1.435958284  192.168.0.2 → 192.168.0.5  TCP 60 9418 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1979 1.435958494  192.168.0.2 → 192.168.0.5  TCP 60 1236 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1980 1.435958564  192.168.0.2 → 192.168.0.5  TCP 60 1022 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1981 1.435938004  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 465 [FIN] Seq=1 Win=1024 Len=0
 1982 1.435958634  192.168.0.2 → 192.168.0.5  TCP 60 1121 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1983 1.435958704  192.168.0.2 → 192.168.0.5  TCP 60 2047 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1984 1.435958774  192.168.0.2 → 192.168.0.5  TCP 60 8654 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1985 1.435958844  192.168.0.2 → 192.168.0.5  TCP 60 51103 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1986 1.435994435  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 7443 [FIN] Seq=1 Win=1024 Len=0
 1987 1.436050005  192.168.0.5 → 192.168.0.2  TCP 54 41034 → 4002 [FIN] Seq=1 Win=1024 Len=0
 1988 1.436259148  192.168.0.2 → 192.168.0.5  TCP 60 2869 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1989 1.436259357  192.168.0.2 → 192.168.0.5  TCP 60 2009 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1990 1.436259427  192.168.0.2 → 192.168.0.5  TCP 60 8031 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1991 1.436604521  192.168.0.2 → 192.168.0.5  TCP 60 3920 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1992 1.436604732  192.168.0.2 → 192.168.0.5  TCP 60 5987 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1993 1.436604802  192.168.0.2 → 192.168.0.5  TCP 60 64680 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1994 1.436604872  192.168.0.2 → 192.168.0.5  TCP 60 8084 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1995 1.436959297  192.168.0.2 → 192.168.0.5  TCP 60 465 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1996 1.436959517  192.168.0.2 → 192.168.0.5  TCP 60 7443 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1997 1.436959587  192.168.0.2 → 192.168.0.5  TCP 60 4002 → 41034 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1998 1.442279803  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 8180 [FIN] Seq=1 Win=1024 Len=0
 1999 1.475509686  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 8009 [FIN] Seq=1 Win=1024 Len=0
 2000 1.475582836  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 2121 [FIN] Seq=1 Win=1024 Len=0
 2001 1.513448637  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 6667 [FIN] Seq=1 Win=1024 Len=0
 2002 1.513523589  192.168.0.5 → 192.168.0.2  TCP 54 41036 → 1524 [FIN] Seq=1 Win=1024 Len=0
 2003 11.437810602 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 2004 11.437824412 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
```
</details>
</details>


<details>
<summary>3. Xmas-сканирование </summary>

```
sudo nmap -sX 192.168.0.2
Starting Nmap 7.93 ( https://nmap.org ) at 2024-07-19 18:30 +05
Nmap scan report for 192.168.0.2
Host is up (0.024s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE         SERVICE
21/tcp   open|filtered ftp
22/tcp   open|filtered ssh
23/tcp   open|filtered telnet
25/tcp   open|filtered smtp
53/tcp   open|filtered domain
80/tcp   open|filtered http
111/tcp  open|filtered rpcbind
139/tcp  open|filtered netbios-ssn
445/tcp  open|filtered microsoft-ds
512/tcp  open|filtered exec
513/tcp  open|filtered login
514/tcp  open|filtered shell
1099/tcp open|filtered rmiregistry
1524/tcp open|filtered ingreslock
2049/tcp open|filtered nfs
2121/tcp open|filtered ccproxy-ftp
3306/tcp open|filtered mysql
5432/tcp open|filtered postgresql
5900/tcp open|filtered vnc
6000/tcp open|filtered X11
6667/tcp open|filtered irc
8009/tcp open|filtered ajp13
8180/tcp open|filtered unknown
MAC Address: 08:00:27:18:EE:BD (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 4.26 seconds
```

<details>
<summary>Дамп Tshark</summary>

```
 1495 3.908030084  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 50003 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1496 3.908313093  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1009 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1497 3.908582882  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1247 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1498 3.908853370  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 30000 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1499 3.909122689  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1041 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1500 3.909426168  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 61532 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1501 3.909697727  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 15003 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1502 3.909966815  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1049 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1503 3.910247564  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3995 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1504 3.910664971  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1166 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1505 3.910934720  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1063 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1506 3.911214439  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9998 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1507 3.911552747  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5859 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1508 3.911823286  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1023 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1509 3.912094564  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2288 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1510 3.912371694  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1433 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1511 3.912641442  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 11111 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1512 3.912910931  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 41511 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1513 3.913200070  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5051 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1514 3.913471828  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2968 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1515 3.916190456  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5907 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1516 3.916460544  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9099 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1517 3.916942662  192.168.0.2 → 192.168.0.5  TCP 60 2160 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1518 3.916942872  192.168.0.2 → 192.168.0.5  TCP 60 5862 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1519 3.916942942  192.168.0.2 → 192.168.0.5  TCP 60 5825 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1520 3.917244240  192.168.0.2 → 192.168.0.5  TCP 60 8873 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1521 3.917244450  192.168.0.2 → 192.168.0.5  TCP 60 3546 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1522 3.917244520  192.168.0.2 → 192.168.0.5  TCP 60 6789 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1523 3.917537089  192.168.0.2 → 192.168.0.5  TCP 60 50500 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1524 3.917537288  192.168.0.2 → 192.168.0.5  TCP 60 19 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1525 3.917537358  192.168.0.2 → 192.168.0.5  TCP 60 3945 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1526 3.917537429  192.168.0.2 → 192.168.0.5  TCP 60 4900 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1527 3.917828108  192.168.0.2 → 192.168.0.5  TCP 60 5431 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1528 3.917828318  192.168.0.2 → 192.168.0.5  TCP 60 48080 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1529 3.917828388  192.168.0.2 → 192.168.0.5  TCP 60 1287 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1530 3.918131547  192.168.0.2 → 192.168.0.5  TCP 60 50003 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1531 3.918131756  192.168.0.2 → 192.168.0.5  TCP 60 1009 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1532 3.918131827  192.168.0.2 → 192.168.0.5  TCP 60 1247 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1533 3.918606694  192.168.0.2 → 192.168.0.5  TCP 60 30000 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1534 3.918606904  192.168.0.2 → 192.168.0.5  TCP 60 1041 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1535 3.918606974  192.168.0.2 → 192.168.0.5  TCP 60 61532 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1536 3.918607044  192.168.0.2 → 192.168.0.5  TCP 60 15003 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1537 3.918607114  192.168.0.2 → 192.168.0.5  TCP 60 1049 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1538 3.918607185  192.168.0.2 → 192.168.0.5  TCP 60 3995 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1539 3.918908582  192.168.0.2 → 192.168.0.5  TCP 60 1166 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1540 3.918908793  192.168.0.2 → 192.168.0.5  TCP 60 1063 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1541 3.918908863  192.168.0.2 → 192.168.0.5  TCP 60 9998 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1542 3.919203372  192.168.0.2 → 192.168.0.5  TCP 60 5859 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1543 3.919203581  192.168.0.2 → 192.168.0.5  TCP 60 1023 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1544 3.919203651  192.168.0.2 → 192.168.0.5  TCP 60 2288 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1545 3.919203722  192.168.0.2 → 192.168.0.5  TCP 60 1433 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1546 3.919495500  192.168.0.2 → 192.168.0.5  TCP 60 11111 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1547 3.919495710  192.168.0.2 → 192.168.0.5  TCP 60 41511 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1548 3.919495779  192.168.0.2 → 192.168.0.5  TCP 60 5051 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1549 3.919823768  192.168.0.2 → 192.168.0.5  TCP 60 2968 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1550 3.919823978  192.168.0.2 → 192.168.0.5  TCP 60 5907 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1551 3.920084457  192.168.0.2 → 192.168.0.5  TCP 60 9099 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1552 3.920159996  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 16000 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1553 3.920426785  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2021 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1554 3.920662875  192.168.0.2 → 192.168.0.5  TCP 60 16000 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1555 3.920663085  192.168.0.2 → 192.168.0.5  TCP 60 2021 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1556 3.920988514  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 100 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1557 3.921254392  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 58080 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1558 3.921478680  192.168.0.2 → 192.168.0.5  TCP 60 100 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1559 3.921780739  192.168.0.2 → 192.168.0.5  TCP 60 58080 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1560 3.921859098  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 666 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1561 3.922124578  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 888 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1562 3.922349947  192.168.0.2 → 192.168.0.5  TCP 60 666 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1563 3.922350177  192.168.0.2 → 192.168.0.5  TCP 60 888 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1564 3.922827733  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 4045 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1565 3.923128622  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6129 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1566 3.923356571  192.168.0.2 → 192.168.0.5  TCP 60 4045 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1567 3.923437452  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 900 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1568 3.923665591  192.168.0.2 → 192.168.0.5  TCP 60 6129 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1569 3.923665800  192.168.0.2 → 192.168.0.5  TCP 60 900 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1570 3.924005409  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2638 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1571 3.924274287  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1244 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1572 3.924502686  192.168.0.2 → 192.168.0.5  TCP 60 2638 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1573 3.924583476  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5555 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1574 3.924811985  192.168.0.2 → 192.168.0.5  TCP 60 1244 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1575 3.924812204  192.168.0.2 → 192.168.0.5  TCP 60 5555 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1576 3.925154823  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 12345 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1577 3.925419681  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2049 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1578 3.925644390  192.168.0.2 → 192.168.0.5  TCP 60 12345 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1579 3.925723610  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 32 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1580 3.925953769  192.168.0.2 → 192.168.0.5  TCP 60 32 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1581 3.926277048  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2869 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1582 3.926635917  192.168.0.2 → 192.168.0.5  TCP 60 2869 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1583 3.926999565  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 545 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1584 3.927273333  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 32780 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1585 3.927497752  192.168.0.2 → 192.168.0.5  TCP 60 545 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1586 3.927497972  192.168.0.2 → 192.168.0.5  TCP 60 32780 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1587 3.927821861  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1300 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1588 3.928098109  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2909 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1589 3.928322937  192.168.0.2 → 192.168.0.5  TCP 60 1300 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1590 3.928401847  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1112 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1591 3.928626126  192.168.0.2 → 192.168.0.5  TCP 60 2909 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1592 3.928626337  192.168.0.2 → 192.168.0.5  TCP 60 1112 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1593 3.928965775  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 497 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1594 3.929230864  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6839 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1595 3.929456903  192.168.0.2 → 192.168.0.5  TCP 60 497 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1596 3.929457114  192.168.0.2 → 192.168.0.5  TCP 60 6839 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1597 3.929781321  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1075 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1598 3.930107729  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1082 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1599 3.930365768  192.168.0.2 → 192.168.0.5  TCP 60 1075 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1600 3.930798686  192.168.0.2 → 192.168.0.5  TCP 60 1082 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1601 3.930890795  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 7778 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1602 3.931155835  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 7000 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1603 3.931381844  192.168.0.2 → 192.168.0.5  TCP 60 7778 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1604 3.931382053  192.168.0.2 → 192.168.0.5  TCP 60 7000 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1605 3.931706691  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2005 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1606 3.931979491  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10778 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1607 3.932243810  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 4848 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1608 3.932508348  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6779 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1609 3.932772387  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9878 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1610 3.933059146  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2717 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1611 3.933323975  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5922 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1612 3.933587673  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 64623 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1613 3.933856372  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1998 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1614 3.934119950  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3390 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1615 3.934385389  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10000 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1616 3.934841958  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9485 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1617 3.935107886  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 340 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1618 3.935373315  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10003 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1619 3.935638423  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6692 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1620 3.938867759  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 82 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1621 3.939135767  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6007 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1622 3.939400775  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3690 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1623 3.939665374  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1045 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1624 3.939930353  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 18040 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1625 3.940255442  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5060 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1626 3.940547021  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 636 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1627 3.940812989  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9103 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1628 3.941078988  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2800 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1629 3.941349547  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1201 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1630 3.941613875  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1666 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1631 3.941878604  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1163 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1632 3.942227122  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 44442 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1633 3.943039009  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1042 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1634 3.943328627  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3221 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1635 3.943595586  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 711 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1636 3.943884005  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1077 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1637 3.944240483  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5280 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1638 3.944574811  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1272 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1639 3.944880720  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 801 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1640 3.945106299  192.168.0.2 → 192.168.0.5  TCP 60 2005 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1641 3.945106508  192.168.0.2 → 192.168.0.5  TCP 60 10778 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1642 3.945392337  192.168.0.2 → 192.168.0.5  TCP 60 4848 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1643 3.945392557  192.168.0.2 → 192.168.0.5  TCP 60 6779 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1644 3.945392627  192.168.0.2 → 192.168.0.5  TCP 60 9878 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1645 3.945681155  192.168.0.2 → 192.168.0.5  TCP 60 2717 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1646 3.945681366  192.168.0.2 → 192.168.0.5  TCP 60 5922 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1647 3.945681436  192.168.0.2 → 192.168.0.5  TCP 60 64623 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1648 3.945681505  192.168.0.2 → 192.168.0.5  TCP 60 1998 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1649 3.946048495  192.168.0.2 → 192.168.0.5  TCP 60 3390 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1650 3.946048704  192.168.0.2 → 192.168.0.5  TCP 60 10000 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1651 3.946048774  192.168.0.2 → 192.168.0.5  TCP 60 9485 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1652 3.946048845  192.168.0.2 → 192.168.0.5  TCP 60 340 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1653 3.946549602  192.168.0.2 → 192.168.0.5  TCP 60 10003 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1654 3.946549822  192.168.0.2 → 192.168.0.5  TCP 60 6692 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1655 3.946549892  192.168.0.2 → 192.168.0.5  TCP 60 82 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1656 3.946885790  192.168.0.2 → 192.168.0.5  TCP 60 6007 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1657 3.946886010  192.168.0.2 → 192.168.0.5  TCP 60 3690 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1658 3.946886080  192.168.0.2 → 192.168.0.5  TCP 60 1045 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1659 3.946886151  192.168.0.2 → 192.168.0.5  TCP 60 18040 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1660 3.946886221  192.168.0.2 → 192.168.0.5  TCP 60 5060 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1661 3.946886291  192.168.0.2 → 192.168.0.5  TCP 60 636 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1662 3.946886360  192.168.0.2 → 192.168.0.5  TCP 60 9103 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1663 3.947183979  192.168.0.2 → 192.168.0.5  TCP 60 2800 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1664 3.947184189  192.168.0.2 → 192.168.0.5  TCP 60 1201 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1665 3.947184258  192.168.0.2 → 192.168.0.5  TCP 60 1666 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1666 3.947519787  192.168.0.2 → 192.168.0.5  TCP 60 1163 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1667 3.947519997  192.168.0.2 → 192.168.0.5  TCP 60 44442 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1668 3.947520068  192.168.0.2 → 192.168.0.5  TCP 60 1042 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1669 3.947520137  192.168.0.2 → 192.168.0.5  TCP 60 3221 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1670 3.947537897  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1059 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1671 3.947597716  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9200 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1672 3.947656276  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9418 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1673 3.947719906  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3814 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1674 3.947776755  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 33899 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1675 3.947852106  192.168.0.2 → 192.168.0.5  TCP 60 711 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1676 3.947852315  192.168.0.2 → 192.168.0.5  TCP 60 1077 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1677 3.947852386  192.168.0.2 → 192.168.0.5  TCP 60 5280 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1678 3.947852456  192.168.0.2 → 192.168.0.5  TCP 60 1272 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1679 3.947833195  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 49175 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1680 3.947894115  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1069 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1681 3.947950484  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2048 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1682 3.948007014  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1186 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1683 3.948064394  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2525 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1684 3.948120943  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 27356 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1685 3.948148774  192.168.0.2 → 192.168.0.5  TCP 60 801 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1686 3.948148984  192.168.0.2 → 192.168.0.5  TCP 60 1059 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1687 3.948149054  192.168.0.2 → 192.168.0.5  TCP 60 9200 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1688 3.948178784  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 720 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1689 3.948235613  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1068 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1690 3.948291633  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 42510 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1691 3.948347892  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3031 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1692 3.948415633  192.168.0.2 → 192.168.0.5  TCP 60 9418 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1693 3.948415843  192.168.0.2 → 192.168.0.5  TCP 60 3814 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1694 3.948415913  192.168.0.2 → 192.168.0.5  TCP 60 33899 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1695 3.948404302  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1309 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1696 3.948462052  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3827 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1697 3.948519972  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2106 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1698 3.948577642  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2607 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1699 3.948634162  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9877 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1700 3.948704852  192.168.0.2 → 192.168.0.5  TCP 60 49175 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1701 3.948705052  192.168.0.2 → 192.168.0.5  TCP 60 1069 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1702 3.948705123  192.168.0.2 → 192.168.0.5  TCP 60 2048 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1703 3.948705192  192.168.0.2 → 192.168.0.5  TCP 60 1186 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1704 3.948691182  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5432 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1705 3.948747341  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 32776 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1706 3.948803482  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6646 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1707 3.948860321  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8045 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1708 3.948917040  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 407 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1709 3.948972960  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 515 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1710 3.948997411  192.168.0.2 → 192.168.0.5  TCP 60 2525 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1711 3.948997620  192.168.0.2 → 192.168.0.5  TCP 60 27356 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1712 3.948997701  192.168.0.2 → 192.168.0.5  TCP 60 720 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1713 3.949030550  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1034 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1714 3.949086479  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9010 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1715 3.949145899  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 416 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1716 3.949202629  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 60020 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1717 3.949294519  192.168.0.2 → 192.168.0.5  TCP 60 1068 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1718 3.949294729  192.168.0.2 → 192.168.0.5  TCP 60 42510 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1719 3.949294799  192.168.0.2 → 192.168.0.5  TCP 60 3031 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1720 3.949582018  192.168.0.2 → 192.168.0.5  TCP 60 1309 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1721 3.949582218  192.168.0.2 → 192.168.0.5  TCP 60 3827 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1722 3.949582288  192.168.0.2 → 192.168.0.5  TCP 60 2106 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1723 3.949582357  192.168.0.2 → 192.168.0.5  TCP 60 2607 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1724 3.949930206  192.168.0.2 → 192.168.0.5  TCP 60 9877 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1725 3.949930416  192.168.0.2 → 192.168.0.5  TCP 60 32776 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1726 3.949930485  192.168.0.2 → 192.168.0.5  TCP 60 6646 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1727 3.949930556  192.168.0.2 → 192.168.0.5  TCP 60 8045 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1728 3.950270494  192.168.0.2 → 192.168.0.5  TCP 60 407 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1729 3.950270694  192.168.0.2 → 192.168.0.5  TCP 60 515 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1730 3.950270775  192.168.0.2 → 192.168.0.5  TCP 60 1034 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1731 3.950270844  192.168.0.2 → 192.168.0.5  TCP 60 9010 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1732 3.950761922  192.168.0.2 → 192.168.0.5  TCP 60 416 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1733 3.950762142  192.168.0.2 → 192.168.0.5  TCP 60 60020 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1734 3.955208621  192.168.0.5 → 192.168.0.2  TCP 54 56619 → 6000 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1735 3.955278241  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3283 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1736 3.955337131  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2009 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1737 3.955394971  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1070 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1738 3.955452281  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3871 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1739 3.955519000  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1461 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1740 3.955577840  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 18101 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1741 3.955635570  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 25734 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1742 3.955693040  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1121 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1743 3.955750779  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1296 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1744 3.955809459  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2105 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1745 3.955866809  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10629 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1746 3.955924768  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5566 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1747 3.955982608  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5544 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1748 3.956040558  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8500 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1749 3.956120057  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1111 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1750 3.956178587  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 88 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1751 3.956235797  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 21571 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1752 3.956293907  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9081 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1753 3.956372596  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5102 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1754 3.956430625  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 28201 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1755 3.956489326  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 465 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1756 3.956546145  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1021 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1757 3.956693423  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9000 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1758 3.956752913  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9503 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1759 3.956810043  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 19283 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1760 3.956866442  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 61900 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1761 3.956922963  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 990 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1762 3.956979812  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5214 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1763 3.957036482  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 32771 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1764 3.957093342  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1137 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1765 3.957150182  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9101 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1766 3.957207412  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3766 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1767 3.957264661  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2875 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1768 3.957321471  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 32770 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1769 3.957378080  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8087 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1770 3.957434550  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3809 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1771 3.957491080  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5998 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1772 3.957547010  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6156 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1773 3.957603250  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 15004 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1774 3.957659289  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5962 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1775 3.957715409  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 16018 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1776 3.957772038  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5357 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1777 3.957827828  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1216 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1778 3.957884498  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5030 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1779 3.957940837  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1098 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1780 3.957997377  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6565 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1781 3.958164657  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2811 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1782 3.958304366  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5718 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1783 3.958461505  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5906 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1784 3.961092402  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2522 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1785 3.961156353  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3493 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1786 3.961212212  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 458 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1787 3.961306562  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 125 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1788 3.961363422  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2020 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1789 3.961419411  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1164 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1790 3.961474911  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1301 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1791 3.961531261  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 49158 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1792 3.961586890  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6101 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1793 3.961642830  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1236 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1794 3.961698319  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2702 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1795 3.961753739  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1089 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1796 3.961809959  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9090 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1797 3.961866249  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 19101 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1798 3.961924328  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 32769 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1799 3.961983548  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 14442 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1800 3.962039678  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1863 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1801 3.962095398  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 27355 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1802 3.962151047  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10616 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1803 3.962206717  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1078 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1804 3.962262476  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10566 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1805 3.962319116  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2920 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1806 3.962492975  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1185 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1807 3.962549467  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 7007 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1808 3.962605866  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 12265 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1809 3.962662326  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8083 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1810 3.962718326  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1010 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1811 3.962774305  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1107 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1812 3.962836855  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 119 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1813 3.968596557  192.168.0.2 → 192.168.0.5  TCP 60 3283 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1814 3.968596767  192.168.0.2 → 192.168.0.5  TCP 60 2009 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1815 3.968596837  192.168.0.2 → 192.168.0.5  TCP 60 1070 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1816 3.968935296  192.168.0.2 → 192.168.0.5  TCP 60 3871 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1817 3.968935505  192.168.0.2 → 192.168.0.5  TCP 60 1461 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1818 3.968935576  192.168.0.2 → 192.168.0.5  TCP 60 18101 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1819 3.968935646  192.168.0.2 → 192.168.0.5  TCP 60 25734 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1820 3.969273843  192.168.0.2 → 192.168.0.5  TCP 60 1121 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1821 3.969274074  192.168.0.2 → 192.168.0.5  TCP 60 1296 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1822 3.969274144  192.168.0.2 → 192.168.0.5  TCP 60 2105 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1823 3.969274214  192.168.0.2 → 192.168.0.5  TCP 60 10629 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1824 3.969612712  192.168.0.2 → 192.168.0.5  TCP 60 5566 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1825 3.969612922  192.168.0.2 → 192.168.0.5  TCP 60 5544 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1826 3.969612992  192.168.0.2 → 192.168.0.5  TCP 60 8500 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1827 3.969613062  192.168.0.2 → 192.168.0.5  TCP 60 1111 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1828 3.969950560  192.168.0.2 → 192.168.0.5  TCP 60 88 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1829 3.969950780  192.168.0.2 → 192.168.0.5  TCP 60 21571 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1830 3.969950850  192.168.0.2 → 192.168.0.5  TCP 60 9081 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1831 3.969950920  192.168.0.2 → 192.168.0.5  TCP 60 5102 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1832 3.970455748  192.168.0.2 → 192.168.0.5  TCP 60 28201 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1833 3.970455968  192.168.0.2 → 192.168.0.5  TCP 60 465 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1834 3.970456038  192.168.0.2 → 192.168.0.5  TCP 60 1021 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1835 3.970456107  192.168.0.2 → 192.168.0.5  TCP 60 9000 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1836 3.970456178  192.168.0.2 → 192.168.0.5  TCP 60 9503 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1837 3.970456267  192.168.0.2 → 192.168.0.5  TCP 60 19283 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1838 3.970754447  192.168.0.2 → 192.168.0.5  TCP 60 61900 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1839 3.970754656  192.168.0.2 → 192.168.0.5  TCP 60 990 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1840 3.970754726  192.168.0.2 → 192.168.0.5  TCP 60 5214 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1841 3.971088466  192.168.0.2 → 192.168.0.5  TCP 60 32771 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1842 3.971088666  192.168.0.2 → 192.168.0.5  TCP 60 1137 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1843 3.971088735  192.168.0.2 → 192.168.0.5  TCP 60 9101 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1844 3.971088805  192.168.0.2 → 192.168.0.5  TCP 60 3766 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1845 3.971615593  192.168.0.2 → 192.168.0.5  TCP 60 2875 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1846 3.971615864  192.168.0.2 → 192.168.0.5  TCP 60 32770 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1847 3.971615934  192.168.0.2 → 192.168.0.5  TCP 60 8087 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1848 3.971616004  192.168.0.2 → 192.168.0.5  TCP 60 3809 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1849 3.971616073  192.168.0.2 → 192.168.0.5  TCP 60 5998 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1850 3.971616144  192.168.0.2 → 192.168.0.5  TCP 60 6156 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1851 3.971980682  192.168.0.2 → 192.168.0.5  TCP 60 15004 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1852 3.971980892  192.168.0.2 → 192.168.0.5  TCP 60 5962 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1853 3.971980962  192.168.0.2 → 192.168.0.5  TCP 60 16018 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1854 3.971981032  192.168.0.2 → 192.168.0.5  TCP 60 5357 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1855 3.972367679  192.168.0.2 → 192.168.0.5  TCP 60 1216 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1856 3.972367879  192.168.0.2 → 192.168.0.5  TCP 60 5030 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1857 3.972367949  192.168.0.2 → 192.168.0.5  TCP 60 1098 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1858 3.972368019  192.168.0.2 → 192.168.0.5  TCP 60 6565 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1859 3.972368089  192.168.0.2 → 192.168.0.5  TCP 60 2811 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1860 3.972708607  192.168.0.2 → 192.168.0.5  TCP 60 5718 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1861 3.972708817  192.168.0.2 → 192.168.0.5  TCP 60 5906 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1862 3.972708897  192.168.0.2 → 192.168.0.5  TCP 60 2522 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1863 3.972708968  192.168.0.2 → 192.168.0.5  TCP 60 3493 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1864 3.973045305  192.168.0.2 → 192.168.0.5  TCP 60 458 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1865 3.973045516  192.168.0.2 → 192.168.0.5  TCP 60 125 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1866 3.973045586  192.168.0.2 → 192.168.0.5  TCP 60 2020 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1867 3.973045655  192.168.0.2 → 192.168.0.5  TCP 60 1164 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1868 3.973384014  192.168.0.2 → 192.168.0.5  TCP 60 1301 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1869 3.973384223  192.168.0.2 → 192.168.0.5  TCP 60 49158 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1870 3.973384294  192.168.0.2 → 192.168.0.5  TCP 60 6101 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1871 3.973384364  192.168.0.2 → 192.168.0.5  TCP 60 1236 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1872 3.973723593  192.168.0.2 → 192.168.0.5  TCP 60 2702 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1873 3.973723803  192.168.0.2 → 192.168.0.5  TCP 60 1089 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1874 3.973723883  192.168.0.2 → 192.168.0.5  TCP 60 9090 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1875 3.973723953  192.168.0.2 → 192.168.0.5  TCP 60 19101 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1876 3.974060962  192.168.0.2 → 192.168.0.5  TCP 60 32769 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1877 3.976352631  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5961 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1878 3.976417770  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2111 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1879 3.976475791  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 7103 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1880 3.976582751  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2041 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1881 3.976641160  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1138 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1882 3.976700670  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2601 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1883 3.976758061  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 222 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1884 3.976851989  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5915 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1885 3.976911138  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3851 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1886 3.976968398  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 722 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1887 3.977024847  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 987 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1888 3.977081187  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 800 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1889 3.977137977  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5679 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1890 3.977195037  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 9080 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1891 3.977252996  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1100 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1892 3.977310196  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8031 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1893 3.977370315  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10215 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1894 3.977427226  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3005 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1895 3.977483725  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8085 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1896 3.977540435  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5221 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1897 3.977596804  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2008 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1898 3.977653184  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 19801 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1899 3.977709585  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3659 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1900 3.977766934  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 10009 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1901 3.977823324  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 625 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1902 3.977880163  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 35500 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1903 3.977936433  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 60443 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1904 3.977992473  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 714 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1905 3.978048853  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1043 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1906 3.978105462  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 7025 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1907 3.978162202  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 3001 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1908 3.978456700  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 16012 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1909 3.978513480  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 514 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1910 3.978570720  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2809 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1911 3.978626900  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 8222 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1912 3.978683639  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6502 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1913 3.978740479  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 17 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1914 3.978796559  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5003 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1915 3.978853268  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1524 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1916 3.978910058  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6792 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1917 3.978966158  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 62078 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1918 3.979023067  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 2382 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1919 3.979079597  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5004 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1920 3.979135537  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 301 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1921 3.979192267  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 280 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1922 3.979248926  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 16016 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1923 3.979304877  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 24444 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1924 3.979361147  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1091 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1925 3.979417916  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1658 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1926 3.979474926  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 417 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1927 3.981783604  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 49152 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1928 3.981846494  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 5001 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1929 3.981903114  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 406 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1930 3.982020113  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 1521 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1931 3.982083823  192.168.0.5 → 192.168.0.2  TCP 54 56617 → 6666 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 1932 3.986132604  192.168.0.2 → 192.168.0.5  TCP 60 14442 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1933 3.986132814  192.168.0.2 → 192.168.0.5  TCP 60 1863 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1934 3.986132894  192.168.0.2 → 192.168.0.5  TCP 60 27355 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1935 3.986565281  192.168.0.2 → 192.168.0.5  TCP 60 10616 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1936 3.986565492  192.168.0.2 → 192.168.0.5  TCP 60 1078 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1937 3.986565562  192.168.0.2 → 192.168.0.5  TCP 60 10566 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1938 3.986565631  192.168.0.2 → 192.168.0.5  TCP 60 2920 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1939 3.986565702  192.168.0.2 → 192.168.0.5  TCP 60 1185 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1940 3.987060219  192.168.0.2 → 192.168.0.5  TCP 60 7007 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1941 3.987060429  192.168.0.2 → 192.168.0.5  TCP 60 12265 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1942 3.987060509  192.168.0.2 → 192.168.0.5  TCP 60 8083 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1943 3.987060569  192.168.0.2 → 192.168.0.5  TCP 60 1010 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1944 3.987060649  192.168.0.2 → 192.168.0.5  TCP 60 1107 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1945 3.987060719  192.168.0.2 → 192.168.0.5  TCP 60 119 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1946 3.987413158  192.168.0.2 → 192.168.0.5  TCP 60 5961 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1947 3.987413367  192.168.0.2 → 192.168.0.5  TCP 60 2111 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1948 3.987413448  192.168.0.2 → 192.168.0.5  TCP 60 7103 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1949 3.987413518  192.168.0.2 → 192.168.0.5  TCP 60 2041 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1950 3.987751857  192.168.0.2 → 192.168.0.5  TCP 60 1138 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1951 3.987752067  192.168.0.2 → 192.168.0.5  TCP 60 2601 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1952 3.987752137  192.168.0.2 → 192.168.0.5  TCP 60 222 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1953 3.987752207  192.168.0.2 → 192.168.0.5  TCP 60 5915 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1954 3.988090935  192.168.0.2 → 192.168.0.5  TCP 60 3851 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1955 3.988091145  192.168.0.2 → 192.168.0.5  TCP 60 722 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1956 3.988091215  192.168.0.2 → 192.168.0.5  TCP 60 987 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1957 3.988091285  192.168.0.2 → 192.168.0.5  TCP 60 800 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1958 3.988429413  192.168.0.2 → 192.168.0.5  TCP 60 5679 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1959 3.988429623  192.168.0.2 → 192.168.0.5  TCP 60 9080 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1960 3.988429694  192.168.0.2 → 192.168.0.5  TCP 60 1100 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1961 3.988429764  192.168.0.2 → 192.168.0.5  TCP 60 8031 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1962 3.988769231  192.168.0.2 → 192.168.0.5  TCP 60 10215 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1963 3.988769442  192.168.0.2 → 192.168.0.5  TCP 60 3005 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1964 3.988769512  192.168.0.2 → 192.168.0.5  TCP 60 8085 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1965 3.989105640  192.168.0.2 → 192.168.0.5  TCP 60 5221 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1966 3.989105860  192.168.0.2 → 192.168.0.5  TCP 60 2008 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1967 3.989105930  192.168.0.2 → 192.168.0.5  TCP 60 19801 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1968 4.002460467  192.168.0.2 → 192.168.0.5  TCP 60 3659 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1969 4.002460667  192.168.0.2 → 192.168.0.5  TCP 60 10009 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1970 4.002460747  192.168.0.2 → 192.168.0.5  TCP 60 625 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1971 4.002460817  192.168.0.2 → 192.168.0.5  TCP 60 35500 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1972 4.002460887  192.168.0.2 → 192.168.0.5  TCP 60 60443 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1973 4.002827975  192.168.0.2 → 192.168.0.5  TCP 60 714 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1974 4.002828185  192.168.0.2 → 192.168.0.5  TCP 60 1043 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1975 4.002828255  192.168.0.2 → 192.168.0.5  TCP 60 7025 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1976 4.002828325  192.168.0.2 → 192.168.0.5  TCP 60 3001 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1977 4.003168203  192.168.0.2 → 192.168.0.5  TCP 60 16012 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1978 4.003168423  192.168.0.2 → 192.168.0.5  TCP 60 2809 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1979 4.003168493  192.168.0.2 → 192.168.0.5  TCP 60 8222 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1980 4.003504802  192.168.0.2 → 192.168.0.5  TCP 60 6502 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1981 4.003505001  192.168.0.2 → 192.168.0.5  TCP 60 17 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1982 4.003505072  192.168.0.2 → 192.168.0.5  TCP 60 5003 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1983 4.003505142  192.168.0.2 → 192.168.0.5  TCP 60 6792 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1984 4.003842010  192.168.0.2 → 192.168.0.5  TCP 60 62078 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1985 4.003842220  192.168.0.2 → 192.168.0.5  TCP 60 2382 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1986 4.003842320  192.168.0.2 → 192.168.0.5  TCP 60 5004 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1987 4.003842400  192.168.0.2 → 192.168.0.5  TCP 60 301 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1988 4.004185869  192.168.0.2 → 192.168.0.5  TCP 60 280 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1989 4.004186088  192.168.0.2 → 192.168.0.5  TCP 60 16016 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1990 4.004186159  192.168.0.2 → 192.168.0.5  TCP 60 24444 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1991 4.004186228  192.168.0.2 → 192.168.0.5  TCP 60 1091 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1992 4.004524178  192.168.0.2 → 192.168.0.5  TCP 60 1658 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1993 4.004524398  192.168.0.2 → 192.168.0.5  TCP 60 417 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1994 4.004524477  192.168.0.2 → 192.168.0.5  TCP 60 49152 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1995 4.004524547  192.168.0.2 → 192.168.0.5  TCP 60 5001 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1996 4.004986845  192.168.0.2 → 192.168.0.5  TCP 60 406 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1997 4.004987055  192.168.0.2 → 192.168.0.5  TCP 60 1521 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1998 4.004987125  192.168.0.2 → 192.168.0.5  TCP 60 6666 → 56617 [RST, ACK] Seq=1 Ack=2 Win=0 Len=0
 1999 4.026374553  192.168.0.5 → 192.168.0.2  TCP 54 56619 → 2049 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 2000 4.049766424  192.168.0.5 → 192.168.0.2  TCP 54 56619 → 5432 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 2001 4.078797668  192.168.0.5 → 192.168.0.2  TCP 54 56619 → 514 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 2002 4.083224137  192.168.0.5 → 192.168.0.2  TCP 54 56619 → 1524 [FIN, PSH, URG] Seq=1 Win=1024 Urg=0 Len=0
 2003 13.796300252 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 2004 13.796316362 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
```
</details>
</details>


<details>
<summary>4. UDP-сканирование </summary>

```
sudo nmap -sU 192.168.0.2
Starting Nmap 7.93 ( https://nmap.org ) at 2024-07-19 18:32 +05
Nmap scan report for 192.168.0.2
Host is up (0.0051s latency).
Not shown: 993 closed udp ports (port-unreach)
PORT     STATE         SERVICE
53/udp   open          domain
68/udp   open|filtered dhcpc
69/udp   open|filtered tftp
111/udp  open          rpcbind
137/udp  open          netbios-ns
138/udp  open|filtered netbios-dgm
2049/udp open          nfs
MAC Address: 08:00:27:18:EE:BD (Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 2623.03 seconds
```

<details>
<summary>Дамп Tshark</summary>

```
3659 2127.030523636  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3660 2128.032796914  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3661 2129.035160468  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3662 2129.035791106  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3663 2130.037382105  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21784 Len=0
 3664 2131.040105003  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21784 Len=0
 3665 2131.047441358  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3666 2132.042324371  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 25709 Len=0
 3667 2133.043972068  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 25709 Len=0
 3668 2133.050748366  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3669 2134.045512449  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 16420 Len=0
 3670 2135.048233594  192.168.0.5 → 192.168.0.2  UDP 82 47731 → 49182 Len=40
 3671 2135.061077064  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3672 2136.051130938  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 16420 Len=0
 3673 2137.052862955  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 16420 Len=0
 3674 2138.054524557  192.168.0.5 → 192.168.0.2  UDP 42 47596 → 16420 Len=0
 3675 2138.065954072  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3676 2139.057681016  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3677 2140.058748071  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3678 2140.063024394  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3679 2141.059903802  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3680 2142.062290129  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3681 2142.062739014  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3682 2143.065393858  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 22695 Len=0
 3683 2144.067163358  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 22695 Len=0
 3684 2144.067809216  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3685 2145.069993004  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 639 Len=0
 3686 2146.072138520  192.168.0.5 → 192.168.0.2  UDP 82 47733 → 49182 Len=40
 3687 2147.074497859  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 639 Len=0
 3688 2147.074941344  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3689 2148.076696363  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3690 2148.211143168 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 3691 2148.211729574 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 3692 2149.078969002  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3693 2149.091929966  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3694 2150.080837153  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3695 2151.083496655  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3696 2151.084080221  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3697 2152.084569227  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19283 Len=0
 3698 2153.085636813  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19283 Len=0
 3699 2153.086219339  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3700 2154.087086760  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3701 2155.087631709  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3702 2156.088598058  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3703 2156.098671232  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3704 2157.089925027  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 2161 Len=0
 3705 2158.091008376  192.168.0.5 → 192.168.0.2  UDP 82 47735 → 49182 Len=40
 3706 2158.091600751  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3707 2159.091942629  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 2161 Len=0
 3708 2160.092897477  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 2161 Len=0
 3709 2160.099119801  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3710 2160.353834379 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 3711 2160.353850110 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 3712 2161.093935830  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3713 2162.094943857  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3714 2162.101047760  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3715 2163.095286463  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19165 Len=0
 3716 2164.095649713  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19165 Len=0
 3717 2165.096433533  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19165 Len=0
 3718 2165.109630398  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3719 2166.097667692  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21360 Len=0
 3720 2167.098354529  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21360 Len=0
 3721 2167.099148446  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3722 2168.099345934  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20522 Len=0
 3723 2169.101550178  192.168.0.5 → 192.168.0.2  UDP 82 47737 → 49182 Len=40
 3724 2169.109637661  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3725 2170.102637862  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 20522 Len=0
 3726 2171.104214919  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 20522 Len=0
 3727 2171.104817015  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3728 2172.106488106  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1021 Len=0
 3729 2173.106965648  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1021 Len=0
 3730 2174.108336770  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 1021 Len=0
 3731 2174.120958851  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3732 2175.110355608  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3733 2176.112716002  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3734 2176.123235640  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3735 2177.114327929  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3736 2178.114947474  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3737 2178.115610661  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3738 2179.115814127  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3739 2180.117388577  192.168.0.5 → 192.168.0.2  UDP 82 47739 → 49182 Len=40
 3740 2180.123546931  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3741 2181.118876643  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3742 2182.123248524  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3743 2183.125897490  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3744 2183.136798723  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3745 2184.130200621  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3746 2185.133426796  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3747 2185.137817961  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3748 2185.333763639 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 3749 2185.342086844 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 3750 2186.135650065  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19719 Len=0
 3751 2187.138136727  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19719 Len=0
 3752 2187.138751954  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3753 2188.140594787  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 68 Len=0
 3754 2189.142602056  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 68 Len=0
 3755 2190.143549359  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 68 Len=0
 3756 2191.147335547  192.168.0.5 → 192.168.0.2  UDP 82 47741 → 49182 Len=40
 3757 2191.150405678  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3758 2192.151141939  192.168.0.5 → 192.168.0.2  UDP 42 47596 → 68 Len=0
 3759 2193.152737601  192.168.0.5 → 192.168.0.2  UDP 42 47598 → 68 Len=0
 3760 2194.157211008  192.168.0.5 → 192.168.0.2  UDP 42 47600 → 68 Len=0
 3761 2195.160789690  192.168.0.5 → 192.168.0.2  UDP 42 47602 → 68 Len=0
 3762 2196.163761366  192.168.0.5 → 192.168.0.2  UDP 42 47604 → 68 Len=0
 3763 2197.166940287  192.168.0.5 → 192.168.0.2  UDP 42 47606 → 68 Len=0
 3764 2198.169341911  192.168.0.5 → 192.168.0.2  UDP 42 47608 → 68 Len=0
 3765 2199.170032955  192.168.0.5 → 192.168.0.2  UDP 42 47610 → 68 Len=0
 3766 2200.172191665  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21663 Len=0
 3767 2200.172796871  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3768 2201.173755174  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 781 Len=0
 3769 2201.179020239  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3770 2202.175545188  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3771 2202.176183195  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3772 2203.177290233  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20117 Len=0
 3773 2203.181335904  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3774 2204.182313317  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 3659 Len=0
 3775 2204.185541941  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3776 2205.185544409  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 2002 Len=0
 3777 2205.199199222  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3778 2206.188166635  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 3779 2206.193547200  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 3780 2207.190939067  192.168.0.5 → 192.168.0.2  TFTP 102 Unknown (0x303a)
 3781 2207.191012188  192.168.0.5 → 192.168.0.2  TFTP 75 Unknown (0x301f)
 3782 2207.202285675  192.168.0.2 → 192.168.0.5  ICMP 130 Destination unreachable (Port unreachable)
 3783 2208.193158637  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3784 2209.195011868  192.168.0.5 → 192.168.0.2  UDP 82 47743 → 49182 Len=40
 3785 2209.202512416  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3786 2210.196800459  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3787 2211.198036813  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3788 2212.199147988  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3789 2212.199775484  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3790 2213.202454548  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 9199 Len=0
 3791 2214.204912359  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 9199 Len=0
 3792 2214.205537225  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3793 2215.208415283  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20126 Len=0
 3794 2215.483039764 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 3795 2215.483055954 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 3796 2216.211062234  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 20126 Len=0
 3797 2216.223647747  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3798 2217.215035103  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3799 2218.217553652  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3800 2218.218173469  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3801 2219.219919993  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3802 2220.221084746  192.168.0.5 → 192.168.0.2  UDP 82 47745 → 49182 Len=40
 3803 2221.223911251  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3804 2221.230240988  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3805 2221.428322078 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 3806 2221.434210381 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 3807 2222.226560909  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17823 Len=0
 3808 2223.229192080  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17823 Len=0
 3809 2223.232312103  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3810 2224.229714283  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 26966 Len=0
 3811 2225.229847935  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 26966 Len=0
 3812 2225.239799540  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3813 2226.233182965  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19707 Len=0
 3814 2227.235234308  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19707 Len=0
 3815 2228.239218674  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19707 Len=0
 3816 2228.239874942  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3817 2229.241409296  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3818 2230.243825262  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3819 2230.247202298  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3820 2231.245628345  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 26720 Len=0
 3821 2232.247155529  192.168.0.5 → 192.168.0.2  UDP 82 47747 → 49182 Len=40
 3822 2232.259545361  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3823 2233.250743451  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 26720 Len=0
 3824 2234.251972798  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 26720 Len=0
 3825 2234.252591695  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3826 2235.254025830  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 996 Len=0
 3827 2236.255572581  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 996 Len=0
 3828 2237.257570312  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 996 Len=0
 3829 2237.258233178  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3830 2238.260365373  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 29823 Len=0
 3831 2239.262262069  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 29823 Len=0
 3832 2239.263214389  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3833 2240.264050769  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 88 Len=0
 3834 2241.265323985  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 88 Len=0
 3835 2241.265965202  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3836 2242.266539777  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3837 2243.268085407  192.168.0.5 → 192.168.0.2  UDP 82 47749 → 49182 Len=40
 3838 2243.278199784  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3839 2244.269113743  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3840 2245.271018573  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3841 2246.275751417  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3842 2246.276399955  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3843 2247.276972098  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 3844 2248.278880662  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 3845 2248.291108240  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 3846 2249.279104609  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3847 2250.280725665  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3848 2250.281494614  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3849 2251.282124884  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3850 2252.283089602  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3851 2252.283663498  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3852 2253.283452078  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3853 2254.284699947  192.168.0.5 → 192.168.0.2  UDP 82 47751 → 49182 Len=40
 3854 2255.285808918  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3855 2255.297590954  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3856 2256.287007874  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21303 Len=0
 3857 2257.287644918  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21303 Len=0
 3858 2257.300947340  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3859 2258.290983663 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 3860 2258.292897844 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 3861 2258.293322027  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3862 2259.294288221  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3863 2259.298457316  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3864 2260.295901187  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3865 2261.297428474  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3866 2261.298486066  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3867 2262.298755064  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19995 Len=0
 3868 2263.300148397  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19995 Len=0
 3869 2264.303640620  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19995 Len=0
 3870 2264.308808514  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3871 2265.307019322  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3872 2266.310317587  192.168.0.5 → 192.168.0.2  UDP 82 47753 → 49182 Len=40
 3873 2266.311221377  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3874 2267.313674819  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3875 2268.315625748  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3876 2268.324636374  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3877 2269.317562920  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3878 2270.320642168  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3879 2270.321251214  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3880 2271.323275515  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21468 Len=0
 3881 2272.324819546  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21468 Len=0
 3882 2272.530294893 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 3883 2272.530311974 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 3884 2273.326761883  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 21468 Len=0
 3885 2273.338217937  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3886 2274.330139809  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 664 Len=0
 3887 2275.332455389  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 664 Len=0
 3888 2275.333144556  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3889 2276.335246406  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19933 Len=0
 3890 2277.337702494  192.168.0.5 → 192.168.0.2  UDP 82 47755 → 49182 Len=40
 3891 2277.338451433  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3892 2278.342859835  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19933 Len=0
 3893 2279.346726387  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19933 Len=0
 3894 2279.349661428  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3895 2280.349844723  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3896 2281.353767582  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3897 2282.357034966  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3898 2282.369848056  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3899 2283.359039393  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 7000 Len=0
 3900 2284.361403275  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 7000 Len=0
 3901 2284.369827827  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3902 2285.362242175  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3903 2286.364627195  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3904 2286.371956935  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3905 2287.368892969  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 23608 Len=0
 3906 2288.369671450  192.168.0.5 → 192.168.0.2  UDP 82 47757 → 49182 Len=40
 3907 2288.370943324  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3908 2289.370171680  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 23608 Len=0
 3909 2290.374733107  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 23608 Len=0
 3910 2290.375342135  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3911 2291.377242277  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3912 2292.381377247  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3913 2293.383003114  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3914 2293.393269265  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3915 2294.384710606  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 539 Len=0
 3916 2295.386992577  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 539 Len=0
 3917 2295.400058437  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3918 2295.411328990 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 3919 2295.423492671 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 3920 2296.389972371  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21644 Len=0
 3921 2297.391700412  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21644 Len=0
 3922 2297.400755239  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3923 2298.393811562  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3924 2299.397902807  192.168.0.5 → 192.168.0.2  UDP 82 47759 → 49182 Len=40
 3925 2300.402022244  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3926 2300.402957575  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3927 2301.405445940  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21568 Len=0
 3928 2302.408964879  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21568 Len=0
 3929 2302.412758870  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3930 2303.411662314  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3931 2304.414683525  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3932 2304.423670173  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3933 2305.416056262  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3934 2306.417110149  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3935 2306.428392571  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3936 2307.418615333  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3937 2308.419124270  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3938 2309.419277198  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3939 2309.431697233  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3940 2310.421821205  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3941 2311.424850621  192.168.0.5 → 192.168.0.2  UDP 82 47761 → 49182 Len=40
 3942 2311.425485168  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3943 2312.428384086  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3944 2313.431854003  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3945 2313.432510231  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3946 2314.434486374  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 16829 Len=0
 3947 2315.435798766  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 16829 Len=0
 3948 2315.436476474  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3949 2316.438405584  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17018 Len=0
 3950 2317.439491819  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17018 Len=0
 3951 2318.440562587  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 17018 Len=0
 3952 2318.443714652  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3953 2319.442292565  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19489 Len=0
 3954 2320.444767356  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19489 Len=0
 3955 2320.445440504  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3956 2321.446989118  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 2051 Len=0
 3957 2322.447631025  192.168.0.5 → 192.168.0.2  UDP 82 47763 → 49182 Len=40
 3958 2322.457802906  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3959 2323.448788720  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 2051 Len=0
 3960 2324.450079871  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 2051 Len=0
 3961 2324.451011792  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3962 2325.451087663  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 8181 Len=0
 3963 2326.451405520  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 8181 Len=0
 3964 2327.453359507  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 8181 Len=0
 3965 2327.453995204  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3966 2328.454655292  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3967 2329.455924219  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3968 2329.459268785  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3969 2329.786307665 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 3970 2329.786326035 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 3971 2330.457544492  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3972 2331.459047519  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3973 2331.464387868  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3974 2332.460683070  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3975 2332.531029540 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 3976 2332.536426581 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 3977 2333.461734060  192.168.0.5 → 192.168.0.2  UDP 82 47765 → 49182 Len=40
 3978 2333.468156820  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3979 2334.463198235  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3980 2335.464110048  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3981 2336.465272418  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3982 2336.471714349  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3983 2337.467002896  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3984 2338.467260441  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 3985 2338.477220840  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3986 2339.468583323  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 22996 Len=0
 3987 2340.470081009  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 22996 Len=0
 3988 2340.483012390  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3989 2341.471012751  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 657 Len=0
 3990 2342.471217910  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 657 Len=0
 3991 2343.472125489  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 657 Len=0
 3992 2343.472763326  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3993 2344.473163873  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17237 Len=0
 3994 2345.474425703  192.168.0.5 → 192.168.0.2  UDP 82 47767 → 49182 Len=40
 3995 2345.475023969  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 3996 2346.475096299  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17237 Len=0
 3997 2347.476079233  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 17237 Len=0
 3998 2347.476789480  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 3999 2348.477718106  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 5500 Len=0
 4000 2349.479327702  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 5500 Len=0
 4001 2350.481255736  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 5500 Len=0
 4002 2350.481916382  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4003 2351.482967689  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 217 Len=0
 4004 2352.483517123  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 217 Len=0
 4005 2352.484128830  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4006 2353.485241643  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17302 Len=0
 4007 2354.486260818  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17302 Len=0
 4008 2354.487006656  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4009 2355.487511281  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4010 2356.488655524  192.168.0.5 → 192.168.0.2  UDP 82 47769 → 49182 Len=40
 4011 2356.500554725  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4012 2357.490245706  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4013 2358.490968111  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4014 2359.491504176  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4015 2359.492141165  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4016 2360.492739203  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19130 Len=0
 4017 2361.494500859  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19130 Len=0
 4018 2361.505228619  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4019 2362.495034124  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4020 2363.495911626  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4021 2363.506921299  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4022 2364.497436668  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4023 2365.498381737  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4024 2366.498989844  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4025 2366.499690912  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4026 2367.499429684  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 30704 Len=0
 4027 2368.500734276  192.168.0.5 → 192.168.0.2  UDP 82 47771 → 49182 Len=40
 4028 2368.510372693  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4029 2369.502408116  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 30704 Len=0
 4030 2370.503057556  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 30704 Len=0
 4031 2370.503691543  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4032 2371.503676062  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 767 Len=0
 4033 2372.504594394  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 767 Len=0
 4034 2372.505239051  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4035 2373.505632779  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 16919 Len=0
 4036 2374.507034041  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 16919 Len=0
 4037 2374.515317901 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 4038 2374.522278768 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 4039 2375.508548035  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 16919 Len=0
 4040 2375.509356636  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4041 2376.509600170  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4042 2377.510521696  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4043 2377.511334125  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4044 2378.511108921  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17487 Len=0
 4045 2379.512863883  192.168.0.5 → 192.168.0.2  UDP 82 47773 → 49182 Len=40
 4046 2379.513482510  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4047 2380.514018091  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17487 Len=0
 4048 2381.516119602  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 17487 Len=0
 4049 2382.517581388  192.168.0.5 → 192.168.0.2  UDP 42 47596 → 17487 Len=0
 4050 2382.519772753  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4051 2383.519210541  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 685 Len=0
 4052 2384.520845665  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 685 Len=0
 4053 2384.532668925  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4054 2385.523010688  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 3296 Len=0
 4055 2386.523959522  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 3296 Len=0
 4056 2386.531357004  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4057 2387.029007281 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 4058 2387.029028970 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 4059 2387.525620346  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19273 Len=0
 4060 2388.526613736  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19273 Len=0
 4061 2389.527034162  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19273 Len=0
 4062 2389.527682259  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4063 2390.527565643  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 24007 Len=0
 4064 2391.528736623  192.168.0.5 → 192.168.0.2  UDP 82 47775 → 49182 Len=40
 4065 2391.529339900  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4066 2392.530126578  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 24007 Len=0
 4067 2393.531125613  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 24007 Len=0
 4068 2393.531805551  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4069 2394.532669345  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4070 2395.533755627  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4071 2395.534356303  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4072 2396.535179645  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19141 Len=0
 4073 2397.537004630  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19141 Len=0
 4074 2398.538467734  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19141 Len=0
 4075 2398.539280763  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4076 2399.539284364  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19682 Len=0
 4077 2400.540286929  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19682 Len=0
 4078 2400.540901026  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4079 2401.542103285  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 24606 Len=0
 4080 2402.543163808  192.168.0.5 → 192.168.0.2  UDP 82 47777 → 49182 Len=40
 4081 2402.556557877  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4082 2403.544785667  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 24606 Len=0
 4083 2404.546102989  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 24606 Len=0
 4084 2404.555626385  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4085 2405.547865126  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21206 Len=0
 4086 2406.550109340  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21206 Len=0
 4087 2407.551307469  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 21206 Len=0
 4088 2407.561413150  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4089 2408.554038147  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 28543 Len=0
 4090 2409.558003670  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 28543 Len=0
 4091 2409.559014060  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4092 2410.559174245  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 16680 Len=0
 4093 2411.561010311  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 16680 Len=0
 4094 2411.567174299  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4095 2412.562410164  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 686 Len=0
 4096 2413.565010445  192.168.0.5 → 192.168.0.2  UDP 82 47779 → 49182 Len=40
 4097 2413.565786632  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4098 2414.569172745  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 686 Len=0
 4099 2415.571390245  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 686 Len=0
 4100 2416.574021534  192.168.0.5 → 192.168.0.2  UDP 42 47596 → 686 Len=0
 4101 2416.574936804  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4102 2417.576199292  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 3703 Len=0
 4103 2418.578666257  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 3703 Len=0
 4104 2418.588221562  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4105 2418.803280944 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 4106 2418.803920851 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 4107 2419.579951856  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 8001 Len=0
 4108 2420.582121482  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 8001 Len=0
 4109 2420.595508181  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4110 2421.584212006  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 22029 Len=0
 4111 2422.587017374  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 22029 Len=0
 4112 2423.588926203  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 22029 Len=0
 4113 2423.598224988  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4114 2424.590350209  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1813 Len=0
 4115 2425.591319215  192.168.0.5 → 192.168.0.2  UDP 82 47781 → 49182 Len=40
 4116 2425.603808665  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4117 2426.591495314  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1813 Len=0
 4118 2427.592404814  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 1813 Len=0
 4119 2427.603311837  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4120 2428.593518807  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1646 Len=0
 4121 2429.595256443  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1646 Len=0
 4122 2429.601990159  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4123 2430.599067063  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4124 2431.601543343  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4125 2432.604803032  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4126 2432.615528573  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4127 2433.605834571  192.168.0.5 → 192.168.0.2  TFTP 54 Unknown (0x0000)
 4128 2433.605912481  192.168.0.5 → 192.168.0.2  TFTP 72 Unknown (0x7777)
 4129 2433.607306187  192.168.0.2 → 192.168.0.5  TFTP 60 Unknown (0x0000)
 4130 2433.607374118  192.168.0.5 → 192.168.0.2  ICMP 82 Destination unreachable (Port unreachable)
 4131 2433.624969737  192.168.0.2 → 192.168.0.5  TFTP 104 Unknown (0x7777)
 4132 2433.625055027  192.168.0.5 → 192.168.0.2  ICMP 132 Destination unreachable (Port unreachable)
 4133 2434.608148327  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 16700 Len=0
 4134 2434.620746978  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4135 2435.612504509  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 18888 Len=0
 4136 2436.614924450  192.168.0.5 → 192.168.0.2  UDP 82 47783 → 49182 Len=40
 4137 2436.615830611  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4138 2437.617105054  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 18888 Len=0
 4139 2438.618980856  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 18888 Len=0
 4140 2439.620679644  192.168.0.5 → 192.168.0.2  UDP 42 47596 → 18888 Len=0
 4141 2439.625851223  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4142 2440.621446696  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 18004 Len=0
 4143 2441.622334235  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 18004 Len=0
 4144 2441.633698524  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4145 2442.623391987  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19789 Len=0
 4146 2443.624557828  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19789 Len=0
 4147 2443.627828443  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4148 2443.880065653 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 4149 2443.880098573 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 4150 2444.625476892  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4151 2445.627301683  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4152 2445.630308557  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4153 2446.628768540  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19140 Len=0
 4154 2447.630561686  192.168.0.5 → 192.168.0.2  UDP 82 47785 → 49182 Len=40
 4155 2448.632333272  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19140 Len=0
 4156 2448.633097371  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4157 2449.632603843  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 28369 Len=0
 4158 2450.632795349  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 28369 Len=0
 4159 2450.633451795  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4160 2451.634370449  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 28641 Len=0
 4161 2452.634650370  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 28641 Len=0
 4162 2452.635289337  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4163 2453.635742562  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 9001 Len=0
 4164 2454.639036652  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 9001 Len=0
 4165 2454.639731280  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4166 2455.639668060  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21 Len=0
 4167 2456.641197940  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21 Len=0
 4168 2457.642463562  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 21 Len=0
 4169 2457.650311120  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4170 2458.644822678  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4171 2459.646322209  192.168.0.5 → 192.168.0.2  UDP 82 47787 → 49182 Len=40
 4172 2459.650383195  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4173 2460.649327897  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4174 2461.650984262  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4175 2461.657946120  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4176 2461.811336738 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 4177 2461.815612058 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 4178 2462.652704143  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20262 Len=0
 4179 2463.653746360  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 20262 Len=0
 4180 2463.665109519  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4181 2464.655743636  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4182 2465.656684555  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4183 2466.658760739  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4184 2466.672290503  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4185 2467.660504844  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 27707 Len=0
 4186 2468.661653174  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 27707 Len=0
 4187 2468.662288200  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4188 2469.662555394  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 26407 Len=0
 4189 2470.664954192  192.168.0.5 → 192.168.0.2  UDP 82 47789 → 49182 Len=40
 4190 2470.665779781  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4191 2471.666989290  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 26407 Len=0
 4192 2472.669351293  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 26407 Len=0
 4193 2472.675131449  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4194 2473.670630469  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 4000 Len=0
 4195 2474.671077245  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 4000 Len=0
 4196 2475.672398125  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 4000 Len=0
 4197 2475.687806180  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4198 2476.672884347  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 25157 Len=0
 4199 2477.673864618  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 25157 Len=0
 4200 2477.681950850  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4201 2478.676512232  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21060 Len=0
 4202 2479.678861086  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21060 Len=0
 4203 2479.679453252  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4204 2480.682904698  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 944 Len=0
 4205 2481.683991963  192.168.0.5 → 192.168.0.2  UDP 82 47791 → 49182 Len=40
 4206 2482.686189730  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 944 Len=0
 4207 2482.693383481  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4208 2483.688427812  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 16548 Len=0
 4209 2484.690674604  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 16548 Len=0
 4210 2484.698353102  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4211 2485.691760295  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4212 2486.693057804  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4213 2486.695977836  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4214 2487.695011081  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1524 Len=0
 4215 2488.699664951  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1524 Len=0
 4216 2488.708849775  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4217 2489.701177827  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 3664 Len=0
 4218 2490.702966413  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 3664 Len=0
 4219 2491.704213611  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 3664 Len=0
 4220 2491.704896858  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4221 2492.707884470  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1214 Len=0
 4222 2493.710965946  192.168.0.5 → 192.168.0.2  UDP 82 47793 → 49182 Len=40
 4223 2493.720844070  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4224 2494.713780770  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1214 Len=0
 4225 2495.716037490  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 1214 Len=0
 4226 2495.723289355  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4227 2496.718072742  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4228 2497.719644778  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4229 2497.720323967  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4230 2498.721778806  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4231 2499.724178526  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4232 2500.083868306 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 4233 2500.083886516 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 4234 2500.725602269  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4235 2500.726399858  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4236 2501.726972583  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20146 Len=0
 4237 2502.727912683  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 20146 Len=0
 4238 2502.732732348  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4239 2503.729281142  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17359 Len=0
 4240 2503.796543990 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 4241 2503.797196829 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 4242 2504.730777455  192.168.0.5 → 192.168.0.2  UDP 82 47795 → 49182 Len=40
 4243 2504.740111860  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4244 2505.731056367  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17359 Len=0
 4245 2506.732052167  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 17359 Len=0
 4246 2506.743574569  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4247 2507.734043132  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 112 Len=0
 4248 2508.736147541  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 112 Len=0
 4249 2509.737325251  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 112 Len=0
 4250 2509.737900787  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4251 2510.739110910  192.168.0.5 → 192.168.0.2  TFTP 44 Unknown (0x0000)[Malformed Packet]
 4252 2511.740095193  192.168.0.5 → 192.168.0.2  TFTP 44 Unknown (0x0000)[Malformed Packet]
 4253 2511.740808953  192.168.0.2 → 192.168.0.5  ICMP 72 Destination unreachable (Port unreachable)
 4254 2512.741068799  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4255 2513.742469232  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4256 2513.743077229  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4257 2514.743115979  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19728 Len=0
 4258 2515.743357592  192.168.0.5 → 192.168.0.2  UDP 82 47797 → 49182 Len=40
 4259 2516.745085295  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19728 Len=0
 4260 2516.745692462  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4261 2517.746457628  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4262 2518.747017851  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4263 2518.747753160  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4264 2519.747895322  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4265 2520.749889147  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4266 2520.761099206  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4267 2521.752008067  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19193 Len=0
 4268 2522.753305458  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19193 Len=0
 4269 2522.764713559  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4270 2523.754154048  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20082 Len=0
 4271 2524.755076210  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 20082 Len=0
 4272 2525.755456249  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 20082 Len=0
 4273 2525.763868236  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4274 2526.756285795  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4275 2527.757829901  192.168.0.5 → 192.168.0.2  UDP 82 47799 → 49182 Len=40
 4276 2527.758451558  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4277 2527.926045903  192.168.0.2 → 192.168.0.255 BROWSER 286 Local Master Announcement METASPLOITABLE, Workstation, Server, Print Queue Server, Xenix Server, NT Workstation, NT Server, Master Browser
 4278 2527.926873953  192.168.0.2 → 192.168.0.255 BROWSER 257 Domain/Workgroup Announcement WORKGROUP, NT Workstation, Domain Enum
 4279 2528.759065886  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4280 2529.760586426  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4281 2529.761162133  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4282 2530.761744485  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21476 Len=0
 4283 2531.763586213  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21476 Len=0
 4284 2531.764175971  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4285 2532.765335833  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21358 Len=0
 4286 2533.766237886  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21358 Len=0
 4287 2534.767605285  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 21358 Len=0
 4288 2534.768215132  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4289 2535.768825886  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4290 2536.770295251  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4291 2536.770981710  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4292 2537.771007892  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 2362 Len=0
 4293 2538.771394817  192.168.0.5 → 192.168.0.2  UDP 82 47801 → 49182 Len=40
 4294 2538.775247083  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4295 2539.773432898  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 2362 Len=0
 4296 2540.774369814  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 2362 Len=0
 4297 2540.775278374  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4298 2541.775586966  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4299 2542.776248147  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4300 2543.777591257  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4301 2543.782784457  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4302 2544.780415836  192.168.0.5 → 192.168.0.2  TFTP 90 Unknown (0xe300)
 4303 2544.780490606  192.168.0.5 → 192.168.0.2  TFTP 90 Unknown (0xd900)
 4304 2545.781911632  192.168.0.5 → 192.168.0.2  TFTP 90 Unknown (0xe300)
 4305 2545.781993523  192.168.0.5 → 192.168.0.2  TFTP 90 Unknown (0xd900)
 4306 2545.793444604  192.168.0.2 → 192.168.0.5  ICMP 118 Destination unreachable (Port unreachable)
 4307 2546.784390421  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21247 Len=0
 4308 2546.803475260 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 4309 2546.804043178 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 4310 2547.785835860  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21247 Len=0
 4311 2547.796856797  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4312 2548.787035978  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4313 2549.787871435  192.168.0.5 → 192.168.0.2  UDP 82 47803 → 49182 Len=40
 4314 2549.788511182  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4315 2550.789004788  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4316 2551.790321665  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4317 2552.791028545  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4318 2552.804451730  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4319 2553.792703710  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4320 2554.793993383  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4321 2554.795528430  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4322 2555.795524100  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4323 2556.796817596  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4324 2556.807905943  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4325 2557.798552029  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1200 Len=0
 4326 2558.799057272  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1200 Len=0
 4327 2558.799646507  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4328 2559.082654230 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 Who has 192.168.0.5? Tell 192.168.0.2
 4329 2559.082693960 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 192.168.0.5 is at 08:00:27:d0:bd:0b
 4330 2559.799658656  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4331 2560.800843441  192.168.0.5 → 192.168.0.2  UDP 82 47805 → 49182 Len=40
 4332 2561.801836445  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4333 2561.813372947  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4334 2562.803117503  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4335 2563.804621269  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4336 2563.805714520  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4337 2564.805652019  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4338 2565.807105257  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4339 2565.807835004  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4340 2566.807996461  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4341 2567.809361891  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4342 2568.811004888  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4343 2568.820568618  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4344 2569.813788069  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4345 2570.815164375  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4346 2570.828327309  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4347 2571.818826561  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1718 Len=0
 4348 2572.822214037  192.168.0.5 → 192.168.0.2  UDP 82 47807 → 49182 Len=40
 4349 2572.823193097  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4350 2573.822813521  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1718 Len=0
 4351 2574.826741116  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 1718 Len=0
 4352 2574.832852388  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4353 2575.828956074  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 17077 Len=0
 4354 2576.832198046  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 17077 Len=0
 4355 2577.834780660  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 17077 Len=0
 4356 2577.835925463  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4357 2578.837054005  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 989 Len=0
 4358 2579.838027416  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 989 Len=0
 4359 2579.839079599  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4360 2580.839249882  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4361 2581.840427050  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4362 2581.841133159  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4363 2582.844210550  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 20717 Len=0
 4364 2583.848832572  192.168.0.5 → 192.168.0.2  UDP 82 47809 → 49182 Len=40
 4365 2583.853886570  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4366 2584.851862447  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 20717 Len=0
 4367 2585.854931855  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 20717 Len=0
 4368 2586.857222225  192.168.0.5 → 192.168.0.2  UDP 42 47596 → 20717 Len=0
 4369 2586.857935194  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4370 2587.859279344  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 21556 Len=0
 4371 2588.860473506  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 21556 Len=0
 4372 2588.869697903  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4373 2589.862175137  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4374 2590.068895619 PcsCompu_d0:bd:0b → PcsCompu_18:ee:bd ARP 42 Who has 192.168.0.2? Tell 192.168.0.5
 4375 2590.069654429 PcsCompu_18:ee:bd → PcsCompu_d0:bd:0b ARP 60 192.168.0.2 is at 08:00:27:18:ee:bd
 4376 2590.865272795  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4377 2590.877597517  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4378 2591.866027938  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 28493 Len=0
 4379 2592.870982641  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 28493 Len=0
 4380 2592.871663178  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4381 2593.872579306  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4382 2594.877018638  192.168.0.5 → 192.168.0.2  UDP 82 47811 → 49182 Len=40
 4383 2595.879429749  192.168.0.5 → 192.168.0.2  TFTP 114 Unknown (0x0500)
 4384 2595.882415593  192.168.0.2 → 192.168.0.5  ICMP 142 Destination unreachable (Port unreachable)
 4385 2596.882873933  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 18360 Len=0
 4386 2597.884429069  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 18360 Len=0
 4387 2597.885095186  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4388 2598.887317759  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 782 Len=0
 4389 2599.888811117  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 782 Len=0
 4390 2599.895688607  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4391 2600.889844331  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4392 2601.892307904  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4393 2601.902980368  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4394 2602.894367974  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 22914 Len=0
 4395 2603.895434243  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 22914 Len=0
 4396 2604.896725438  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 22914 Len=0
 4397 2604.897401246  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4398 2605.898734653  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 5093 Len=0
 4399 2606.902468100  192.168.0.5 → 192.168.0.2  UDP 82 47813 → 49182 Len=40
 4400 2606.915515412  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4401 2607.905305118  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 5093 Len=0
 4402 2608.908649213  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 5093 Len=0
 4403 2608.909289112  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4404 2609.912127115  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4405 2610.913162357  192.168.0.5 → 192.168.0.2  TFTP 82 Unknown (0x3eec)
 4406 2610.924432248  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4407 2611.914530165  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19722 Len=0
 4408 2612.915639763  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19722 Len=0
 4409 2613.916612813  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19722 Len=0
 4410 2613.917252979  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4411 2614.919164212  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 983 Len=0
 4412 2615.919534376  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 983 Len=0
 4413 2615.920224276  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4414 2616.921147028  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 19695 Len=0
 4415 2617.925545245  192.168.0.5 → 192.168.0.2  UDP 82 47815 → 49182 Len=40
 4416 2617.926342754  192.168.0.2 → 192.168.0.5  ICMP 110 Destination unreachable (Port unreachable)
 4417 2618.928837710  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 19695 Len=0
 4418 2619.931821073  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 19695 Len=0
 4419 2619.933972348  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
 4420 2620.934211912  192.168.0.5 → 192.168.0.2  UDP 42 47590 → 1886 Len=0
 4421 2621.935278207  192.168.0.5 → 192.168.0.2  UDP 42 47592 → 1886 Len=0
 4422 2622.936688096  192.168.0.5 → 192.168.0.2  UDP 42 47594 → 1886 Len=0
 4423 2622.949947702  192.168.0.2 → 192.168.0.5  ICMP 70 Destination unreachable (Port unreachable)
```
</details>
</details>

<details>
<summary>Отличия режимов сканирования с точки зрения сетевого трафика:</summary>
1. SYN Scan (-sS)
2. FIN Scan (-sF)
</details>

<details>
<summary>Ответы сервера:</summary>

</details>
