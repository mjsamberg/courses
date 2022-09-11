---
layout: page
title: "Interoperability"
course: "dlprograms"
unit: 3
---

Once content is selected, CTOs and ITFs need to work to weave all of the content into a coherent ecosystem. We will talk more about infrastructure in Unit 4. However, for content packages, you should be particularly aware of the data needs of an application and will have to work to integrate it. Interoperability between educational software is a relatively new concept, and most packages still rely on text files being passed back and forth to provide data to different apps.

## Authentication
For apps that require logins, there are multiple ways to provision accounts. Some apps still require that accounts are provisioned manually, or via a data extract from your Student Information System (SIS). Some applications can log in via Google/Microsoft in districts with Google Suite for Education accounts or Microsoft Office 365. Other applications support SAML, which is a protocol that allows for secure login via the web (Shibboleth and NCEdCloud are SAML services). Tools like ClassLink and Clever can automate this process as well, replacing application logins with a centralized login interface that is provisioned across applications. 

## Rostering
Beyond creating accounts, students usually need to be placed into classes within the application. Many applications tend to achieve this using a data extract from the SIS, though some applications can connect to the SIS directly. 

The [1EdTech Consortium][1] (formerly known as _IMS Global_) maintains many of the standards discussed on this page. One of them is the [OneRoster protocol][2], which allows applications to be provided roster data and transmit grades back to an authoritative source.  Canvas can be a provider and consumer for OneRoster data, and as an LMS, can roster students in consumer apps based on their Canvas classes and then feed grades back in to Canvas.

## Content Sharing
The [Learning Tools Interoperability (LTI)][3] framework allows activities to be shared between systems so that learning objects can be embedded into learning management systems. For example, the #GoOpenNC platform supports LTI. Therefore, it is possible from within the Canvas or Schoology LMSes to browse the #GoOpenNC platform, select learning objects, and pull them into your course all from within the LMS. LTI also supports more advanced features where if the destination system provides assessment support, the grades can be sent back to the host LMS.

The [1EdTEch Common Cartridge][4] standard is a standardized export format from LMS systems. A Common Cartridge exported from one LMS should be able to be consumed by any other LMS system and displayed with fidelity, provided no features that aren't supported in the 1ET-CC spec are used. Some textbook vendors distribute coursepacks as common cartridges such that a teacher can import a complete course based on a textbook into any LMS. 

[1]:	https://www.imsglobal.org/
[2]:	https://www.imsglobal.org/activity/onerosterlis
[3]:	https://www.imsglobal.org/activity/learning-tools-interoperability
[4]:	https://www.imsglobal.org/cc/index.html