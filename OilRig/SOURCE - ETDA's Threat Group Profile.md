# ETDA's Threat Group Profile
-> overview, references other sources to create a  timeline of OilRig's campaigns

Link: [OilRig, APT 34, Helix Kitten, Chrysene - Threat Group Cards: A Threat Actor Encyclopedia](https://apt.etda.or.th/cgi-bin/showcard.cgi?g=OilRig%2C%20APT%2034%2C%20Helix%20Kitten%2C%20Chrysene)

Source Reliability: 
- Verdict: moderately reliable
   - reliable as a **secondary source** given the reputable sources they draw upon & a lack of understandable incentives, as a threat research team under a Thailand governmental agency, to misrepresent information about OilRig
   - but, does not provide citations for many assertions which is especially concerning as a secondary source
- ETDA (Electronic Transactions Development Agency) is a Thailand government agency
- the threat profile is part of a project that aims to create threat profiles for "all [threat actor] groups worldwide"
- Not necessarily famous as a Threat Intelligence producer, but records show they track multiple threat actors & have published a lot of research
- ETDA states that they track threat actors exclusively using OSINT, mainly from the following sources: MISP Threat Actors galaxy, MITRE ATT&CK Groups, Malpedia, AlienVault OTX. 
- ETDA states that they "play a strictly neutral role and everything collected in this portal does in no way signify specific endorsements, placing blame on countries or taking sides."

## PIR: Who is Oilrig?
### General Information
- First seen in 2014 (uncited)
- Aliases
   - OilRig (Palo Alto)
   - APT 34 (FireEye)
   - Helix Kitten (CrowdStrike)
   - Twisted Kitten (CrowdStrike)
   - Crambus (Symantec)
   - Chrysene (Dragos)
   - Cobalt Gypsy (SecureWorks)
   - TA452 (Proofpoint)
   - ITG13 (IBM)
   - EUROPIUM (Microsoft, pre-new naming convention)
   - Hazel Sandstorm (Microsoft)
   - Scarred Manticore (Check Point)
   - Yellow Maero (PWC)
- In 2019, someone (possibly the CIA? - uncited) leaked OilRig's hacking tools on telegram ([Zdnet](https://www.zdnet.com/article/source-code-of-iranian-cyber-espionage-tools-leaked-on-telegram/))

### Attribution
- States "FireEye assesses that the group works on behalf of the Iranian government based on infrastructure details that contain references to Iran, use of Iranian infrastructure, and targeting that aligns with nation-state interests." (uncited)
- Previously tracked under two distinct groups, APT 34 and OilRig, but combined due to additional reporting giving higher confidence about overlap of activity. (uncited)
- Closely related to APT33, DNSpionage, and Hexane (uncited)

### Capabilities

### Motivation & End Objectives
- Primary motivation: Information theft & espionage (! uncited)

### Targeting
- primarily Middle Eastern victims (uncited)

## PIR: What are Oilrig's TTPs?
- carries out supply chain attacks (uncited)
### Timeline of attacks & relevant TTPs
- 2016, [Unit42-  Targeted Attacks against Banks in the Middle East](https://unit42.paloaltonetworks.com/the-oilrig-campaign-attacks-on-saudi-arabian-organizations-deliver-helminth-backdoor/)
   - Unit42 grouped two campaigns against Saudi Arabian financial & technology and defense industries respectably into OilRig
   - OilRig uses Spearphishing attachments (`T1598.002`)--in this campaign a macro-enabled (User Execution, Malicious File - `T1204.002`) Excel spreadsheet that displays decoy content while it installs a backdoor written in powershell(`T1059.001`) & vbscript (`T1059.005`) or just a exe file (`T1059`)
   - the backdoor is a reverse shell that communicates over DNS or HTTP (C2 over Application Protocols`T1071.001`) using a custom protocol (Non standard encoding, `T1132.002`)
   - automatically runs network & system discovery protocls (Account discovery, `T1087`) (Network Service discovery, `T1046`) (System information discovery, `T1082`) (Process discovery, `T1057`)
   - a number of domains were used to host malicious files & receive c2 
   - WHOIS registrant pointing to a Iranian email address & geolocation as well as persian characters in malware samples potentially alludes to a Iranian actor, but "it is important to remember that this data is easily falsified."
- 2016, [Unit42](https://unit42.paloaltonetworks.com/unit42-oilrig-actors-provide-glimpse-development-testing-efforts/) reports that OilRig has been actively testing their lure files against antivirus products 
   - "This testing activity also suggests that the threat group responsible for the OilRig attack campaign have an organized, professional operations model that includes a testing component to the development of their tools."
   - Oilrig followed a "Very structured approach, using a baseline test sample followed by small iterative changes"
   "Testing activities ceases with a very low antivirus detection rate"
   - "Changes made only a few minutes apart and can involve:
Removal or location change of payload
Modified decoy contents and sheet names
Changes to function and variable names
Removal of entire lines of code
Obfuscating strings via concatenation or an alternate encoding (base64 or hexadecimal)
Reordering of functions in the code"


## PIR: Defensive Reccomendations?
