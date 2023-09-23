---
layout: page
title: "Other Devices in the Schools"
course: "dlprograms"
unit: 4
---
Beyond computers, Internet connectivity is a part of just about every device that's going to be installed in schools now. 

Many of these devices are powered using Power Over Ethernet (PoE). PoE utilizes a special type of network switch that sends both data and electrical power over the same ethernet cable. Plugging a PoE compatible device, like a phone, into a PoE switch will power the device and communicate between the switch and the phone along a single cable. Switches in network closets should always be equipped with Uninterruptible Power Supplies (UPS). A UPS is a large battery that your network devices are plugged in to which is in turn plugged in to an electrical outlet. UPSes provide redundancy for several hours in the event of a power blip or electrical failure.

As a point of clarification, "cloud hosted" refers to a software-as-a-service model, where the vendor hosts infrastructure to support a system instead of the servers being hosted on premises. 


## District Infrastructure 

### Phones and Intercom Systems
Just about any office phone system you'll purchase for your school now is Voice Over IP (VoIP). VoIP means that the phone connects to a server on the Internet and that server handles internal call routing, voicemail, etc., and in-turn connects to the Public Switched Telephone Network (PSTN) to make and receive calls externally. VoIP servers and the gateway to the PSTN can be located on site or hosted in the cloud. Special adapters can be purchased for fax machines. Schools used to be required to have at least one traditional telephone line on site (also called a "POTS" line, short for "Plain Old Telephone Service") to connect to the fire alarm, burglar alarm, and an elevator call boxes. Most of these systems can now function using VoIP gateways. However, the fire marshals tend to prefer that fire alarms use POTS lines. Local public safety officials may also require a POTS line if your school is used as an emergency shelter. 

Intercom systems can also connect to a phone system by a special adapter and may use traditional telephone wiring. Speakers in newer intercom systems may instead be IP endpoints, allowing the speakers to connect and pull data from the Internet or for announcements to be addressable district-wide. While it was also possible for older intercom systems to be divided into zones so that bells and announcements could be targeted to different wings of the building, IP-based speaker systems can be configured at the classroom level so that bells for lunches can only ring in the classrooms where they're supposed to.

### Security Devices
Security camera systems made nowadays almost exclusively use IP-based cameras. These cameras collect recordings and feed them to a server at the school or district level or in the cloud. Because of the number of cameras in most schools, the bandwidth requirements for cloud-based security camera systems still make them out of reach for most schools.

Many districts are also using the [Aiphone doorbell entry systems][1] which have an IP gateway that allow the video streams to be accessed and the doors unlocked over the Internet. Door proximity readers also typically connect to a central device which in turn connects to the network for access control purposes. 

Most districts tend to use traditional radio-based walkie talkies. However, some companies are releasing radios that work over wi-fi to enable extended range. Other districts are using tools like [Zello][2] to replace traditional radios with cell phones or to bridge radios and cell phones so that users have fewer devices to carry (and tools like Zello can represent a cost savings when used in place of traditional radios).  

### Environmental Monitoring
Most newer buildings and HVAC systems are equipped with sensors that connect over your IP network to allow district facilities staff to monitor conditions throughout the building, configure HVAC schedules and lighting controls, and diagnose issues remotely. Vendors may also be able to access system remotely for troubleshooting purposes. Many cafeteria freezers also have remote monitoring capabilities to alert district staff if a freezer malfunctions. 

### Student Information Systems
All districts have Student Information Systems (SIS) which are responsible for tracking various data elements regarding student performance. Typically, these are located off-site and are cloud hosted. However, data from the SIS can be exported to provide data to populate other applications (rostering services). In North Carolina, the state-issued SIS is [PowerSchool][3]. 

### Financial Systems
Districts also run their own financial, HR, and Payroll systems (collectively known as Enterprise Resource Planning, or ERP systems). Private schools and charter schools may run apps internally or may contract out for these services. In North Carolina, there are two prevalent applications in public schools: SysologistEd by Sysologist (an outgrowth of older mainframe sysetms) and [LINq][4]. These systems are either hosted locally or within the cloud. The [North Carolina School Business Systems Modernization][5] on providing new, more comprehensive ERP tools to school districts. IN 2017, an RFP was undertaken resulting in two options for schools to choose from under this initiative: [Tyler Munis][6] and [Oracle Cloud][7]. 

ERP modernization is one of the most risky ventures any organizaztions can undertake. [Many of these large ERP system implementations fail](https://www.cio.com/article/278677/enterprise-resource-planning-10-famous-erp-disasters-dustups-and-disappointments.html) as the systems they replace are so customized, so comprehensive, and so integral to business process that shifting to a new system is disruptive to the point of chaos. **[There is a reason so many mainframes are still in use](https://arstechnica.com/information-technology/2023/07/the-ibm-mainframe-how-it-runs-and-why-it-survives/)**. 

In North Carolina, several large ERP system implementations have experienced very significant and very disruptive struggles, including the [NCFAST Food Stamp System](https://www.wral.com/story/nc-fast-rollout-continues-amid-myriad-of-challenges/13864953/), the [NC E-Courts System](https://www.wral.com/story/100-million-e-courts-system-in-nc-linked-to-wrongful-arrests-unlawful-detentions/20928885/), and [child welfare systems](https://www.northcarolinahealthnews.org/2019/03/22/computer-glitches-frustrate-county-workers-could-eventually-cost-the-state-millions/). School Business Systems Modernization has been no exception to this - districts moving from 40-plus year old mainframe systems to comprehensive systems has been extremely challenging. Gaston County Schools, the first to go live on the Oracle platform, has had [payroll challenges for more than a year](https://www.wbtv.com/2023/03/21/some-gaston-co-schools-payroll-issues-fixed-others-still-progress-officials-say/). New Hanover County Schools was the first to go live with the Tyler platform, having fewer but very significant challenges as well. 

### Identity and Access Management
Data from your HR system and SIS system can be used to provision access automatically for new students and staff, including account creation and password resets. An IAM system can provide a single-sign-on to a variety of apps so that users can access them with a single username and password that is synced across platforms. This process is done for public schools automatically using the [NC Education Cloud IAM Service][8]. Tools such as [Clever][9] and [ClassLink][10] combine IAM with rostering service to connect with a variety of educational apps.

## Classroom Infrastructure
### Display Systems
Throughout the 2000s, the "in thing" was to have an Interactive Whiteboard in each classroom and to encourage teachers to use it. While many teachers found success with the interactive whiteboard, many others found the work required to create a high-quality interactive whiteboard lesson to not be worth the payoff. Most interactive whiteboards ended up being used as projection surfaces or simply as virtual whiteboards. They were also expensive, with a typical setup in the $5,000 range for a single classroom.

With 80-inch TVs now available for under $1,000, many districts are turning to large TVs in lieu of interactive displays. Using tools such as an [AppleTV][11], [Miracast Adapter][12], [Chromecast][13], [Yealink Wireless Pods](https://www.yealink.com/en/product-detail/roomcast) or [AirParrot][14] and [Reflector][15], it's possible to stream wirelessly from an iPad or Chromebook to the TV in the front of the classroom. For teachers with tablets or tablet-convertable devices, this gives them the option to capture the interactive element of an interactive whiteboard, while maintaining the freedom to move around the classroom or to have different students be able to present their screens. Some districts choose to leave a desktop computer running Reflector hard-wired to the TV so that a teacher can use that computer and have it ready at any time, while others use a device and require teachers to always initiate streaming. With exception of Chromecast, all of these devices support passcodes to prevent students from casting to the screen unnoticed. Some schools may also isolate these devices to the staff-only network, but that does mean students cannot stream to them. TVs can also be used to display output from other devices such as [document cameras][16]. 

### Printing
Printing is a perennial problem for schools. A small, 2,500 student district that I used to work for, averaged about 2 million copies annually. This is about average. As a strategy question, districts need to determine if they're going to put quotas on teacher prints and copies during the year, if students will be able to print at all, and if so, will they be charged for printing.

Printing is a challenge in schools because many print drivers are antiquated and don't work well, because configuring and deploying printers through an MDM solution is often slightly different depending on the type of printer used, and additional restrictions like access codes and logins are often buried in the print screen. Tools like [PaperCut](https://www.papercut.com) has some tools that are purpose designed to help with printing in schools and large corporate envrionemnts (though it should be noted that PaperCut had a [significant security breach in 2023](https://www.bleepingcomputer.com/news/security/new-papercut-critical-bug-exposes-unpatched-servers-to-rce-attacks/) which impacted [dozens of schools](https://duo.com/decipher/ransomware-group-exploits-papercut-flaw-in-education-sector-cyberattacks) including many here in North Carolina. 

One you determine who gets to print, the next question you'll have to answer is the device that you're going to use. Many schools lease high-volume copier/printer/scanner devices and pay a per-page charge for each print instead of purchasing the equipment outright. This has the advantage of reducing up-front and recurring costs (the copier and the toner are provided as a part of the lease), and reduces the support burden on a school (the copier company will fix any issues that arise with the device). The school's responsibility is to supply paper and make sure people can connect to it. A school can usually get away with a small number of these devices strategically placed throughout the school.

Other schools purchase smaller printers that one or more classrooms can share. These are extremely convenient, in that a teacher can print (even in color, potentially) without leaving their classroom and they tend to have fewer breakdowns than large and complicated copy machines. However, because of the convenience, users tend to print more and to waste more paper, driving the TCO of these devices up. Additionally, the cost to print a color page is always more than the cost to print a black and white page, so color laser printers also have a higher TCO than a black and white copier.

That said, the price for printers with advanced features such as double-sided printing have continued to decline (compounded by new options for aftermarket toner and cartridges) while the cost of copier leases has remained relatively stable. A CTO needs to conduct an analysis of current printing needs and be able to run projections in both scenarios to determine which may be a better option for their district. 

[1]:	https://www.aiphone.com/home/products/jp-series-7-touchscreen-video-intercom-with-room-to-room-communication
[2]:	https://zello.com/accessories/radio-gateways/
[3]:	https://www.powerschool.com
[4]:	https://www.linq.com
[5]:	https://www.dpi.nc.gov/districts-schools/district-operations/school-business-systems-modernization
[6]:	https://www.tylertech.com/products/munis
[7]:	https://www.oracle.com/cloud/
[8]:	https://ncedcloud.mcnc.org
[9]:	https://clever.com
[10]:	https://www.classlink.com
[11]:	https://support.apple.com/en-us/HT204289
[12]:	https://www.microsoft.com/accessories/en-us/products/adapters/wireless-display-adapter-2/p3q-00001
[13]:	https://support.google.com/chromebook/answer/3289520?hl=en
[14]:	https://www.airsquirrels.com/airparrot/
[15]:	https://www.airsquirrels.com/reflector
[16]:	https://www.ipevo.com/prods/VZ-R_HDMI_8MP_Camera
