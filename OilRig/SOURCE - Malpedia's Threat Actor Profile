
# Malpedia - OilRig Threat Actor Profile

[OilRig (Threat Actor)](https://malpedia.caad.fkie.fraunhofer.de/actor/oilrig)
- Summary source containing a high-level overview of OilRig and links to other sources

## Source Reliability: 
- Malpedia seems to be a pretty well repudiated source, managed by Fraunhofer Society for the Advancement of Applied Research
- It is a **secondary source**, but it features extensive citations from reliable sources. 

## Executive Summary
Malpedia asserts that OilRig is a highly active and organized threat actor that was attributed to the Iranian government by FireEye in 2014. OilRig primarily targets Middle Eastern organizations  in various industries using social engineering attacks. However, OilRig has also been seen using n-day vulnerabilities, supply chain attacks, and leaked credentials to gain initial access to organizations. Once OilRig gains access, they aim to evade defenses, move laterally, and gain persistance using various sophisticated techniques like conducting evasion testing of tools, using custom DNS-based c2 frameworks (`T1071.004`), custom webshells to persist on servers (`T1505`), and lateral movement with dumped credentials (`TA0006`, `T1078`). 


## PIR: Who is Oilrig?
- **Attribution**: 
	- FireEye attributed OilRig to the Iranian government in 2014, based on their use of infrastructure tied to Iranian operations as well as timing and alignment with the national interests of Iran.
- **Targeting**
	- Primarily targets Middle Eastern organizations, but occasionally orgs outside the middle east
	- Specifically targets organizations chosen for strategic purposes, instead of targets of opportunity. (! no direct evidence provided, but aligns with other sources)
- **Capabilities**:
	- highly active and organized (! no direct evidence provided)

## PIR: What are Oilrig's TTPs?
- OilRig has been seen carrying out supply chain attacks
- Leverages unsophisticated initial access techniques: primarily relies on social engineering (T1566), but sometimes...
	-  exploitation of patched vulnerabilities (T1190)
	- using credentials to access public facing services like outlook web access (T1078) 
	- supply chain compromises (T1195)
- Shows sophistication in post-exploitation techniques: 
	- defense evasion: organized evasion testing used the during development of their tools
	- c2: Use of custom DNS Tunneling protocols for command and control (C2) and data exfiltration. (T1071.004)
	- persistence: Custom web-shells and backdoors used to persistently access servers. (T1505)
	- lateral movement: OilRig relies on stolen account credentials for lateral movement. (T1078)

## PIR: Defensive Reccomendations?
- No specific defensive recommendations provided, but insights into specific TTPs are a good resource for coming up with possible defenses--ex: focusing on detection & prevention of credential dumping would be a strong defense against the seemingly credential-reliant OilRig
