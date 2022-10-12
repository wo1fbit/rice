# Table of Content

# Introduction
1. Objective
2. Executive Summary
   2.1 Recommendations
3. Methodologies
    3.1 Information Gathering
    3.2 Service Enumeration
    3.3 Recon
    3.4 Enumeration
    3.5 Houes Cleaning


# 1. Objective
The objective of this assessment is to perform an internal penetration test against the kehackathon.co.ke network.

# 2. Executive Summary
Hexclan was tasked with performing an internal penetration test towards kehackathon.co.ke. An internal penetration test is a dedicated attack against internally connected systems. The focus of this test is to perform attacks, similar to those of a hacker and attempt to infiltrate kehackathon.co.ke network. Hexclan's overall objective was to evaluate the network, identify systems, and exploit flaws while reporting the findings back to kehackathon.

When performing the internal penetration test, there were several alarming vulnerabilities that were identified on kehackathon’s network. When performing the attacks, Hexclan was able to enumerate users, primarily due to outdated patches and poor security configurations.

3.1 Recommendations
Hexclan recommends patching the vulnerabilities identified during the testing to ensure that an attacker cannot exploit these systems in the future. One thing to remember is that these systems require frequent patching and once patched, should remain on a regular patch program to protect additional vulnerabilities that are discovered at a later date.

# 3. Methodologies
# 3.1 Information Gathering

The information gathering portion of a penetration test focuses on identifying the scope of the penetration test. During this penetration test, Hexclan was tasked with exploiting kehackathon.co.ke network. The specific IP address was:

        198.187.29.125

This was gotten after doing a dig query on the domain name kehackathon.co.ke

![dig](images/dig.png)

Hexclan was able to find the location and user information of the server by doing a whois and an ipinfo lookup on the ip gotten from dig. The location could prove crucial to physical penetration testing which is out of scope of the current Penetration testing.

![whois](images/whois.png)

![ipinfo](images/ipinfo.png)

# 3.2 Service Enumeration

An nmap scan showed the running services on the ip address.
![nmap1](images/nmap.png)
![nmap2](images/nmap2.png)
![nmap3](images/nmap3.png)

# 3.3 Reconnaisance

Hexclan started with enumerating port 80, which proved useful in enumerating usernames that could be used for future further attacks.
Looking around, Hexclan found that the site is running Joomla cms version 4.2.3 by appending "/administrator" directory to the base url "kehackathon.co.ke/hackathon".

![joomla](images/joomla.png)

Looking up the cms version accordingt to the scan below by joomscan, hexclan found it is susceptible to sqlinjection attacks which ranks third in owasp 10.

![joomscan](images/joomscan.png)

Joomscan version 4.2.3 sqlinjection.

![sqli](images/sqlinjection.png)
