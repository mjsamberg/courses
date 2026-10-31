---
layout: page
title: "Incident Response Planning"
course: "dlprograms"
unit: 7
---
Every page in this unit assumes you're preventing or recovering from an attack. This page is about what happens in between: the plan you need *before* the 3 a.m. phone call happens, not during it.

An Incident Response Plan (IRP) doesn't need to be complicated, but it does need to exist on paper, before you need it. Trying to figure out who to call and what to do while you're also actively containing a breach is how good people make bad decisions under pressure. An incident response plan is a critical part of a school safety infrastructure. In a critical breach, phones, payment systems, student data, bus routes may all be unavailable. These disruptions may close school or make school unsafe so need to be considered. 

Much of this information can be found in the [Friday Institute's Incident  Response Toolkit](https://docs.google.com/document/d/1enRX_P3UUroj3T2677MHafhKn6PuwvoXDKKMPLlhITY/view?tab=t.64mcj4751p87#heading=h.rlbi819ogzjd).

### The Core Team

Your IRP should name specific roles (not just "IT will handle it"):

- **Incident Commander** - usually the CTO, responsible for coordinating the response and making the call on major decisions (do we shut down the network? do we close school?).
- **Legal Counsel** - needs to be looped in immediately, not after you've already decided what to disclose.
- **Communications/PIO** - drafts what goes to staff, parents, and media.
- **Superintendent/Board Liaison** - someone responsible for keeping leadership informed without leadership trying to run the technical response themselves.
- **External Contacts** who can come in and lend support. In NC Public schools, this is always the [NCLGISA Strike Team](https://www.nclgisa.org/page/strike-team).

### The First Hour

Regardless of what caused the incident, the first hour looks similar:

1. **Contain it.** Isolate affected systems from the network. Don't power them off if you can help it - you may need forensic images of live memory. Unplug the network cable instead.
2. **Don't touch more than you have to.** IT staff "cleaning up" a compromised system before it's documented is one of the most common ways evidence gets destroyed.
3. **Call law enforcement.** Cyberattacks are federal crimes. Contact your local Sheriff's Office and then the FBI as needed.
4. **Call your state supports.** In North Carolina, that's the [NCLGISA Strike Team](https://www.nclgisa.org/page/strike-team) and the [Joint Cybersecurity Task Force](https://governor.nc.gov/news/press-releases/2022/03/16/governor-cooper-signs-executive-order-establishing-state-north-carolina-joint-cybersecurity-task).
5. **Loop in legal counsel and cybersecurity insurance before you communicate anything externally.**

### Notification Deadlines

If personal information is involved, you have legal obligations that start running the moment you discover the breach - not when you finish investigating it. North Carolina's [Identity Theft Protection Act (G.S. 75-65)](https://www.ncleg.gov/EnactedLegislation/Statutes/PDF/BySection/Chapter_75/GS_75-65.pdf) requires notice to affected individuals "without unreasonable delay," and if more than 1,000 people are notified at once, you must also notify the Attorney General's Consumer Protection Division and the nationwide credit bureaus. This applies to school districts as public entities, not just businesses. Additional statutes require notification to the Department of Information Technology within [24 hours of confirmation of a breach (G.S. 143B-1379)](https://www.ncleg.gov/EnactedLegislation/Statutes/HTML/BySection/Chapter_143B/GS_143B-1379.html). 

### Document Everything

Whatever you decide during an incident, write down *why* you decided it, and when. If this ever becomes a legal matter - and breaches involving student data often do - the paper trail showing you followed a reasonable, pre-existing plan matters just as much as the technical response itself.

### Practice Before It's Real

The single best thing you can do to prepare is run a **tabletop exercise**: a scripted, facilitated walkthrough of a fake incident with your actual response team, including your superintendent and board chair - not just IT staff. A good tabletop puts people in the room with a scenario ("it's 7am Monday and your SIS is encrypted with a ransom note") and forces them to work through decisions out loud: who talks to the press, when do we tell parents, do we cancel school, who has the authority to say yes to any of this. The value isn't in getting the "right" answer - it's in discovering the gaps in your plan while nothing is actually on fire.

The single best thing you can do to prepare is run a **tabletop exercise**: a scripted, facilitated walkthrough of a fake incident with your actual response team, including your superintendent and board chair. The FI's cybersecurity toolkit has sample tabletops.

A few things that make a tabletop worth doing instead of just checking a box:
- **Invite the people who will actually be in the room during a real incident** - your superintendent, your PIO, your finance officer, not just technical staff.
- **Use a facilitator who isn't also the Incident Commander**, so the person running the exercise can watch for gaps instead of also playing a role in the scenario.
- **Write down what broke.** The whole point is finding the weak links in your plan - a tabletop that ends with "that went great, no changes needed" probably wasn't hard enough.

### Cyber Liability Insurance

Most districts carry cyber liability insurance, but a lot of CTOs don't actually read their policy until they need it - which is exactly the wrong time to discover what isn't covered. A typical policy can help pay for breach notification and credit monitoring, legal counsel, forensic investigation, a PR firm if the incident goes public, and sometimes business interruption costs if an attack takes your systems down for an extended period. Some policies include ransom payment coverage, though [North Carolina public entities are legally prohibited from paying a ransom](https://www.ncleg.gov/EnactedLegislation/Statutes/PDF/BySection/Chapter_143/GS_143-800.pdf) regardless of what the policy allows, so that particular line item doesn't apply to you.

Here's the part that matters most for a CTO specifically: **the application itself is a cybersecurity audit, and it isn't optional.** Carriers now routinely require documented proof - not just a yes/no answer - of [MFA across all staff and administrative accounts, EDR on managed devices, tested and isolated backups, and a written incident response plan](https://www.k12dive.com/news/k-12-cyber-insurance-costs-rising-ransomware/729011/) before they'll issue or renew a policy. Premiums have risen sharply across the sector in the last few years, and in several well-known cases, districts have had policies denied or even voided retroactively after a breach revealed that a control described on the application (MFA, usually) wasn't actually in place the way the district claimed. In other words: don't guess on the questionnaire. If you don't have a control in place, say so, fix it, and get it right at the next renewal - an honest gap is fixable, but a claim denial after a real breach is not.

A few practical notes:
- **Read the fine print on business email compromise/wire fraud coverage specifically.** Many policies cover this at a lower sublimit than the main policy, and coverage is often contingent on having a documented verification procedure (a callback to a known number before changing any payment information) - if you skip that step, you may find the fraud itself isn't covered even though you have a cyber policy.
- **Your insurer may require you to use their approved incident response and forensics vendors.** Find this out before an incident, not during one - this should be one of the contacts on your IRP team list above.
- **Renewal is an annual forcing function.** Treat the questionnaire as a free audit of where your security posture actually stands, and use it to make the budget case to your board for the controls insurers (and increasingly, DPI) expect you to have.