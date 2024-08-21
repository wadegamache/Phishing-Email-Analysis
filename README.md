# Phishing Email Analysis
## Introduction and Objective

In this project, I use various tools and technologies to analzye some suspicious emails that were sent my way. For anyone looking for a new job, it can be stressful to constantly send your information around the internet. It's important to be aware of what a phishing email is and some of the TTP's (Tactics, Techniques, and Procedures) that threat actors use to take advantage.

Phishing is a type of social engineering attack where malicious actors impersonate legitimate companies or entities to trick recipients into revealing their sensitive information, such as usernames, passwords, credit card information, etc. Threat actors often create a sense of urgency. They use alarming statements and enticing offers to persuade recipients to click a malicious link or download an infected attachment quickly. These emails can be very convincing, often using logos, email templates, and language that mimic a legitimate organization.

There are many tools and resources out there to help analyze emails. I think it's important to use a variety of sources, as they are all designed with a different purpose and the combination of their analytics will provide the best insight. A few of my favorite are:

- [VirusTotal](https://www.virustotal.com/gui/home/upload) (Analyzes URL's, files, IP's with multiple antivirus engines)
- [URLScan.io](https://urlscan.io/) (Detailed info about URL's, including repuation and associated domains)
- [PhishTool](https://www.phishtool.com/) (Analyzes and visualizes phishing emails to identify malicious elements)
- [MXToolbox](https://mxtoolbox.com/) (DNS lookup, blacklist checks, email header analysis)
- [hybrid-analysis.com](https://hybrid-analysis.com/) (Sandboxing, IOC's, file and URL analysis)

## First Email


  
<!--![image](https://github.com/wadegamache/Azure-SOC-Honeynet/assets/171600915/f230e3f4-76a0-4ad5-a895-9a90e096b636)

The architecture of 

- Vir
- Netw
- Virt
- Lo
- Azur
- Azu
- Micr

## Architect
![image](https://github.com/wadegamache/Azure-SOC-Honeynet/assets/171600915/2389228e-054c-4b84-a6ac-5715e5c4df57)

For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

## Attack Maps 
![image](https://github.com/wadegamache/Azure-SOC-Honeynet/assets/171600915/2c87dc78-fd19-4f69-b345-cb940d1b928a)

This map 

![image](https://github.com/wadegamache/Azure-SOC-Honeynet/assets/171600915/65948389-4d70-4153-a3c1-91e0a84ced4d)

This map sho 

![image](https://github.com/wadegamache/Azure-SOC-Honeynet/assets/171600915/b9c75901-b04d-4bb0-bbe1-44b56ae5acb3)

This map sh

## Metrics Before Hardening / Security Control

## Architecture After Hardening / Security Controls
![image](https://github.com/wadegamache/Azure-SOC-Honeynet/assets/171600915/14e53716-1a48-488e-9ad7-0c783c631871)

For the "AFTER"  well as 

## Attack Maps

```All map queries hardening.```

## Metrics

The follo

Start

Stop 

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 0
| Syslog                   | 1
| SecurityAlert            | 0
| SecurityIncident         | 0
| AzureNetworkAnalytics_CL | 0

## Conclusion

After reviewing the logs ingested -->
