---
layout: page
title: "E-Rate Program"
course: "dlprograms"
unit: 6
---
Take a look at your most recent cell phone bill or Internet bill. On the bill, you'll notice a "Universal Service Fee". This charge funds the Federal [Universal Service Fund][1]. The USF is a program mandated by the FCC and administered by the [Universal Service Administrative Company][2] (USAC). USF provides application-based funding to offset the cost of network construction and service for the following four categories:
* Offsetting high cost telecommunications installations such as running telephone cables to rural houses or across mountains.
* Providing subsidies for low-income households to access phone and Internet services (the "Lifeline" program, discussed in Unit 4)
* Subsidizing telecommunications services for rural health care providers to provide telemedicine services at a price point similar to urban areas.
* The E-Rate program, providing subsidies for telecommunications services and connectivity for schools and libraries. 

Any public school or district is eligible for participation in the E-Rate program. Private schools may also participate provided they have a not-for-profit status and an endowment of less than $50 million. Unlike most Federal programs, the payments are made to the vendor and not the school itself. Therefore, a recipient of E-Rate funds does not have to comply with Title IX, Section 504, or other laws that apply to schools that receive Federal funds, which increases participation among private schools. CIPA, however, only applies to schools (public or private) that benefit from E-Rate funds. 

There are a *lot* of rules around the E-Rate process, the following is a very high-level overview. At the highest level, E-Rate is a subsidy that pays 20-90% of Internet access charges and internal connectivity charges for an eligible school/district. Eligibility is based on whether the district is in a rural or urban area, and the percentage of students eligible for free and reduced priced meals.

## Eligible Services
Eligible services for E-Rate are divided into two categories. **Category 1** services include Internet and WAN connection services. For many years, web hosting, email, voice, cellular, and paging services were also eligible, but they have since been phased out. Discounts for Category 1 are up to 90% based on eligibility.

**Category 2** services include internal connections such as switches, wireless access points, network controllers, UPS devices and racks for switches, wireless controllers, firewalls, and the software and maintenance plans to support this equipment. Discounts for Category 2 are up to 85%. Each school may receive a minimum of $9,200 or a maximum of $150 per ADM every five years. 2020 is a transition year where E-Rate is switching to the next five-year cycle. 

The full [eligible services list][3], adopted by the FCC and published yearly, defines what can and cannot be considered eligible for funding. Some eligible devices may not be fully eligible. For example, security cameras are ineligible for E-Rate funding. Because of this, the internal connections for security cameras are also ineligible. Therefore, when applying for E-Rate, the cost for that single wire and single port on a switch must be cost-allocated out of your request as an ineligible portion of an otherwise eligible service. This usually only accounts for small fractions of funding, but can cause big problems in an audit.

Only schools that directly serve students are eligible for Category 2 funding. Central offices, for example, are not. In a case where a firewall or core switch is located at a central office, the cost of that equipment must be cost-allocated across all schools on a per-ADM basis. A central office (called a Non-Instructional Facility or NIF in E-Rate world) can be eligible for Category 1 funding. 

## Discounts
The discount for E-Rate is set at the district level. For private and charter schools, they are treated as a school district. The first step is to calculate the percentage of free and reduced lunch-eligible students, which is the number of eligible students divided by the district ADM.

For districts participating in the Community Eligibility Program, the percentage of students directly certified through CEP would be multiplied by 1.6 to determine the E-Rate eligible percentage (capped at 100%). 

For districts that don't participate in the National School Lunch Program, the district can use [several alternative measures][4] to calculate poverty rates. 

Once the poverty percentage is calculated, a district needs to [determine if it's Rural or Urban][5] based on the FCC's  designation. From there, the discount percentages can be calculated:

|Income|Urban Discount (C1)|Rural Discount (C1)|Urban Discount (C2)|Rural Discount (C2)|
|--- |--- |--- |--- |--- |
|\<1%|20%|25%|20%|25%|
|1%-19%|40%|50%|40%|50%|
|20%-34%|50%|60%|50%|60%|
|35%-49%|60%|70%|60%|70%|
|50%-74%|80%|80%|80%|80%|
|75%-100%|90%|90%|85%|85%|
{:.table .table-bordered .table-striped}

## The Process
The [E-Rate process][6] is divided into several, typically referred to by the form numbers:
* The first process (the 470 process) is an RFP process to select services for the coming year (or contract period - for Internet services, districts may award contracts that last multiple years). This process starts with the filing of E-Rate Form 470, and the posting of an RFP in a public way. The RFP must be open for 28 \days, and all vendors must be offered an opportunity to ask questions, tour sites, and any follow-up needed. The responses to these questions but be made available to all potential bidders. The bids must be open and fair such that it doesn't exclude any potential bidders (you cannot say in the RFP that "vendors may only use Cisco switches", but you can say "must be compatible with current infrastructure"). 
* Once bids are received, the school/district must score all entries received against a rubric. Price must be the most heavily weighted factor, but a district may use whichever rubric they want, so long as it's fair and doesn't provide an automatic advantage to any one vendor. A state contract may be considered a bid.
* Once a winner is selected for each service, the school/district must sign a contract with an intent to purchase (the purchase can be dependent on E-Rate funding), will file a Form 471, which is a request for funding. 
* Over the next few months, programs will go through a PIA (Program Integrity Assurance) review. This review makes sure that no E-Rate rules are being violated. A PIA reviewer reviews each application and will respond with questions in writing. A CTO has 14 days to provide a written response, and may receive several follow-ups. If any rules are broken, or more than 30% of the services being requested are ineligible, the request will be denied.
* Eventually, if an application is approved, school/district will be issued a Funding Commitment Decision Letter (FCDL) which outlines how much funding was allocated for the project (all eligible funding or no funding), and work may begin. A Form 500 can be used to modify the original 471 if needed, to reflect reduced pricing or new contract start and end dates based on when the FCDL was received. Once a district starts services, they file a Form 486, indicating that services are in progress and that the school/district is in compliance with CIPA. 
* Once service has begun, the district has two options for payment. The first is Service Provider Invoicing where the service provider will collect funding from USAC directly and the service provider will only bill a school/district for the non-discounted portion of their services. This is useful in cases where the school/district waits to be funded before starting work (usually Category 2 work). The Billed Entity Applicant Reimbursement form (BEAR) is used in cases where the School and District pays the service provider the full amount and USAC will reimburse the school/district based on their discount percentage. This is used in cases such as Internet and WAN services, where the service must be in place, whether it's funded by E-Rate or not.  
* Audits: The e-rate program will conduct random audits for compliance. A reviewer will come in to review the equipment purchased to make sure that it is in the school that it's supposed to be in (equipment purchased for a school must remain in that school for three years), that the equipment is tagged with the year it was purchased and the FCDL number, and that the equipment is only being used for eligible services according to how it was cost allocated. Districts that violate E-Rate rules may be required to return funds and may forfeit further participation in the E-Rate program. Gift rules also apply - a CTO may not accept any gift valued over $20 from a vendor participating in a bid process. 

## Consortia
A district or group of districts may file for E-Rate as a consortium, calculating the discount from across the districts. The state does this and files on behalf of the districts for Internet connectivity, currently through MCNC. 

## School Connectivity
In North Carolina, districts and charters participate in the School Connectivity Program. That means that the non-discounted portion of any C1 charges are returned to the district by the state in PRC073, so that a district can pay their Internet bills. Districts are required to submit copies of their C1 471 forms to DPI so that PRC073 can be funded correctly.

## Support
The E-Rate program is incredibly complex and time-consuming, but provides great benefit for school districts. North Carolina employs three E-Rate support coordinators out of DPI who are responsible for supporting districts in filing for E-Rate. E-Rate consultants, who work on commission, also support districts and private schools in filing for E-Rate and maximizing available benefits. 

## COVID-19 Relief Funding
The FCC allocated additional money during COVID for the [Emergency Connectivity Fund (ECF)](https://www.fcc.gov/emergency-connectivity-fund) to purchase broadband equipment and devices including hotspots and laptops. This represents an additional $158 million of COVID funding, specifically for technology, in North Carolina. 

[1]:	https://www.fcc.gov/general/universal-service-fund
[2]:	https://www.usac.org/
[3]:	https://docs.fcc.gov/public/attachments/DA-21-1602A1.pdf
[4]:	https://www.usac.org/e-rate/applicant-process/applying-for-discounts/alternative-discount-mechanisms/
[5]:	https://sltools.universalservice.org/portal-external/urbanRuralLookup/
[6]:	https://www.usac.org/e-rate/applicant-process/
