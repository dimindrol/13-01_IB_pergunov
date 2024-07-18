# Домашнее задание к занятию "Уязвимости и атаки на информационные системы" - Пергунов Д.В

### Задание 1

1. Просканировали Хост с помощью команды NMAP  
<details>
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
</details>


### Задание 2

1. `Заполните здесь этапы выполнения, если требуется ....`


