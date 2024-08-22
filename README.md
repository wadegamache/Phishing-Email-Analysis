# Phishing Email Analysis
## Introduction and Objective

In this project, I used various tools and technologies to analzye some suspicious emails that were sent my way. In this world of continual data growth and collection, it can be challenging to secure one's personal information. It's important to be aware of what a phishing email is and some of the TTP's (Tactics, Techniques, and Procedures) that threat actors use to take advantage of this public knowledge.

Phishing is a type of social engineering attack where malicious actors impersonate legitimate companies or entities to trick recipients into revealing their sensitive information, such as usernames, passwords, credit card information, etc. Threat actors often create a sense of urgency, using alarming statements and enticing offers to persuade recipients to click a malicious link or download an infected attachment. These emails can be very convincing, often using logos, email templates, and language that mimic a legitimate organization.

There are many tools and resources out there to help analyze emails. I think it's important to use a variety of sources, as they are each designed with a different purpose. The combination of analytics will provide the best insight and scope. A few of my favorite are:

- [VirusTotal](https://www.virustotal.com/gui/home/upload) (Analyzes URL's, files, IP's with multiple antivirus engines)
- [URLScan.io](https://urlscan.io/) (Detailed info about URL's, including repuation and associated domains)
- [PhishTool](https://www.phishtool.com/) (Analyzes and visualizes phishing emails to identify malicious elements)
- [MXToolbox](https://mxtoolbox.com/) (DNS lookup, blacklist checks, email header analysis)
- [hybrid-analysis.com](https://hybrid-analysis.com/) (Sandboxing, IOC's, file and URL analysis)

## First Email

The first email appears to be from "amazon" at first glance because of the familiar logo. The subject line is labeled "Action Required: Billing Information Issues..." to create a sense of urgency and rush the recipient. Closer inspection of the senders email shows that it was from "info@simplecrew.com" with the email "no-reply@sys.amz.com" above, similar to a legit amazon email domain. If you hover the mouse over the "no-reply@sys.amz.com" it redirects you back to the "simplecrew" domain. A quick google search of "sys.amz.com" brings up blogs and posts about email scamming. The first clue that this email is not legit.

Scrolling down we can see that the wording in the email continues to create urgency and panic, giving the recipient only 72 hours before all orders are cancelled. It prompts you to upload a document including your name, address, payment type, and relevant transaction information. They also included a link which says "Account Verify". They named it so to create a sense of trust or security. If you hover over the link with your mouse (careful not to click on it) you see where the link actually takes you, in this case a google site. This is another clue becuase a link to verify an Amazon account should take you to an Amazon site, not Google.

At this point I am already suspicious, but I want to dive in and investigate further. My next step is to look at the raw email message for more detail and clues to potential malicious activity. To do this, click on the three dots at the top right corner of the email. The raw messege gives us the whole context of the email with nothing filtered or hidden. This includes verification checks like DKIM, SPF and DMARC to verify authenticity and detect spoffed addresses. The first thing I look for in the raw messege is the "Return-Path". This is where the email actually came from. If "Return-Path" differs from the "From:" section we saw earlier then it is most likely a malicious email. 

  
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
