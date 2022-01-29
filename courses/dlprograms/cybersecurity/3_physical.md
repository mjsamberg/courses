---
layout: page
title: "Physical Security"
course: "dlprograms"
unit: 7
---
If I walked in to your school office dressed as the copier repair person, and knew the locations of the copy machines in your building, how far would I get before I was questioned? Would I be able to roam your building freely? Would someone let me use a computer? Would they log out of whatever applications they were using before they did? 

In my first job in IT, my boss used to say "there's no amount of security you can buy that will prevent damage from someone with hands on a computer inside your network."

A malicious actor on premises can inflict all kinds of damage including loading malware onto devices, installing hardware to monitor network traffic or access network systems, adding physical keyloggers to computers, or stealing hardware. A malicious actor may be unauthorized, but in many cases, they may also be students or employees. 

Any actor interfacing with IT systems should be monitored such that their actions on the network should be closely monitored and least privilege access should be enforced (the Target credit card data breach in 2014 was caused by a [bad actor in the HVAC systems][1] who was able to access the Target network through the HVAC system and jump over to install malware on the credit card processing terminals).

The physical security of devices and infrastructure is another critical component of cybersecurity. This includes things like preventing unauthorized people from using computers and accounts which may have extra access (nobody touches my laptop), locking server rooms and network closets, keeping track of which devices are connected to your network and looking for anything out of sorts. In addition, it's reasonable and prudent to treat any computer as if it's potentially compromised (hence the need for privilege separation). 

## Physical Device Security
In addition to protecting devices in the building, with an increasing number of devices, laptops need to be protected from theft as well. Apple devices have a tool called [FileVault][2] and Windows devices have a tool called [BitLocker][3]. These tools encrypt the hard drives on laptops such that they can only be unlocked with the user's password (on Macs) or using a hardware-specific chip (Windows). This prevents a theft where a user steals a laptop and [removes the hard drive to access the data][4] from another computer. The downside to these tools is that data from failed disks can be impossible to recover, since that's the point. This underscores the need for users to either use cloud storage solutions like Google Drive or One Drive, or to have a comprehensive desktop-level backup strategy in place. The strategy isn't to use flash drives - while they're convenient, they are easy to lose or steal which may contribute to a data breach. In addition, moving flash drives from computer to computer is an effective way to spread malware.

In addition, tools like [Find My Mac][5] and Windows [Find My Device][6] can locate and disable devices from being used as soon as they connect to a wifi network. These measures are insufficient, however, without a strong user password on every device that is easy for a user to remember and hard for others to guess. Mac and Windows devices now both also include biometric authentication as a viable alternative.

When a device outlives its usefulness, the device should be [thoroughly wiped][7] before being surplussed. Typically on a computer, when you delete a file, it doesn't remove the file from disk, but simply marks the space as "ok to write over". That means that files can be recovered. Tools like Killdisk and others erase every file from the disk, and then overwrite the entire disk with random data, and may repeat this process up to eight times to ensure that data cannot be recovered from the disk. That, combined with disk encryption set up while the computer is in use, guarantees that no data can be recovered on the disk. 

All devices should be wiped in this way. Most modern copy machines have a hard drive which stores images of recent copies and print jobs. Since lots of confidential data goes through a copier, these disks are good targets for potential theft. Some copiers have a mode for secure copies that should be employed when needed. For all copiers, these disks should be kept physically secure, and should not be allowed to leave your building without a data wipe. 

[1]:	https://krebsonsecurity.com/2014/02/target-hackers-broke-in-via-hvac-company/
[2]:	https://support.apple.com/en-us/HT204837
[3]:	https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption
[4]:	https://www.tweaktown.com/news/39120/stolen-laptop-opens-up-20-000-students-in-south-carolina-to-data-theft/index.html
[5]:	https://support.apple.com/en-us/HT204756
[6]:	https://support.microsoft.com/en-us/help/11579/microsoft-account-find-and-lock-lost-windows-device
[7]:	http://killdisk.com/killdisk-freeware.htm