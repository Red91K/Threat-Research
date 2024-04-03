

# research scope & details
audience: 
1. Policymakers & Business Executives
2. Defenders

## dissemination
- slide deck for policymakers / buisness executives
- written TA report for defenders
- report on a specific campaign for defenders, mapping TTPs to 
	- attack flow
	- attack matrix
	- diamond model
	- kill chain

## intel requirements
### Who is OilRig? 
- General information, Attribution, Capabilities
> Hackers are not all the same; they range in skill, resources, and capability and often go by different names. How would you classify this threat actor? Do they go by any aliases? Where are they from? How would you rate the skill level and resources available to this threat actor? 

- Motivation, Targeting, Geopolitical context
> Hackers are motivated to act for specific reasons. What are the motivations of your threat actor? What is the specific geo-political context they are operating in and what insight does that give you for why they are operating in this manner?

### What are OilRig's TTPs?
> Hackers utilize specific tradecraft, tactics, and processes to act on their motivations. Describe the range of efforts used by your threat actor to engage in the hacking process. Utilize the Lockheed Martin Kill Chain to help describe those efforts.
> Hackers utilize the hacking process to achieve certain “end-effects” on their target. Provide examples or case studies of attacks your threat actor has been involved with over the years and describe their primary, secondary, and second order effects.

### Defensive reccomendations?
> Not all hackers represent a strategic problem for policy makers. How would you characterize your threat actor, are they chiefly a private problem for businesses or a public concern for policy makers? How should policy makers respond? 

# sources
-> compilation of TLP:clear sources, each covering a spefic Intelligence Requirement / visibility

## Malpedia - OilRig Threat Actor Profile
[OilRig (Threat Actor)](https://malpedia.caad.fkie.fraunhofer.de/actor/oilrig)
#### Source Reliability: 
- Malpedia seems to be a pretty well repudiated source, managed by Fraunhofer Society for the Advancement of Applied Research
- It is a **secondary source**, but it features extensive citations from reliable sources. When referencing information from this source, cite the primarily source that is cited.

#### Executive Summary
- Malpedia asserts that OilRig is a highly active and organized threat actor that was attributed to the Iranian government by FireEye in 2014. 
- OilRig primarily targets Middle Eastern organizations in various industries using social engineering attacks. 
- However, OilRig has also used n-day vulnerabilities, supply chain attacks, and leaked credentials to gain initial access to organizations. 
- Once OilRig gains access, they aim to evade defenses, move laterally, and gain persistance using various sophisticated techniques like conducting evasion testing of tools, using custom DNS-based c2 frameworks (`T1071.004`), custom webshells to persist on servers (`T1505`), and lateral movement with dumped credentials (`TA0006`, `T1078`). 

## etda
-> great overview, references other sources to create a comprehensive timeline of attacks and responses
[OilRig, APT 34, Helix Kitten, Chrysene - Threat Group Cards: A Threat Actor Encyclopedia](https://apt.etda.or.th/cgi-bin/showcard.cgi?g=OilRig%2C%20APT%2034%2C%20Helix%20Kitten%2C%20Chrysene)

Source Reliability: 
- ETDA (Electronic Transactions Development Agency) is a Thailand government agency
- Not necessarily famous as a Threat Intelligence producer, but records show they track 
- ETDA states that they track threat actors exclusively using OSINT, mainly from the following sources: MISP Threat Actors galaxy, MITRE ATT&CK Groups, Malpedia, AlienVault OTX. 


## cfr
[OilRig | CFR Interactives](https://www.cfr.org/cyber-operations/oilrig)

[APT 34 | CFR Interactives](https://www.cfr.org/cyber-operations/apt-34)


## unit 42
[Behind the Scenes with OilRig](https://unit42.paloaltonetworks.com/behind-the-scenes-with-oilrig/)

2019, Highly comprehensive overview

## ESET
[OilRig’s persistent attacks using cloud service-powered downloaders](https://www.welivesecurity.com/en/eset-research/oilrig-persistent-attacks-cloud-service-powered-downloaders/)

2023, Specific case study of an OilRig campaign

## Trend Micro
[APT34 Deploys Phishing Attack With New Malware](https://www.trendmicro.com/en_th/research/23/i/apt34-deploys-phishing-attack-with-new-malware.html)

2023, Specific case study

## Symantec
[Crambus: New Campaign Targets Middle Eastern Government | Symantec Enterprise Blogs](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/crambus-middle-east-government)

2023, Specific case study

## Fortinet
[Please Confirm You Received Our APT | FortiGuard Labs ](https://www.fortinet.com/blog/threat-research/please-confirm-you-received-our-apt)

2022, Specific Case Study

## MITRE
[OilRig, COBALT GYPSY, IRN2, APT34, Helix Kitten, Evasive Serpens, Group G0049 | MITRE ATT&CK&reg;](https://attack.mitre.org/groups/G0049/)

Updated 2023, but contains sources from as early as 2017
mapping to MITRE ATT&CK based on reputable secondary sources

## attackiq
Opportunities for detection
[ATTACKIQ - Emulating OilRig](https://www.attackiq.com/2022/07/11/oilrig-attack-graphs-emulating-the-iranian-threat-actors-global-campaigns/)

# Overall
## PIR: Who is Oilrig?
### General Information
### Attribution
- FireEye attributed OilRig to the Iranian government in 2014, based on their use of infrastructure tied to Iranian operations as well as timing and alignment with the national interests of Iran. (MALPEDIA)

### Capabilities
- highly active and organized (MALPEDIA)
- 

### Motivation & End Objectives

### Targeting
- Primarily targets Middle Eastern organizations, but occasionally orgs outside the middle east. (MALPEDIA)
- Specifically targets organizations chosen for strategic purposes, instead of targets of opportunity. (MALPEDIA)

## PIR: What are Oilrig's TTPs?
### Reconnaissance

### Weaponaization
-  organized evasion testing used the during development of their tools (MALPEDIA, but also get info from unit42 virustotal development lifecycle)

### Delivery
- MALPEDIA - primarily phishing (`T1566`), but also
	- exploitation of patched vulnerabilities (`T1190`)
	- using credentials to access public facing services like outlook web access (`T1078`) 
	- supply chain compromises (`T1195`)

### Exploitation

### Installation
- Custom web-shells and backdoors used to persistently access servers. (`T1505`)

### C2
- Use of custom DNS Tunneling protocols for command and control (C2) and data exfiltration. (`T1071.004`) (MALPEDIA)

### Actions on Objective
- OilRig will restart the kill chain once gaining access, using stolen account credentials for lateral movement. (`T1078`) (MALPEDIA)

## PIR: Defensive Reccomendations?
