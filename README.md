# 4. Execution_of_NetworkCommands

## NAME : Thaarakeshwar

## REG NUMBER : 212225040466

## AIM
Use of Network commands in Real Time environment

## Software
Command Prompt and Network Protocol Analyzer (Wireshark)

## Procedure
1. Open Command Prompt and run the basic networking commands below.
2. Start Wireshark, select the active interface, and capture the ping and traceroute PDUs.
3. Open Packet Tracer / a router CLI and run the router configuration commands.

### Basic network commands

| Command | Purpose |
|---|---|
| `ping 127.0.0.1` | Loopback test of the local TCP/IP stack |
| `ping -n 6 -l 500 1.1.1.1` | Ping with a set count (6) and packet size (500 bytes) |
| `netstat -s` | Statistics per protocol (IP, ICMP, TCP, UDP) |
| `netstat -e` | Ethernet interface statistics |
| `netsh interface ipv4 show excludedportrange protocol=tcp` | TCP port ranges reserved by Windows |
| `nslookup -type=aaaa google.com 8.8.8.8` | IPv6 (AAAA) record of a domain using Google DNS |
| `curl -V` | curl version and supported protocols |
| `sc query dhcp` | Status of the DHCP Client service |
| `sc qc dnscache` | Configuration of the DNS Client service |
| `sc query lanmanworkstation` | Status of the Workstation service |

### Router commands (Cisco IOS)

```
Router> enable                          ! user mode -> privileged mode
Router# configure terminal              ! privileged mode -> global config
Router(config)# hostname R1
Router(config)# interface fastEthernet 0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# exit
Router# show ip interface brief         ! interface status
Router# show ip route                   ! routing table
Router# show running-config             ! current configuration
Router# show version                    ! router processes and statistics
Router# copy running-config startup-config   ! save to permanent memory
Router# disable                         ! back to user mode
```

## Output

```
C:\Users\acer>ping 127.0.0.1

Pinging 127.0.0.1 with 32 bytes of data:
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128

Ping statistics for 127.0.0.1:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

```
C:\Users\acer>ping -n 6 -l 500 1.1.1.1

Pinging 1.1.1.1 with 500 bytes of data:
Reply from 1.1.1.1: bytes=500 time=100ms TTL=56
Reply from 1.1.1.1: bytes=500 time=68ms TTL=56
Reply from 1.1.1.1: bytes=500 time=89ms TTL=56
Reply from 1.1.1.1: bytes=500 time=67ms TTL=56
Reply from 1.1.1.1: bytes=500 time=67ms TTL=56
Reply from 1.1.1.1: bytes=500 time=74ms TTL=56

Ping statistics for 1.1.1.1:
    Packets: Sent = 6, Received = 6, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 67ms, Maximum = 100ms, Average = 77ms
```

```
C:\Users\acer>netstat -s

IPv4 Statistics

  Packets Received                   = 106669
  Received Header Errors             = 0
  Received Address Errors            = 4565
  Datagrams Forwarded                = 0
  Unknown Protocols Received         = 0
  Received Packets Discarded         = 56430
  Received Packets Delivered         = 145781
  Output Requests                    = 7306
  Routing Discards                   = 0
  Discarded Output Packets           = 0
  Output Packet No Route             = 15
  Reassembly Required                = 2097
  Reassembly Successful              = 516
  Reassembly Failures                = 0
  Datagrams Successfully Fragmented  = 0
  Datagrams Failing Fragmentation    = 0
  Fragments Created                  = 0

IPv6 Statistics

  Packets Received                   = 464101
  Received Header Errors             = 142
  Received Address Errors            = 73550
  Datagrams Forwarded                = 0
  Unknown Protocols Received         = 2
  Received Packets Discarded         = 4654
  Received Packets Delivered         = 391461
  Output Requests                    = 151455
  Routing Discards                   = 0
  Discarded Output Packets           = 5947
  Output Packet No Route             = 253
  Reassembly Required                = 1691
  Reassembly Successful              = 637
  Reassembly Failures                = 0
  Datagrams Successfully Fragmented  = 0
  Datagrams Failing Fragmentation    = 0
  Fragments Created                  = 0

ICMPv4 Statistics

                            Received    Sent
  Messages                  12          20
  Errors                    0           0
  Destination Unreachable   0           8
  Time Exceeded             0           0
  Parameter Problems        0           0
  Source Quenches           0           0
  Redirects                 0           0
  Echo Replies              8           4
  Echos                     4           8
  Timestamps                0           0
  Timestamp Replies         0           0
  Address Masks             0           0
  Address Mask Replies      0           0
  Router Solicitations      0           0
  Router Advertisements     0           0

ICMPv6 Statistics

                            Received    Sent
  Messages                  4593        1533
  Errors                    0           0
  Destination Unreachable   215         371
  Packet Too Big            0           0
  Time Exceeded             0           0
  Parameter Problems        0           0
  Echos                     0           0
  Echo Replies              0           0
  MLD Queries               0           0
  MLD Reports               2           0
  MLD Dones                 2           0
  Router Solicitations      0           46
  Router Advertisements     684         0
  Neighbor Solicitations    161         880
  Neighbor Advertisements   3529        236
  Redirects                 0           0
  Router Renumberings       0           0

TCP Statistics for IPv4

  Active Opens                        = 1840
  Passive Opens                       = 1688
  Failed Connection Attempts          = 812
  Reset Connections                   = 12
  Current Connections                 = 34
  Segments Received                   = 21170
  Segments Sent                       = 20274
  Segments Retransmitted              = 117

TCP Statistics for IPv6

  Active Opens                        = 2417
  Passive Opens                       = 0
  Failed Connection Attempts          = 672
  Reset Connections                   = 206
  Current Connections                 = 17
  Segments Received                   = 105878
  Segments Sent                       = 88903
  Segments Retransmitted              = 3727

UDP Statistics for IPv4

  Datagrams Received    = 103465
  No Ports              = 43556
  Receive Errors        = 1
  Datagrams Sent        = 1923

UDP Statistics for IPv6

  Datagrams Received    = 509812
  No Ports              = 742
  Receive Errors        = 3
  Datagrams Sent        = 55175
```

```
C:\Users\acer>netstat -e
Interface Statistics

                           Received            Sent

Bytes                    1125033480        54948976
Unicast packets              922056          330456
Non-unicast packets             150            3990
Discards                          0               0
Errors                            0               0
Unknown protocols                 0
```

```
C:\Users\acer>netsh interface ipv4 show excludedportrange protocol=tcp

Protocol tcp Port Exclusion Ranges

Start Port    End Port
----------    --------
        80          80
     28385       28385
     28390       28390
     50000       50059     *

* - Administered port exclusions.
```

```
C:\Users\acer>nslookup -type=aaaa google.com 8.8.8.8
Server:  dns.google
Address:  8.8.8.8

Non-authoritative answer:
Name:    google.com
Address:  2404:6800:4007:810::200e
```

```
C:\Users\acer>curl -V
curl 8.21.0 (Windows) libcurl/8.21.0 Schannel zlib/1.3.2 WinIDN WinLDAP
Release-Date: 2026-06-24
Protocols: dict file ftp ftps gopher gophers http https imap imaps ipfs ipns ldap ldaps mqtt mqtts pop3 pop3s smtp smtps telnet tftp ws wss
Features: alt-svc AsynchDNS HSTS HTTPS-proxy IDN IPv6 Kerberos Largefile libz SPNEGO SSL SSPI threadsafe Unicode UnixSockets
```

```
C:\Users\acer>sc query dhcp

SERVICE_NAME: dhcp
        TYPE               : 30  WIN32
        STATE              : 4  RUNNING
                                (STOPPABLE, NOT_PAUSABLE, ACCEPTS_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x0
```

```
C:\Users\acer>sc qc dnscache
[SC] QueryServiceConfig SUCCESS

SERVICE_NAME: dnscache
        TYPE               : 10  WIN32_OWN_PROCESS
        START_TYPE         : 2   AUTO_START
        ERROR_CONTROL      : 1   NORMAL
        BINARY_PATH_NAME   : C:\Windows\system32\svchost.exe -k NetworkService -p
        LOAD_ORDER_GROUP   : TDI
        TAG                : 0
        DISPLAY_NAME       : DNS Client
        DEPENDENCIES       : nsi
                           : Afd
        SERVICE_START_NAME : NT AUTHORITY\NetworkService
```

```
C:\Users\acer>sc query lanmanworkstation

SERVICE_NAME: lanmanworkstation
        TYPE               : 30  WIN32
        STATE              : 4  RUNNING
                                (STOPPABLE, PAUSABLE, IGNORES_SHUTDOWN)
        WIN32_EXIT_CODE    : 0  (0x0)
        SERVICE_EXIT_CODE  : 0  (0x0)
        CHECKPOINT         : 0x0
        WAIT_HINT          : 0x0
```

## Result

Thus Execution of Network commands Performed.
