# Metasploit

Metasploit is an exploitation framework (aka penetration framework) , build for security professional to support penetration testing.

**Most related alternative**
Cobalt strike – closed source/ commercial use only

## Why prefer Metasploit?
It supports and provides sufficient tools for almost all the phases of the penetration testing.

**Notations**
```mermaid
graph TB
A(Metasploit support)
B(Commercial version only)
style A fill:lightgreen,color:black,stroke:#333,stroke-width:1px
style B fill:orange,color:black,stroke:#333,stroke-width:1px

```
**Phases of penetration testing**
```mermaid
graph LR
A(Reconnance) --> B(Scanning)
B --> C(Gaining Access)
C --> D(Maintaining Access)
D --> E(Clearing Tracks)
E --> F(Reporting)

style A fill:lightgreen,color:black,stroke-width:1px
style B fill:lightgreen,color:black,stroke-width:1px
style C fill:lightgreen,color:black,stroke-width:1px
style D fill:lightgreen,color:black,stroke-width:1px
style E fill:lightgreen,color:black,stroke-width:1px
style F fill:orange,color:black,stroke-width:1px
```

## Modules provided by Metasploit?

 - exploits – the code that if executed takes advantage of the vulnerability to get unauthorized access to the desired system. Usually by the payload.

- payload – used by exploits. payload is a piece of code that are run by the target after successful exploitation (for backdoor, add new user, privilege escalation)

- Auxiliary – pre-exploitation features (scanning, fuzzing, sniffing)

- Encoders – to bypass firewall, IDS, IPS, Antivirus

- NOPS – no operation, use to ensure that if using multiple payloads, it is of same size. It ensures the proper execution of the instructions.

## How to Get Started?

### Metasploit Framework is Accessible Through:

 - Msfconsole [Metasploit Unleashed (offsec.com)](https://www.offsec.com/metasploit-unleashed/msfconsole/)
 - Armitage


**\#NOTE:** In case you are using any pen-testing OS like [Kali Linux](https://www.kali.org/) or [Parrot Security](https://www.parrotsec.org/), Metasploit  framework comes pre-installed with Msfconsole in them. 


## Penetrating Windows 7 Machine?

**Attacker's Machine:** Kali Linux 2022.2

**Target Machine:** Windows 7

**Prerequisite:** 

 - The environment is setup oracle vmware, in NAT connection 
 - The firewall of the windows is already disabled in this demonstration
 - The Attacker and Target machine is connected over the save network. i.e., they are in same subnet.  

### Attacker Machine:
****
Open msfconsole
```bash
sudo msfconsole
```

**Finding the Target's IP**
Find your eth0 IP address, to identify subnet to scan, because as the target machine is connected with the same router, it must be in the same subnet as well.
```bash
msf> ifconfig
```
Let attaker's IP: 192.168.126.128
Running a simple no-port host discovery nmap scan on the sub-network to find the target's machine.
```bash
msf> nmap -sn 192.168.126.0/24
```
![scan 1  result](https://github.com/000Sushant/metasploit_docs/blob/main/scan1.png)

One of this host could be the target machine we are looking for, so let's perform the osscan to be sure.
```bash
msf> nmap -O 192.168.126.0/24
```
![scan 2  result](https://github.com/000Sushant/metasploit_docs/blob/main/scan2.png)
we found the IP address of the target machine.
Target IP: 192.168.126.132

**Finding Vulnerability in Target Machine**
Checking if the current version of OS the target machine is running on is having any publicly known vulnerability. This can be achieved by nmap script scan.
```bash
msf> nmap --script="vuln" 192.168.126.132
```
![scan 3  result](https://github.com/000Sushant/metasploit_docs/blob/main/scan3.png)

We identified that the target's machine is vulnerable for remote code execution, by the exploit smb-vuln-ms17-010. more details could be gathered from [CVE-2017-0143](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0143).

**Searching and Setting up the Exploit**


 
