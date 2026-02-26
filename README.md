# My Penetration Testing Journey: Beginner to Mastery

##  The Ethical Commitment
All activities in this repository are conducted in isolated, legally authorized environments for strictly educational purposes. No real-world systems are targeted without explicit written permission.

## Tools & Environment
- Virtualization: [Virtual Box]
- Target VMs: [Metasploitable]
- Attack Platform: [I am testing the new Hexstrike MCP in Kali Linux]

- ## Learning Journey
- Step 1: Building a home lab: I have decided to use Kali Linux and Metasploitable 2 for now
- [ ] Step 2: ... I have chose to use The host only adapter and i will see if I will be able to access metasploitable 2 with kali and hexstrike
- [ ] Step 3: Perfect! I have pinged Metasploitable from kali and have 0% package loss. May the (Ethical) Hacking begin!
- [ ] Step 4: I attempted a nmap scan, however it seems metasploitable was unreachable, so this time i'm not going to use the Host only adapter, we will see how hexstrike will respond.
- [ ] Step 5: Success! After changing the network to NAT network, i have established connection with metasploitable and retained contact with the Hexstrike MCP server. Now running an advanced scan.
- [ ] Step 6: Here are the results: Funny enough, it was able to identify that it was Metasploitable 2, how crazy is that? OS:Linux 2.6 (Ubuntu), Hostname: Metasploitable.localdomain, Open services & Technologies: 21/tcp FTP vsftpd 2.3.4 Critical-backdoor(CVE-2011-2523), 22/tcp SSH OpenSSH 4.7pl Debian High-plaintext credentials, 25/tcp SMTP Postfix smtpd Medium-outdated. 53/tcp DNS ISC Bind 9.4.2 Medium-outdated. 53/tcp DNS ISC Bind 9.4.2 Medium-outdated.80/tcp Http Apache 2.2.8 + Dav/2 High-outdated Apache+ WEbDAV, 139/tcp NetBios Sambo 3.0.20 Critical-MS-17-010/ CVE-2007-2447, 445/tcp My SQI MySQI 5.0.5la High-likely no root password.
- [ ] Step 6: We are going to looking at the first vulnerability: vsftpd 2.3.4. It contains a backdoor triggered by a smiley face :) in the username (Gives a root shell on port 6200) . This backdoor was installed on the VSFTPD download archive, the "Very secure file tranfer protocol daemon" allows secure transfers for Unix systems. Well on the 30 June 2011, this backdoor was introduced on version 2.3.4, it was only removed on July 3rd 2011.
- [ ] Step 7: I am going to use hexstrike to exploit the vsftpd vulnerability and see its results:
