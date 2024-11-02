---
layout: page
title: "User Education"
course: "dlprograms"
unit: 7
---
All of the technical tools in the world can't protect a user in your district from inadvertently releasing or being manipulated into sharing personal information.  Additionally, users are increasingly accessing school-owned data from personal devices (checking email accounts from their phones, etc.) so security practices can't be limited to software on the machines. Security best practices need to be implemented on all personally-owned devices as well, and schools have a responsibility to verify and enforce these settings. Some settings [can be managed remotely][1], but others require training users to do things on their own.

## Device Security
The simplest way for a user to protect a device is to ensure that it can't be physically compromised. In addition to drive-level encryption, all devices should have a passcode that is required after several minutes of inactivity. For school managed devices, these can be set through your configuration management system (JAMF, ActiveDirectory, ChromeOS Management Console, etc). For personal devices, it is good practice to enable a passcode or fingerprint on your phone or to enable screen timeout on [Mac][2], [Windows][3], and [ChromeOS][4] immediately when a computer goes to sleep or the screen times out. Users should also manually lock computers when they step away. This prevents a computer from being compromised if left unattended.

## Secure Passwords
Because many sites [store passwords insecurely][5], passwords can be compromised in a data breach (and [many people use common passwords that are easy to crack anyway][6]). You can [search your email address on this website][7] and see how many different places have your passwords.  While [passwords are not a great tool for security][8], password security is critical. 

There are [two common strategies for passwords][9]: use passwords that are difficult to guess but easy to remember and use unique passwords across each site.

A few years ago, the webcomic xkcd released a strip called [Password Strength][10], that recommended that instead of the passwords we tend to use, a random four word string is both easy to remember and difficult for a computer to guess. A lot of research has been done on this subject, and it turns out that it's true - a password like _correct horse battery staple_ is much more secure than _Tr0ub4dor&3_ because it avoids common substitutions, is less likely to be written down, and is more difficult for a computer to guess via brute force. This approach is generally recommended, though many sites still require a number or a symbol as well. But a quote or phrase, with a number and symbol mixed in, is a highly secure password.

The second recommendation is to ensure that no two sites use the same password. Every password should be unique to every website, such that if a website is compromised, the damage will be limited to that one website. The password should also be entirely unique, such that a hacker could guess the password to another site based on the one password they know. Obviously, this is incredibly difficult to manage. However, the use of a password manager tool, such as [Bitwarden][11], [1Password][12], or [Dashlane][13] avoids this issue by automatically generating passwords for sites when you sign up, and then storing all of your passwords for you. The passwords are stored in a database and then filled in for you across your devices. These apps are designed with special encryption, such that even if the password and database were stolen, it would be nearly impossible to capture data from them. Using a password manager means that a user would need to remember a small handful of passwords for their computer and password manager, instead of passwords for every website. 

Combining these recommendations, you would have a secure passphrase for your password manager, and nonsense random passwords generated for all sites at the point of use. As the Computerphile video shares, the best option is to use Google/Facebook/Apple or other single-sign-in when you can.

## Two-Factor Authentication
Authentication factors are the different ways that you can identify that a person is who they claim to be. In general, there are three different factors of authentication that are used:

* **Something you know: ** such as a password, PIN number, or challenge question.
* **Something you have: ** such as a cell phone, hardware token, card, etc.
* **Something you are: ** such as a fingerprint or facial scan.

Multifactor authentication is when two or more factors are used (and two-factor authentication in particular are when two factors are used). An ATM card is one example of two-factor authentication: you have something you have (your ATM card) and something you know (your PIN).

{% include youtube.html id="hGRii5f_uSc" ratio="16x9" title="Why You Should Turn On Two Factor Authentication" %}

An important distinction for two-factor authentication is the requirement that **both** factors to be used to gain access. Compare this with your phone, where you have the option of a PIN or a fingerprint/face scan. However, because only one of these are required, we say that the phone offers single-factor authentication with two possible factor options. On accounts that require a password AND a PIN, these accounts have two step, single-factor authentication, since both elements are only relying on something you know.

When two-factor authentication is used, a user will typically log in with a username and password (something you know), and then take some action from your phone (such as enter a code form a text message, acknowledge a push notification, or enter a code from an app like [Google Authenticator][14] or [Authy][15]) or by inserting a hardware token like a [Yubikey][16] (something you have). Many apps support two-factor authentication such as [Google][17], [Microsoft][18], [Amazon][19], [Facebook][20], [Twitter][21], and many [others (full list)][22]. 

Many organizations (such as NC State) are requiring two-factor authentication for all organization-issued accounts. This is an accepted best practice in organizations, but users should be encouraged to use 2FA for all accounts that make them available. 

When a user asks me why they should enable two-factor authentication, I always tell them [the horrifying story of Matt Honan, a Wired magazine reporter who lost all of the data in his Google and iCloud accounts][23] (see his [follow-up as well](https://www.wired.com/2012/08/mat-honan-data-recovery/)), as well as his Apple devices **permanently** because of a hacking. I always share the article and ask people to read it, because it's scary enough to help them realize their accounts are vulnerable. The attack started as a series of social engineering attacks and data lookups in public records. From there, they employed built-in features to take over Honan's accounts, wipe his Google account, all of his computers, and his iCloud account - destroying all of his digital records. As Honan acknowledged in the article, if he had used two-factor authentication on his Amazon, iCloud, Twitter, and Google accounts, all of these issues may have been avoided. Some of the companies involved have new policies to prevent some of the social engineering vectors used.

While text messages are used by many providers for two-factor authentication, I strongly discourage their use - recommending instead that users set up a tool like Google Authenticator or Authy and use a hardware key as a backup. The reason is that text message based authentication is vulnerable to [a social engineering attack known as _simjacking_][24], where a hacker is able to convince a cell phone provider to port your number out to another provider or transfer your service to a new SIM card enabling it to be used in a phone you can't control. The hackers then request a two-factor code be sent to your phone number, which will then be sent to their phone. This is common in the [underground market for influential Instagram accounts][25] and Instagram has added support for app-based two-factor authentication in response. However, many users don't use these services relying on text-based authentication or by only using a single authentication factor.

Even within app-based MFA, there's still a phishing technique with breached passwords where a user is spammed with push notifications until they accept one inadvertently, providing account access to an attacker. Newer MFA apps now employ an additional factor where a user has to match a numebr shown on the login screen with a number in the push notification. 

### Passkeys
While two-factor authentication is the current "gold-standard" for authentication, complex passwords are annoying and two-factor authentication is inconvenient. Apple, Google, Microsoft, in cooperation with the [FIDO Alliance](https://fidoalliance.org) have created a new form of authentication called [PassKeys](https://fidoalliance.org/passkeys/). Passkeys eliminate the need for passwords by using your phone as the authentication source. There are still two factors - something you have (your phone or a physical key) and either something you know (your phone's PIN) or something you are (your phone's TouchID/FaceID). Passkeys are still in their infancy, but [Windows does support it for authentication](https://www.microsoft.com/en-us/security/blog/2021/09/15/the-passwordless-future-is-here-for-your-microsoft-account/) and [Apple has recently added support as well](https://appleinsider.com/inside/ios-16/tips/how-to-use-passkeys-instead-of-passwords-on-ios-16). Passkeys are now the default for new Google accounts instead of passwords and passkey setups are now becoming increasingly common across websites. Passkeys are the most secure method of authenitcation, but unless you're using a password manager, passkeys require your mobile phone to be avialable and you need to ensure they're backed up.

## User Security
User training and education is a critical component to any cybersecurity program. User training is especially important in phishing attacks. In many attacks, the phishing email is the extent of the attack - a user will provide financial information, wire money, etc. and the attack is concluded. In particular, your user education initiatives [should cover the following][26]:
* Spam emails may look legitimate but may not be. There are many [email scams][27] that look legitimate or [use stolen information to convince people that the scammers know something about them][28]. Spam emails should always be ignored and deleted and if a user has questions, they should check the senders address and make contact with that company through a new email (instead of reply) or another channel.
* Phishing emails may also look like legitimate emails asking for verification of account details. Users should check the URL of the website to ensure that it's the legitimate website as well as both the email address that is in **both** the FROM field and the REPLY-TO field (senders may spoof the from field, but want the return email, so they'll use a different reply-to field. Never send a phisher any information, and make contact through another channel (or if they want to be safe, change a password by going to the app directly and not using the email). If they click on a phishing link, two-factor authentication may mitigate or eliminate the threat, but users should change passwords right away.
* Don't change financial information without verifying the legitimacy of the email or the contact. 
* Never click on files or links in an email if you don't trust (and have verified) the sender.
* In the event of a malware attack, the computer should be turned off immediately by holding down the power button until the computer turns off and be submitted to IT for investigation.
* Users should enable two-factor authentication everywhere it's an option and use password managers.
* Data should only be stored in approved storage locations (covered on the next page).

[1]:	https://support.google.com/a/answer/7422256?hl=en
[2]:	https://macpaw.com/how-to/lock-mac-screen
[3]:	https://www.addictivetips.com/windows-tips/automatically-lock-windows-10-system-inactive/
[4]:	https://support.google.com/chromebook/thread/3771150?hl=en
[5]:	https://www.youtube.com/watch?v=8ZtInClXe1Q
[6]:	https://www.youtube.com/watch?v=7U-RbOKanYs
[7]:	https://haveibeenpwned.com
[8]:	https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984
[9]:	https://www.youtube.com/watch?v=7U-RbOKanYs
[10]:	https://xkcd.com/936/
[11]:	https://www.bitwarden.com
[12]:	https://1password.com
[13]:	https://www.dashlane.com
[14]:	https://support.google.com/accounts/answer/1066447?co=GENIE.Platform%3DAndroid&hl=en
[15]:	https://authy.com
[16]:	https://www.yubico.com/products/
[17]:	https://support.google.com/accounts/answer/185839?co=GENIE.Platform%3DDesktop&hl=en
[18]:	https://support.microsoft.com/en-us/help/12408/microsoft-account-how-to-use-two-step-verification
[19]:	https://www.amazon.com/gp/help/customer/display.html?nodeId=202073820
[20]:	https://www.facebook.com/help/148233965247823
[21]:	https://help.twitter.com/en/managing-your-account/two-factor-authentication
[22]:	https://twofactorauth.org
[23]:	https://www.wired.com/2012/08/apple-amazon-mat-honan-hacking/
[24]:	https://www.vice.com/en_uk/article/3kx4ej/sim-jacking-mobile-phone-fraud
[25]:	https://www.vice.com/en_us/article/vbqax3/hackers-sim-swapping-steal-phone-numbers-instagram-bitcoin
[26]:	https://it.nc.gov/resources/online-safety
[27]:	https://www.atg.wa.gov/5-common-e-mail-scams
[28]:	https://www.cnbc.com/2019/06/17/email-sextortion-scams-on-the-rise-says-fbi.html