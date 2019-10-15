# oscp
Planning and prepare for OSCP

Checks

[ ] Scanning

[ ] Enumeration

[ ] Exploitation

[ ] Privilege Escalation

[ ] Flags

[ ] Post Exploitation


------------------------------------------------------------------------------------------------------------------------

[ ] Scanning

  Fping
  
    fping is a small command line tool to send ICMP (Internet Control Message Protocol) echo request to network hosts, similar to ping, but much higher performing when pinging multiple hosts. fping totally differs from ping in that you can define any number of hosts on the command line or specify a file with the list of IP addresses or hosts to ping.
    
    For install:
    # apt install fping  [On Debian/Ubuntu]
    
    Use examples:
      For scan a range:
        # fping -g 192.168.1.0/24
        
  Nmap
  
    Nmap ("Network Mapper") is a free and open source (license) utility for network discovery and security auditing. Many systems and network administrators also find it useful for tasks such as network inventory, managing service upgrade schedules, and monitoring host or service uptime. Nmap uses raw IP packets in novel ways to determine what hosts are available on the network, what services (application name and version) those hosts are offering, what operating systems (and OS versions) they are running, what type of packet filters/firewalls are in use, and dozens of other characteristics. It was designed to rapidly scan large networks, but works fine against single hosts.
      
    For Install:
    # apt install nmap
    
    Use examples:
      Quick TCP Scan
        nmap -sC -sV -vv -oA quick 192.168.1.1

      Quick UDP Scan
        nmap -sU -sV -vv -oA quick_udp 192.168.1.1

      Full TCP Scan
        nmap -sC -sV -p- -vv -oA full 192.168.1.1
        
        
      -p- scans 1-65535 so you can omit 1-65535.

    I use this one a lot in general

    nmap -p 445 -vv --script=smb-vuln-cve2009-3103.nse,smb-vuln-ms06-025.nse,smb-vuln-ms07-029.nse,smb-vuln-ms08-067.nse,smb-vuln-ms10-054.nse,smb-vuln-ms10-061.nse,smb-vuln-ms17-010.nse 192.158.1.1
        
     More NMAP:
     nmap -sS -Pn 192.168.1.1 -vvv
     nmap -A -Pn 192.168.1.1 -vv
     nmap -sU -Pn 192.168.1.1 -vv
     ...
       
