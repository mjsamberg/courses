---
layout: page
title: "Introduction"
course: "dlprograms"
unit: 7
---
## Fall 2020 Whitepaper Series
Read: [Cybersecurity in K-12: An Overview of the Threat Landscape][1]

## Introduction
A data breach or a cybersecurity incident is the closest thing a CTO will have to a "3 a.m. phone call". Cybersecurity breaches of any kind can be critically damaging to a CTO, to their school and district, to students and staff and their families, and to public trust. 

In most places, school districts represent the largest and most accessible networks in that locale. That, combined with the trove of personal data available on school systems makes them a very tempting target for hackers. Government IT as a whole is an increasingly popular target for ransomware attackers because of the combination of personal data, the lack of IT resources, and typically lax security practices relative to corporate entities. Most attacks aren't _ransomware_ attacks, where data are encrypted. In many cases, data are stolen or manipulated, and an IT department may never even know. The question is not whether your district will be the target of an attempted cyberattack, it's a question of when. Whether the attack succeeds or not will depend on your plans to identify, contain, mitigate, and remediate the threats caused by these attacks.
  
Attacks are typically one of three things: malicious attacks that are intended to destroy networks or harm property, data theft or data destruction attacks where an attacker attempts to earn money through the sale of stolen data or by a ransom by threatening to release or destroy data, and nuisance attacks designed to disrupt systems but not to cause damage. Schools are targets for all three types of attacks.

Preventing and mitigating cyberattacks is not solely a technical problem. In fact, most attacks are not very sophisticated. Mitigating cyberattacks and data breaches involve a combination of strategic planning, technical tools, physical security, and user education.

Being security-minded (and the content of this chapter) can make you paranoid, and successful cybersecurity practices blend the right amount of paranoia while balancing considerations of user experience. Being too restrictive means that _Shadow IT_ emerges, where users develop systems and structures to use software and tools that are not approved to get around the restrictions put in place. When this happens, the _attack surface_ (the number of potential targets for attack) in your organization increases, and new _attack vectors_ (the different ways an attack can be introduced) are created. 

## Types of Attacks
The following is a list of high-level types of attack vectors that are used. This list is far from exhaustive and attack vectors are often combined in more sophisticated attacks. A thing to remember is that cyberattacks are almost always Federal crimes. In the event of an attack, a CTO should stop the spread of the attack, contain it, and contact authorities before beginning mitigation and cleanup procedures.

### Social Engineering
Social engineering attacks are by far the most common and the easiest to pull off. A social engineering attack is non-technical in nature, and relies on human-to-human connection to create a new attack vector. These take multiple forms, such as searching property tax records or voter registration records online to get enough personal information to convince a customer service agent that you are someone else, or simply holding the door for someone entering a restricted area without verifying identity. Social engineering attacks have been used to convince bank tellers to move money from a savings account into a compromised bank account. In schools, several social engineering attacks have been employed to gain physical access to a building and tap phones or to convince a finance officer to release sensitive information about employees, including W-2 forms. Since these attacks are not technical in nature, the primary prevention method is user education and policy.

### Phishing
A phishing attack is a specific type of social engineering attack where a malicious actor poses as a trusted entity (a service provider or another employee) and convinces the user to take action. Typically this will be an email that asks someone to log in and verify their account. The user will be directed to a fake site that looks like, for example, a Google login. When the user enters their login and password, the site can capture and steal those credentials. Phishing attacks can also convince users to share documents by imitating other users. In some cases, phishers will create false signatures based on website data and generate false emails that appear to be from a supervisor. In some cases schools have initiated wire transfers of funds based on false invoices or shared confidential employee information. While some technical measures exist to intercept phishing emails, user education is the primary defense - teaching users to verify the FROM: address of an email or the URL of a website, and generate new emails to confirm actions that don't seem right instead of replying. 

### Spoofing
A spoofing attack occurs when someone sets up a fake website that appears to be another website for the purpose of collecting user data. This is typically used in conjunction with phishing attacks to convince users they've arrived at their bank's site, for example, and to log in with their credentials. Spoofers will also create websites with domain names that are common misspellings of the intended website for the purpose of stealing user data.

### Data Tampering
Data tampering attacks occur when an attacker gets access to a system and makes changes to data without a user's knowledge or steals data. These attacks are typically not technically sophisticated, occurring through phishing or another way in which credentials are stolen. The attacker can then log in to a system to change data (i.e. change student grades). 

### Technical Debt
Technical debt is a term that encompasses a wide variety of problems in IT management. In short, technical debt is a term defining when configuration on a server or application is done incorrectly "but it works" or when patches and configuration changes aren't deployed because they would be too costly or too time consuming to implement. These unpatched vulnerabilities or misconfigurations create exploitable vectors in servers, on workstations, and in networks that can be used to gain entry to systems and deploy an attack or steal data. Technical debt on servers and server-based applications is another argument for using managed services whenever possible. Attacks can also be mitigated by keeping servers, desktops, and network equipment patched, up-to-date, and properly configured. 

### Viruses and Malware
Malware (including viruses) is software that is installed on a computer to cause harm to the computer, typically by changing the way the computer functions, logging keystrokes to steal data, or causing damage to files on the computer. Malware typically spreads via email (via a phishing attack where a user is tricked into opening an infected file or executable) or through unpatched exploits on computers and networks. Malware can be mitigated by using anti-malware software such as Windows Defender on Windows 10, DetectX on Mac, or Chrome OS's built-in tools. Malware tends not to infect iOS or Android devices because they are locked-down to not allow the execution of non-store code. 

### Ransomware
Ransomware is a form of malware that encrypts files on a computer such that a user cannot access them or read them without a decryption key. The attacker demands a payment, usually in the form of Bitcoin, in order to provide the decryption key and release the files. Ransomware is particularly destructive because it will work across all files that a user has access to, including files on networked drives or on Google Drive if the user is running an app like Google Drive FileStream or Backup and Sync. While many ransomware victims have paid the ransom and gotten their files back, many others have not, and the FBI does not recommend paying the ransom. If the ransom is not paid, the files must be recovered from any backups that exist or recreated.

[Municipal ransomware attacks are incredibly common][2]. Several municipalities in North Carolina have suffered catastrophic attacks in recent years, including [Mecklenburg County][3], [Orange County][4], [Lincoln County][5], and the [city and county of Durham][6]. Schools are not immune to these threats either, and several districts have been subject to ransomware attacks this year including [Burke County Schools][7], [Columbus County Schools][8], [Rockingham County Schools][9], [Haywood County Schools][10], and several others. 

### Denial of Service
A Denial of Service attack is where one computer (or lots of computers, in which case it's called a Distributed Denial of Service attack, or DDoS) generates lots of traffic to a website, network, or server. The purpose of this attack is not to steal data, but to crash the website or overwhelm a network. DoS attacks are hard to prevent, but typically, shutting down the impacted site, waiting for the attack to pass, and then bringing everything back up will mitigate this type of attack. Firewalls can also intelligently handle and adapt to DDoS attacks using a function called "rate limiting", where all requests from an IP address are automatically blocked above a certain threshold. 

[1]:	https://www.fi.ncsu.edu/resources/cybersecurity-in-k-12-an-overview-of-the-threat-landscape/
[2]:	https://statescoop.com/Ransomware-Map/
[3]:	https://www.charlotteobserver.com/news/politics-government/article189428824.html
[4]:	https://statescoop.com/orange-county-n-c-recovering-from-ransomware-attack/
[5]:	https://www.wcnc.com/article/news/crime/ransomware-attack-in-lincoln-county-for-2nd-time/275-4ea0de54-d9dc-4f89-924f-04c870af0e8a
[6]:	https://www.forbes.com/sites/daveywinder/2020/03/10/two-russian-ransomware-attacks-take-down-north-carolina-city-and-county-government-systems/#5a773c2588fa
[7]:	https://www.morganton.com/news/education/bcps-targeted-in-cyber-threat/article_95b3e3d7-e806-501f-be0d-d0e3568af193.html
[8]:	https://www.wwaytv3.com/2019/10/18/virus-disrupts-internet-phone-lines-at-columbus-county-schools/
[9]:	https://thejournal.com/articles/2018/01/12/nc-district-hit-with-malware.aspx
[10]:	https://wlos.com/news/local/haywood-county-schools-closed-after-ransomware-attack