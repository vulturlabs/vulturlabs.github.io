---
layout: custom-post
title: "A look inside FulcrumSec"
description: "An interview with the FulcrumSec Group"
thumbnail: /assets/images/fulcrum2.png
color: green
---

## Introduction

_FulcrumSec_ (also known as "Fulcrum Security" or "The Threat Thespians") is a financially motivated hacking crew focused on data breaches that came into action quite recently. The group is characterized by relying solely on code flaws or configuration errors instead of methods like social engineering or malware infections which are often leveraged by other threat actors. They have a website dedicated for shaming organizations who fail to pay the ransom, but it is interesting to notice how they explain the attack methodology and the structure of the exfiltrated data in great detail. Moreover it is their habit to scold the company for their security malpractices in their announcements. Their victims include several high provile companies in many different sectors, such as logistics, healthcare, electronics and finance. Most notably, the firm LexisNexis, which serves 85% of Fortune 500 companies, nearly all top US insurers, and major banks worldwide, has been compromised by the hackers.

## The Interview

Q - **From what we were able to see your preferred attack vectors are exploitation of vulnerabilities and misconfigurations. Have you ever used phishing, Initial Access Brokers, infostealer data or insiders like your "competitors" often do? If not why you have decided to proceed this way?**

A - No, we have never used any of those methods for initial access. FulcrumSec formed in part out of a desire to punish the guilty, so to speak. The organisations guilty of prioritising profits at all costs over taking care of the sensitive data that their users/clients/patients have entrusted them with. They're supposed to be guardians of this intimate data, and they are failing at that simple obligation.

These are the companies we expose: those who simply can't be bothered with the most elementary security. While phishing or credential stuffing via infostealer data certainly expose other types of vulnerabilities -- human weakness, password reuse, etc -- we have a simpler approach.

If a company is not making mindblowingly basic missteps that endanger their entire enterprise, they don't need to worry about us. The issue is that they all seem to. Keep an eye on our new concept campaign, The Hardcoded Horror Show (www.fulcrumsec.net/horrorshow) to see how many giant multinational corporations make the most basic of errors. The initial reveal: our breach of Avnet last year was due to a leaked Databricks token in the javascript of a staging page they'd forgotten about.

We should add that, from an economic perspective, we simply do not need to use those other methods. Our current methodology provides a massive firehose of exfiltrated data, to the point where we are limited only by the number of companies we can deal with at one time.

Q - **In one instance you decided not to release the full leak in order to prevent identity theft and other serious damages to the public. This and other signals suggest that even if you are primarily financially motivated, you also seem to have some sort underlying values or ideology. Could you elaborate more on this aspect?**

A - We minimise harm to the innocent whenever possible. In the case you refer to, the Australian media already had saturation-level coverage of the youX breach. Their clients and partner orgs were fleeing in droves. Class actions will likely follow. At that point, youX had already been made into a very effective example for us to point to when in talks with future companies. Why put hundreds of thousands more people at risk?

The principle of harm minimisation carries over into every breach we've carried out. Particularly with medical data or data that could impact individuals' physical safety, we have a policy of redaction to avoid unnecessary collateral damage.

Q - **Are there any "red lines" that you would never cross?**

A - Yes, many -- see the above. We also have been following a rule of non-disruption, meaning no ransomware (encryption or destruction), based on a common understanding among our members that we can make a staggering amount of money without ever shutting anything down by force. Our weapon of choice is shame, and it works.

Q - **Before deciding to target a company do you check its size and financial statistics first?**

A - Yes, but the order is a bit different. Since we cast a wide net based on misconfigurations and vulns, as you noted, we often decide what company to "target" after the actual breach has already happened, once we've assessed the data and done some research on the company. We are working through a backlog of hundreds of companies whose data we have in store, and we will only end up contacting a fraction of them. Due to this huge volume and our small team size, we only invest the effort if the breach stands to be devastating or existential in its impact, and the company has clear means to pay a worthwhile fee.

Q - **In one occasion you stated to have sold information to a third party. Is this a viable monetization strategy in case you do not get paid in the beginning?**

A - The only time we did this was with Avnet's business intelligence for $100k. This might sound good, but it is relatively a tiny sum compared to what cooperating companies will pay. It is likely a viable monetization strategy, but since Avnet we have preferred just to leak data for free in order to make an example of the uncooperative company. We believe we will make far more from the increased conversion rate than what could earn from selling the data.

We receive constant requests to purchase PII or financial data, and we decline them all for the ethical reasons mentioned above, as well as the fact that organising a sale a few thousand dollars is a waste of time that could be spent racking up more payments of $500,000+.

Q - **Do you have any favourite tools or programming languages that you find useful for your activities?**

A - We use AI agents to help us triage and analyse vast quantities of data, chunking it into manageable bits and passing it to the swarm. Even with strict orchestration, they make bizarre assumptions and errors in judgment, so everything flagged as sensitive must be human-verified, but it still speeds up data analysis by 100x, if not more.

We also use Trufflehog on a daily basis -- we have a custom fork that serves us very well.

Q - **What are the most common and dangerous mistakes that you've found during your work? And has a company ever been able to successfully interrupt or contain an attack of yours?**

A - The list is endless. We have two concept campaigns dedicated to the most elementary security blunders that cost massive corporations dearly.

Only one company has interrupted an attack-in-progress, but it was still too late, as we had hundreds of gigabytes already exfiltrated. Companies need to watch their cloud environments more carefully, it is astounding what you can get away with without even an attempt at stealth.

Q - **Ransomware operators usually encrypt the company's data after exfiltration, but your group doesn't do it. What is the reason behind this?**

A - As mentioned above, encryption/ransomware is far more destructive and disruptive than data extortion, and we can make a great deal of money without doing it, so why cross that line?

Q - **What is your opinion on "The Com" / "The Community" and young cybercriminals in general?**

A - We have no insight apart from what we read in the media, but it seems to us there is a lot of variance. You have the truly awful harm groups coming out of the Com, which do things like sextortion of children and are absolutely despicable, and then you have hackers like ShinyHunters, who may make poor decisions now and then but carry out legitimate, respectable attacks.

There's clearly some genuine talent there. We would encourage them to work on their opsec and stop threatening security researchers. They'll last a lot longer.

Q - **What practices do you adopt in order to protect your anonymity?**

A - One practice is avoiding answering questions like this with specifics, for one ;)

Q - **Are you an individual or a group? If so, it is difficult to coordinate operations and internal disagreements among members?**

A - We're a a small, tight-knit group. We are aligned on almost everything.

Q - **Have you ever collaborated with another threat actor?**

A - No. We receive requests for collaboration whenever we publish a new breach, and we have occasionally considered it, but the combination of ideological alignment and skillsets we would require in a collaborator is rare. Besides, we are lean and effective as is, so we are happy as we are now.

## Conclusions

We are grateful to FulcrumSec for stepping forward and taking the time to participate in the interview. These useful insights behind the motivations and the methodology of the group are certainly in the public interest.
