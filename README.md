# Phishing Email Analysis
## Introduction and Objective

In this project, I used various tools and technologies to analzye some suspicious emails. In this world of continual data growth and collection, it can be challenging to secure one's personal information. It's important to be aware of what a phishing email is and some of the TTP's (Tactics, Techniques, and Procedures) that threat actors use to take advantage of this public knowledge.

Phishing is a type of social engineering where malicious actors impersonate legitimate companies or entities to trick recipients into revealing their sensitive information, such as usernames, passwords, credit card information. Threat actors often create a sense of urgency, using alarming statements and enticing offers to persuade recipients to click a malicious link or download an infected attachment. These emails can be very convincing, often using logos, email templates, and language that mimic a legitimate organization.

There are many tools and resources out there to help analyze emails. I think it's important to use a variety of sources because each are designed with a different purpose. The combination of analytics will provide the best insight and scope. A few of my favorite are:

- [VirusTotal](https://www.virustotal.com/gui/home/upload) (Analyzes URL's, files, IP's with multiple antivirus engines)
- [URLScan.io](https://urlscan.io/) (Detailed info about URL's, including repuation and associated domains)
- [PhishTool](https://www.phishtool.com/) (Analyzes and visualizes phishing emails to identify malicious elements)
- [MXToolbox](https://mxtoolbox.com/) (DNS lookup, blacklist checks, email header analysis)
- [hybrid-analysis.com](https://hybrid-analysis.com/) (Sandboxing, IOC's, file and URL analysis)

## "Amazon" Email

![image](https://github.com/user-attachments/assets/561decd6-412d-4e1d-ad1a-7cf4408d1a10)


This email appears to be from "amazon" at first glance because of the familiar logo. The subject line is labeled "Action Required: Billing Information Issues..." to create a sense of urgency and rush the recipient. Closer inspection of the senders email shows that it was from "info@simplecrew,com" with the email "no-reply@sys,amz,com" above, similar to a legit amazon email domain. If you hover the mouse over the "no-reply@sys,amz,com" it redirects you back to the "simplecrew" domain. A quick google search of "sys,amz,com email domain" brings up blogs and posts about email scamming. The first clue that this email is not legit.

![image](https://github.com/user-attachments/assets/6cfe0bfc-f969-481d-b2f2-3c18ac66ecd7)

Scrolling down we can see that the wording in the email continues to create urgency and panic, giving the recipient only 72 hours before all orders are cancelled. It prompts you to upload a document including your name, address, payment type, and relevant transaction information. They also included a link which says "Account Verify". They named it so to create a sense of trust or security. If you hover over the link with your mouse (careful not to click on it) you see where the link actually takes you, in this case a google site. This is another clue becuase a link to verify an Amazon account should take you to an Amazon site, not Google.

At this point I am already suspicious, but I want to dive in and investigate further. My next step is to look at the raw email message for more detail and clues to potential malicious activity. To do this, click on the three dots at the top right corner of the email. 

![image](https://github.com/user-attachments/assets/a8c5d591-31bb-4328-9db1-39bd1b970caa)

The raw message gives us the whole context of the email with nothing filtered or hidden. This includes verification checks like DKIM, SPF and DMARC to verify authenticity and detect spoffed addresses. The first thing I look for in the raw messege is the "Return-Path". This is where the email actually came from. If "Return-Path" differs from the "From:" section we saw earlier then it is most likely a malicious email. In this case the Return-Path is ".....@minidogworld,net" and not "info@simplecrew,com", like the email read originally. We can conclude that the email is hiding it's true intentions and can not be trusted. 

Other details to look at include the authenticity checks, DKIM (DomainKeys Identified Mail), SPF (Sender Policy Framework), and DMARC (Domain-based Message Authentication, Reporting & Conformance). We can see these checks came back as "dkim = unknown", "spf = none" and "dmarc = fail". Failing all three is highly suspicious. To further analyze the email we can use a site called [PhishTool](https://www.phishtool.com/). PhishTool can accept .eml, .msg or .txt message formats, so I copied the email (in the raw message) and pasted it into a text file. That text file can be uploaded and analyzed.

![image](https://github.com/user-attachments/assets/1e951028-3d95-412a-9a61-3c16054a7de5)

![image](https://github.com/user-attachments/assets/8c30b295-fd89-4a32-97f6-69c649da339d)

The analysis from PhishTool confirmed what we saw in the raw email with regards to the failed authenticity checks and the From/Return-Path discrepancy. I always recommend at least two sources for analysis. Another great site is [VirusTotal](https://www.virustotal.com/gui/home/upload). VirusTotal can analyze suspicious files, domains, IP's and URLs to detect malware and other breaches. It automatically shares this information with the security community and provides great insight for correlation and behavior analytics.

![image](https://github.com/user-attachments/assets/4fd5abca-8ad3-4cc4-862c-cba8ff851503)

VirusTotal uses multiple antivirus engines, scanners and sandboxes to provide a wide scope of behavioral indicators and threat intelligence. 
In this first image we see that no malware was detected, but a few other things grab our attention. The site detected 16 MITRE Signatures, 1 Sigma Rule, 8 dropped files and 9 network communications. 

The MITRE ATT&CK (Adversary Tactics, Techniques and Common Knowledge) framework is a knowledge base for modeling, detecting, preventing and fighting cybersecurity threats based on known adversarial behaviors. The 16 MITRE Signatures found are some of the tactics threat actors use to execute their goals. Each one can be investigated further to determine exactly what the file is trying to do. We can also investigate any dropped or written files, and any attempted network communications.

![image](https://github.com/user-attachments/assets/0e0841b6-c5e4-46bf-a0ba-e33d9c052b8c)

VirusTotal also detected 1 Sigma Rule. A Sigma Rule is an open-source, generic signature format used in cybersecurity. It allows for the creation and sharing of detection methods across SIEM systems. In this case, it found that an "Office Application Initiated Network Connection To Non-Local IP". The summary goes on to provide the CVE number of a similar exploit to research. 

This image also shows some network communication details, including DNS resolutions and IP traffic. These connections and domains can be investigated individually if attestation is required.

## Conclusion
 I concluded that this email was phishing and most likely malicious. I reported it to Amazon through their "stop-spoofing" email address. This allows them to see similar attacks quicker and get ahead of them. Cybercriminal TTP's (Tactics, Techniques, and Procedures) are extremely important to understand how something or someone may be exploited. Many of these TTP's can serve as early warning signs to detect fraud. It's okay to be suspicious, especially when it comes to your data.
