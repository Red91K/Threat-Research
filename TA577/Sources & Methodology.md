# Methodology
- This research was prompted by a [report](https://www.proofpoint.com/us/blog/threat-insight/ta577s-unusual-attack-chain-leads-ntlm-data-theft) published by Proofpoint's Threat Research team, detailing a dramatic shift in TTPs from TA577.
- The prolific nature of TA577 as interest in projections of future Qakbot activity & how Qakbot affiliates would shift their ttps in response to disruption 
   - As Red Canary puts it: *"While the takedown disrupted the Qbot malware, it is important to distinguish Qbot the tool from the adversaries who use it. You can think of the takedown like a government raid that seizes a warring faction’s largest weapons cache; a blow to be sure, but while the adversaries are still at large you can bet they will retool and rearm themselves. Only time will tell what their new weapon of choice will be and how it will be used."*




# analysis
- NTLM theft definitely represents attempt to diversify, also likely after the disruption of their main malware strain--Qakbot
   - TA577 was observed
   - part of continuity of testing a variety of new TTPS- https://exchange.xforce.ibmcloud.com/search/TA577, but a couple notable ones include AiTM phishing kits, embedded links in PDFs, new malware, etc
   - also just the nature of TA577, but shift away from malware delivery could be unique-- maybe in fear of similar disruptions to other malware & c2 frameworks in the future

# Key Takeaways from Sources
## [TA577’s Unusual Attack Chain Leads to NTLM Data Theft  | Proofpoint US](https://www.proofpoint.com/us/blog/threat-insight/ta577s-unusual-attack-chain-leads-ntlm-data-theft)


## [TA577 Targeting Windows NTLM Hashes in Global Campaigns](https://www.hivepro.com/threat-advisory/ta577-targeting-windows-ntlm-hashes-in-global-campaigns/)


## [Qbot Analysis - RedCanary](https://redcanary.com/threat-detection-report/threats/qbot/)
-> explores how Qbot landscape changed, with a focus on its takedown in August 2023 and its impact on the landscape
- TA570 and TA577 are historically two of the most active Qbot malware affiliates.
- Qbot is usually deployed as the initial stage of an adversary’s playbook, with follow-on activity tied to the objectives of the affiliate group deploying it. While Red Canary does not observe a lot of post-Qbot activity, we know various ransomware affiliates have used it as an initial access vector.

#### qbot landscapte
- even before takedown, Qbot activity decreased dramatically, likely due to presence of 

## [X-Force data reveals top spam trends, campaigns and senior superlatives in 2023](https://securityintelligence.com/x-force/spam-trends-campaigns-senior-superlatives-2023/)
- TA577 resumed email phishing campaigns on January 25 after pausing distribution since mid-December 2023.
- The “Most Dangerous Campaigns” category goes to the initial access broker TA577
- TA577 campaigns in 2023 delivered Qakbot until it was disrupted in August, after which they switched to DarkGate, IcedID, and Pikabot. 
- TA577 combines high-volume campaigns with email “thread hijacking”, in which attackers add malicious URLs or attachments to a stolen email to make it appear more legitimate. 
- "The majority of TA577 campaigns since last spring have leveraged malicious URLs or PDFs containing a malicious URL." *This likely represents an attempt to evade detection and increase effectiveness in terms of user execution* 
- Additionally, threat actors like TA577 have continuously shifted techniques to evade detection--like password-protecting pdfs to prevent security solutions scanning embedded urls and data, and also potentially to give off a false sense of security

## [What is old is new: the NTLM Relay attack](https://www.secureauth.com/blog/what-is-old-is-new-again-the-relay-attack/)

## [Global NTLM relay attacks deployed by APT28 | SC Media](https://www.scmagazine.com/brief/global-ntlm-relay-attacks-deployed-by-apt28)


## [TA577 Shifts to PikaBot](https://www.obrela.com/advisory/pikabot-a-new-emerging-threat/)
- TA577 is a **financially-motivated initial access broker**
- Commonly, TA577 sells their access to hands-on ransomware operators like Storm-0506, Storm-0216, and Storm-0826
- TA577 historically distributed the QakBot trojan, but Obrela has observed it now **distributing PikaBot.**
- This reflects a continuity of TA577's continuously-shifting tooling--it has shifted its malware, flipping between SquirrelWaffle, Qakbot, and now Pikabot
- While the group’s geographical origin remains unconfirmed, it targets a wide range of industries and regions
- It has previously exploited n-day vulnerabilities like the Microsoft Support Diagnostic Tool (CVE-2022-30190), ProxyLogon (CVE-2021-26855, CVE-2021-26857, CVE-2021-26858, and CVE-2021-27065), and ProxyShell (CVE-2021-31207, CVE-2021-34473, and CVE-2021-34523) as part of its operations.

- 2 case studies of TA577 intrusions
   - TA577 sent spearphishing messages that *hijaked email threads* by masquerading as replies to previous emails, but from illegitamate email addressses (Spearphishing link &attachment - `T1566.001`, `T1566.002`) (Establish email accounts - `T1585.002`)
   - A password-protected Zip file was attached, which contained an embedded JS file
   - on user execution (`T1204.002` - User execution, file), it used living-off-the-land tools the (cmd.exe & curl - `T1509`) to download & execute malware from a hard-coded domain