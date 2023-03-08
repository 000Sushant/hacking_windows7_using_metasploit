# Metasploit

Metasploit is a exploitation framework (aka penetration framework) , build for security professional to support penetration testing.

**Most related alternative** <br>
Cobalt strike – closed source/ commercial use only

## Why prefer Metasploit? <br>
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
