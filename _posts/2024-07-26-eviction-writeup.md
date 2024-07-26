---
title : "TryHackMe - Eviction Writeup"
categories: [Writeups]
tags: [Challenges,Cyber Threat Intelligence, TryHackMe]
---


## Context of the Challenge : 

Sunny is a SOC analyst at E-corp, which manufactures rare earth metals for government and non-government clients. She receives a classified intelligence report that informs her that an APT group (APT28) might be trying to attack organizations similar to E-corp. To act on this intelligence, she must use the MITRE ATT&CK Navigator to identify the TTPs used by the APT group, to ensure it has not already intruded into the network, and to stop it if it has.


A snapshot of the analysis of APT28 techniques following MITRE ATT&CK Framework:
![Pasted image 20240726204014.png](/assets/img/Pasted%20image%2020240726204014.png)


### Who is APT28 ?

Per [ATT&CK MITRE](https://attack.mitre.org/groups/G0007/) , *APT28 is a threat group that has been attributed to Russia's General Staff Main Intelligence Directorate (GRU) 85th Main Special Service Center (GTsSS) military unit 26165, it reportedly compromised the Hillary Clinton campaign, the Democratic National Committee, and the Democratic Congressional Campaign Committee in 2016 in an attempt to interfere with the U.S. presidential election* to name few of it's operations.

In a normal time, a study of the techniques used by those APTs is related to the technology being promoted in the suspect country (AKA Russia in that case), and in the country subject of attack, in addition to the current events happening on the geopolitical landscape.



## Writeup :


> Before starting, note that under each Category in the framework, you would find techniques, which are general things that denotes the APT approach in his campaign, and sub-techniques, which are the actual instances of using the general technique.
For example : an APT may evade defences (category) by removing the Indicators (technique), which was shown to be used in removing Windows Logs (sub-technique) 
{: .prompt-info }



> In real time Investigations, reading the reports assigned to each techniques is very useful, as it may offer clues to indeitfy the mode of operation and compare to the actual incident. 
{: .prompt-info }


Q1 : What is a technique used by the APT to both perform recon and gain initial access?

Answer : Spearphishing link

While looking for about the answer, we can see that spearphishing has been mentioned twice in the Reconnaissance phase, and in the Initial access phase.


Reconnaissance :

![Reconnaissance](/assets/img/Pasted%20image%2020240726200812.png)

Initial Access : 

![Pasted image 20240726200934.png](/assets/img/Pasted%20image%2020240726200934.png)

---

Q2 : Sunny identified that the APT might have moved forward from the recon phase. Which accounts might the APT compromise while developing resources?

Answer : Email accounts

We are asked to look for accounts within the Resource Development, and the one technique to look for is the "Compromise Accounts". We find  there Email Accounts has been used to by this APT.

![Pasted image 20240726201426.png](/assets/img/Pasted%20image%2020240726201426.png)

----

Q3 : E-corp has found that the APT might have gained initial access using social engineering to make the user execute code for the threat actor. Sunny wants to identify if the APT was also successful in execution. What two techniques of user execution should Sunny look out for? (Answer format: <technique 1> and <technique 2>)

Answer : Malicious file and malicious link

Using social engineering infers that we have to look for something that is related with "users", where the attacker will not be the direct source of execution, and this is described with User Execution technique, as sub-techniques, it is reported that APT28 used Malicious files and links as means of execution upon user interaction. 


![Pasted image 20240726201938.png](/assets/img/Pasted%20image%2020240726201938.png)

----

Q4 : If the above technique was successful, which scripting interpreters should Sunny search for to identify successful execution? (Answer format: <technique 1> and <technique 2>)

Answer : Powershell and Windows Command shell

Always within the execution phase, APT28 is reported to use PowerShell and Windows Command Shell as means scripting interpreters to attack, which is quiet logical, as hiding a malicious PowerShell script as an innocent executable or embedded with any file isn't uncommon.


![Pasted image 20240726210822.png](/assets/img/Pasted%20image%2020240726210822.png)


----

Q5 : While looking at the scripting interpreters identified in Q4, Sunny found some obfuscated scripts that changed the registry. Assuming these changes are for maintaining persistence, which registry keys should Sunny observe to track these changes?

Answer : Registry run keys

The first thing (Usually) that an attacker want to do immediately after having a foothold on a system is to maintain it, so it is a plausible supposition to say that the obfuscated script is used for Persistence.
And one thing that maintain a good persistence are Startup folders (that can be found within HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run for example).

Fortunately, it has been reported that APT28 used Registry Run keys for Persistence

![Pasted image 20240726210859.png](/assets/img/Pasted%20image%2020240726210859.png)

----

Q6 : Sunny identified that the APT executes system binaries to evade defences. Which system binary's execution should Sunny scrutinize for proxy execution?

Answer : Rundll32


We are tasked to find a system binary that is reported to be is used to evade defences. Obviously, we would look after it in the sub-techniques fields, because we are looking for a specific name.
We will find Rundll32, which is a a process that loads and runs 32-bit dynamic-link libraries (DLLs). (Per [Microsoft](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/rundll32)), and impossible to stop without breaking things (Per [Red Canary](https://redcanary.com/threat-detection-report/techniques/rundll32/#:~:text=Like%20other%20prevalent%20ATT%26CK%20techniques,or%20disabled%20without%20breaking%20things.)) making it a solid candidate to use as a decoy.


![Pasted image 20240726203015.png](/assets/img/Pasted%20image%2020240726203015.png)

----

Q7 : Sunny identified tcpdump on one of the compromised hosts. Assuming this was placed there by the threat actor, which technique might the APT be using here for discovery?

Answer : Network sniffing 


Tcpdump is a networking utility that that allows you to capture and analyse network traffic (notably TCP/IP) going through your system (more details in [this article](https://opensource.com/article/18/10/introduction-tcpdump)), so it is obvious that the first keyword to search about is networking.
we quickly find that network sniffing (which tcpdump can be used for) is a technique that APT28 used already.


![Pasted image 20240726203315.png](/assets/img/Pasted%20image%2020240726203315.png)

---

Q8 : It looks like the APT achieved lateral movement by exploiting remote services. Which remote services should Sunny observe to identify APT activity traces?

Answer : SMB/Windows Admin shares.

Using Remote Service is a technique that can be used for Lateral Movement, when consulting it, we find that APT28 is reported to use SMB/Windows Admin shares, because it is enabled by default to allow remote management of hosts via internal networking (more details in [this article](https://redcanary.com/threat-detection-report/techniques/windows-admin-shares/))

![Pasted image 20240726203503.png](/assets/img/Pasted%20image%2020240726203503.png)

---

Q9 : It looked like the primary goal of the APT was to steal intellectual property from E-corp's information repositories. Which information repository can be the likely target of the APT?

Answer : Sharepoint

Collection is the category to look in for an answer, for it defined as being the process of gathering intelligence and data. Knowing this, we will find that APT28 is reported to use Microsoft Sharepoint services, which is an information repository because is it used as a document management and storage, content management, and team collaboration.

![Pasted image 20240726203631.png](/assets/img/Pasted%20image%2020240726203631.png)

---

Q10 : Although the APT had collected the data, it could not connect to the C2 for data exfiltration. To thwart any attempts to do that, what types of proxy might the APT use? (Answer format: <technique 1> and <technique 2>)


Answer : external proxy and multi-hop proxy

Under C2, or Command and Control, APT28 is reported to use two types of proxies : 
- External Proxy : which is an intermediary between a client's device and the internet.
- Muti-hop Proxy : which is the process of using many proxies before getting to the target, to maximise anonymity.

![Pasted image 20240726203820.png](/assets/img/Pasted%20image%2020240726203820.png)

----


Q11 : Congratulations! You have helped Sunny successfully thwart the APT's nefarious designs by stopping it from achieving its goal of stealing the IP of E-corp.

Answer : No Answer Needed


---

This was a fun room :).