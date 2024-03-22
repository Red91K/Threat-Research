

# research scope & details
audience: general public

## dissemination
- slide deck
- written TA report for defenders
- attack flow on case study / general TTPs
- written case study report
- diamond model?

## intel requirements
### Who is OilRig? 
- General information
- Attribution
- Capabilities
-> Hackers are not all the same; they range in skill, resources, and capability and often go by different names. How would you classify this threat actor? Do they go by any aliases? Where are they from? How would you rate the skill level and resources available to this threat actor? 

- Intent /Motivation
- Geopolitical context
-> Hackers are motivated to act for specific reasons. What are the motivations of your threat actor? What is the specific geo-political context they are operating in and what insight does that give you for why they are operating in this manner? 

### What are OilRig's TTPs?
Hackers utilize specific tradecraft, tactics, and processes to act on their motivations. Describe the range of efforts used by your threat actor to engage in the hacking process. Utilize the Lockheed Martin Kill Chain to help describe those efforts.

Hackers utilize the hacking process to achieve certain “end-effects” on their target. Provide examples or case studies of attacks your threat actor has been involved with over the years and describe their primary, secondary, and second order effects.

### Defensive reccomendations?
Not all hackers represent a strategic problem for policy makers. How would you characterize your threat actor, are they chiefly a private problem for businesses or a public concern for policy makers? How should policy makers respond? 

# sources
-> open-source & TLP:clear information

## malpedia
https://malpedia.caad.fkie.fraunhofer.de/actor/oilrig
-> General information & links to other sources
Reliablility: Reliable, summarizes other sources therefore depends on reliability of cited.
Managed by Fraunhofer Society for the Advancement of Applied Research, a german research institution.

### PIR: Who is Oilrig?
- Attribution: Iranian threat actor !  TODO
- Targeting
	- Primarily targets Middle Eastern organizations, but occasionally orgs outside the middle east
	- Specifically targets organizations chosen for strategic purposes, instead of targets of opportunity
- Capabilities:
	- highly active and organized (! no direct evidence provided)
	- 

### PIR: What are Oilrig's TTPs?
- OilRig has been seen carrying out supply chain attacks
- Leverages unsophisticated initial access techniques: primarily relies on social engineering (T1566), but sometimes...
	-  exploitation of patched vulnerabilities (T1190)
	- using credentials to access public facing services like outlook web access (T1078) 
	- supply chain compromises (T1195)
- Shows sophistication in post-exploitation techniques: 
	- defense evasion: organized evasion testing used the during development of their tools.
	- c2: Use of custom DNS Tunneling protocols for command and control (C2) and data exfiltration. 
	- persistence: Custom web-shells and backdoors used to persistently access servers. 
	- lateral movement: OilRig relies on stolen account credentials for lateral movement. (T1078, 
	- execution: after moving laterally with stolen credentials, OilRig preferrs to use lolbins like 

### PIR: Defensive Reccomendations?


## etda
-> great overview, references other sources to create a comprehensive timeline of attacks and responses
https://apt.etda.or.th/cgi-bin/showcard.cgi?g=OilRig%2C%20APT%2034%2C%20Helix%20Kitten%2C%20Chrysene

## attackiq
https://www.attackiq.com/2022/07/11/oilrig-attack-graphs-emulating-the-iranian-threat-actors-global-campaigns/

## cfr
https://www.cfr.org/cyber-operations/oilrig
https://www.cfr.org/cyber-operations/apt-34

## ESET
https://www.welivesecurity.com/en/eset-research/oilrig-persistent-attacks-cloud-service-powered-downloaders/
2023

## unit 42
2019
https://unit42.paloaltonetworks.com/behind-the-scenes-with-oilrig/

## industrial cybersecurity pulse
2023
https://www.industrialcybersecuritypulse.com/threats-vulnerabilities/throwback-attack-iranian-backed-oilrig-targets-critical-infrastructure-in-the-middle-east/


# Research
## general info
First identified by Symantec in 2012 -- Attack IQ 
Recently clustered / attributed w/ apt34