---
title : "Intelligence is the cornerstone of Cyber Security."
categories: [Technical Concepts]
tags: [Cyber Threat Intelligence, Cyber Philosophy]
---


The close relationship between intelligence practice and the evolution of cybersecurity is evident to anyone familiar with the field's history. Many of the concepts, methods, and technologies that underpin contemporary cyber operations emerged from intelligence (the "spy" intelligence, not the "AI" intelligence) traditions. Yet, for reasons we will examine shortly, intelligence has largely been relegated to a small corner of the discipline under the label of "cyber threat intelligence." Even this important area has often been reduced in practice to the production of technical reports on malware and indicators of compromise (IOCs).

Yet cybersecurity ( and security across all domains) has always been, and will continue to be, fundamentally about information and how to "get" it. The core of the field is not about how to infiltrate or compromise a given system, but rather how to acquire information, how to interpret it, and how to act upon it. Questions of access, exploitation, and compromise matter only insofar as they serve broader informational objectives. Once viewed through this lens, the technical aspects of cyber operations become contextualized within a larger intelligence process.

To understand how this perspective was gradually lost, we must first examine what cyber intelligence actually is. More importantly, we must consider how a proper understanding of intelligence can reshape the way we think about cybersecurity, cyber careers, and the industry as a whole.

### A (very) brief history of the Cyber Security practice :

Cybersecurity is -like most modern information technology- a product of warfare. During the Second World War, and at the very moment when the first blueprints for modern computing were being created, cryptography gained the momentum and breakthroughs it needed. Although its foundations had been laid earlier in the century by scientists such as Kirchhoff, this period marked the first major surge in what we now call information security, as cryptography concerns itself with securing information by making it unreadable to an adversary.
The idea and reason for which cryptography exists was to be a way to "protect an information" among others, or if we may : as a way to ensure "Information security". This term is thrown around a lot, and usually it is given that if it is not an equivalent for cybersecurity, it is the case for cryptography (or it is just some buzz word that boring CISOs love to spit around). But alas Cryptography had (and in many cases still has) assumptions that prevent it from being fully equivalent to information security, let alone cybersecurity. Before we can understand what this means, we should first clarify that:

- Information security is concerned with the secrecy of information as it moves through the world, in all its states (at rest and in transit), as well as with the inference, acquisition, and protection of information. As such, it intersects with both privacy and cybersecurity, while remaining broader than either. 
- Cybersecurity is concerned with protecting the cyber world: a primarily **informational** and **abstract** world. However, it is not restricted to that abstraction, as this world ultimately resides on physical hardware (such as servers) and in specific locations (such as data centres and buildings), which also fall within the scope of cybersecurity.

At first, the assumptions required for cryptography to function were located on the "human side" of the information security spectrum. To prove this, if an encrypted message was divulged without the cipher being broken, it simply indicated a deficiency in human security. or, in other words, the existence of a spy or agent.

![cyber-security-diagram](/assets/img/d8926821-af4e-4ec7-9722-f95a44c27446.png)


But as technology advanced, more and more information management and information work were transferred to the cyber world. Saving, accessing, searching, and, more recently, analysing information have all been outsourced from humans to cybernetic systems (more than merely machines). Information remained at the centre, but the way we dealt with it changed, creating new responsibilities for cyber security.

This change was not separated from a concurrent change in the way humans organize inside the fortresses they built. The philosophical assumptions underlying the technical world enabled the recreation of feudal-like communities, where digital landlords rule and own everything, while "highway robbers" or militias periodically raid their stores of wealth. The "police" and the "militias" (the defenders and attackers in Cyber Security per this analogy) became trapped in a perpetual cat-and-mouse pursuit. In doing so, attention was gradually diverted away from the fundamental problem of acquiring and protecting information and toward the narrower problem of finding vulnerabilities and patching them. Dealing with hits and run instead of building a system of security.


But aren't they the same thing? Not really. If we follow the logic to its conclusion, **finding vulnerabilities and exploiting them would merely be a branch of a broader intelligence function whose purpose is to protect informational assets.** In such a framework, disciplines that are often dismissed by "CTF-bros" as less important (PS : OSINT) would carry the same weight as penetration testing, if not more. The value of a practice would not be determined by its technical sophistication, but by its contribution to acquiring, protecting, or understanding information.

Such a shift in the POV would also transform cybersecurity education. Information theory would become central. "Intelligence" concepts would become the organizing principles. Technical skills would remain important, but they would be understood as means rather than ends, and as means that evolve continuously with technology. Under this view, we would not see hackers panicking because an AI can write exploits better than they can; writing exploits was never the objective in the first place. The objective was always to obtain, protect, or act upon information.

Anyway, what about the intelligence branch itself? What is commonly referred to today as Cyber Threat Intelligence (CTI) is often presented as cybersecurity's intelligence component. In practice, however, CTI has largely inherited the same biases as the rest of the industry. Rather than functioning as a true intelligence discipline, it is frequently reduced to the collection and dissemination of technical indicators, malware analyses, and reports on adversary infrastructure. 
Woo to us if we dismiss such activities, but these are not "intelligence" (it is a part of it as we will explain shortly). A list of indicators of compromise is information. An assessment of an adversary's intentions, capabilities, objectives, and likely future actions is intelligence. So how should this intelligence be ?


### An (also brief) Guid to the hows and shoulds of CTI :

The gap between what a Cyber Threat Intelligence professional is supposed to do in theory and what they actually do in practice is enormous. It seems that the "secondary" tasks have gradually become normalized as the core of the profession. 
Usually, the main occupation of a CTI analyst is to track the TTPs of APTs, short for the Tactics, Techniques, and Procedures of Advanced Persistent Threats (which are, in our earlier analogy, the militia groups and their "ways" of doing things). The professional therefore dives into tactical intelligence, attempting to triage and detect malware signatures, and perhaps even attribute them to a specific group based on the methods used to gain access, maintain persistence, or write code. It is often a reverse-engineering job, and only rarely an intelligence one.

If this were merely the occupation of an intelligence unit within a specific company or organization, it would be perfectly understandable. A bank would not spend much time asking, "Why would they attack us?" because the answer is usually obvious: money. Nor would it seek to identify and apprehend the perpetrators, as that is primarily the work of law enforcement. The problem arises when cybersecurity vendors stop at this level as well, without developing intelligence capabilities at the operational and strategic levels. If geopolitical implications are considered irrelevant, if the impact of AI on offensive cyber operations is deemed out of scope, if the identity and location of APT members are regarded as somebody else's problem, and if the infiltration of underground networks or the analysis of influence and propaganda campaigns are ignored, then what remains of information security, which the very reason all of this exists in the first place?

![cyber-intelligence-strategy](/assets/img/Pasted%20image%2020260529224736.png)

At this point, a question may arise: "But clients are asking for these services. We are simply responding to market demand. What else should we do?"
The "invisible hand" of the market is a useful concept for understanding capitalism; it is not a doctrine carved in stone. Markets can be shaped, and clients are often unaware of the value of strategic and operational intelligence work. States and large organizations already outsource significant portions of their security functions, and there is no reason why broader intelligence activities could not be included if the market matured to recognize their value.

Now, how should this be done?

A comprehensive answer would require an entire book. And many authors have done an excellent job of providing one. A notable example is _Cyber Threat Intelligence_ by Martin Lee. But for the sake of our increasingly short attention span readers, we can rely on one of the most fundamental concepts inherited from the intelligence tradition: the Intelligence Cycle.

This Cycle can be useful for the entire cybersecurity division For now, however, let us remain within the CTI landscape and examine how it could be expanded beyond its current limitations.

![intelligence-cycle](/assets/img/Pasted%20image%2020260529224115.png)

##### 1. Planning and Direction

This is the step in which we clarify "what we are seeking". As we know, data is effectively unlimited and constantly generated; our task is to pierce through it, place it into context, and transform it into information. This is not an easy task, it needs careful preparation and scoping. 
An example might be intelligence gathering about a specific business: who targets it, what assets are usually targeted, how attackers typically gain access, and, if there is a specific group involved, who they are.
This means that we must ask the right questions before we can hope to obtain the right answers.

##### 2. Collection

The means by which we collect information are so numerous that covering them all would defeat the conciseness of this article. Penetration testing, for example, is a mean of collection, whether by producing a report about an adversary's defensive capabilities or by obtaining information directly through access.
OSINT, SIGINT, HUMINT, and many other disciplines are all vectors, doors through which we can either compromise or reinforce the territory we seek to protect from an information security standpoint, and that would help us answer the question "what is in there?".

##### 3. Processing and Exploitation

Here, the collected data enters a phase of understanding. We ask ourselves: what did we actually find? Who can make use of it? And how?

It is important to note that this processing stage contains many assumptions that require validation, otherwise we risk falling into the familiar problem of mislabelling and misattribution. This has been a recurring issue in intelligence practice in recent years (for many reasons, most of them are "mindset-related", we may cover them later.), because there is always this tendency toward confirmation bias and the projection of our own assumptions into the labels we assign. For example : we may assume that the "bad hackers" are from a specific place, and therefore we interpret everything pointing towards other possibilities as being "a bait" or a "faint" to lure us.
Of course, these are often considered "luxury" problems, as most security professionals rarely concern themselves with such issues.

##### 4. Analysis

This is perhaps the most critical step, where we answer the question: _what does it mean?_

Analysing intelligence requires both broad and deep knowledge, as well as a mindset capable of connecting disparate pieces of information and placing them within a coherent context to paint the bigger picture.
This is where AI can serve as a powerful accelerator and enhancer. However, assuming that it can replace the nearly limitless contextual reasoning of the human mind (which is a phenomenon we still do not fully understand) is a serious mistake.

##### 5. Dissemination

"*What should be done with this information?*" is the central question at this stage.

Here the loop closes, as the intelligence function both delivers its output to those who need it and begins preparing for future collection and operational activities.

The application of this cycle can span every operational layer. We commonly see it applied to indicators of compromise, malware analysis, and similar tactical artifacts. Yet when it comes to connecting operations to the broader struggles taking place in cyberspace, to geopolitical developments, to assessments of adversarial capabilities, or to the construction of comprehensive intelligence plans, things suddenly become "tedious" for the strictly technical engineer.


### Conclusion 


We have seen that security in the digital world is, first and foremost, about information. The practice of acquiring, protecting, and exploiting information in an adversarial environment (a fancy name for war) is known as intelligence. Therefore, intelligence must be a cornerstone of cybersecurity, both as a professional practice and as a framework for education.
We are not trying to undermine the technicalities of cyber security. Instead the idea is to act in a good context. If cybersecurity is ultimately about information, then intelligence should occupy a far more central place in the discipline than it currently does. We will explore the practical implications of this shift in future articles.