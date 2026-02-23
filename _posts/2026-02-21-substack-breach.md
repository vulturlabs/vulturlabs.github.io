---
layout: custom-post
title: "An interview with W1kkid, the Substack breach author"
thumbnail: /assets/images/substack/bf_avatar.png
color: blue
---

## What Happened

On October 2025 a malicious actor started exploiting Substack's systems, obtaining private user information. The company initially didn't notice this accident.

On the 2nd of February 2026 a user known as "w1kkid" or "wikkid" publicly claimed responsibility for the attacked and uploaded a _.csv_ file containing 662,751 rows of user data on the hacking forum Breach Forums.

![The email](/assets/images/substack/email.png)

A few days later Substack CEO's Chris Best notified the affected users through an email, stating that the Substack team "identified evidence of a problem with \[their\] system that allowed an unauthorized third party to access limited user data without permission".

## The Data

Substack describes itself as a "media platform for video, writing, podcasts, and creator-centered communities, all powered by subscriptions". According to its own data Substack can be proud of having **50+ million active subscriptions** across the platform and **5 million paid subscriptions** (_in March 2025_). Given this role of being an important platform for intellectuals, journalist and academics with huge audiences this data leak is particularly concerning.

The dataset contains several personal identifiers such as usernames, display names, email addresses (662,687 unique emails) and phone numbers (271,986 unique numbers).
From the country codes of the phone numbers it was possible to infer the possible country of origin of the accounts. The most affected accounts come from the US, the UK and India, followed by Brazil, Australia, Spain, France, Italy, the Netherlands and Nigeria. Moreover, it's concerning that a subset of the leaked emails may come from "sensitive" domains such as _.edu_, _.gov_ and even _.mil_.

Other secondary information such as the account bio, account creation timestamp and other internal metadata is present as well. As also confirmed by the Substack team, passwords and payment information were not exposed in the leak. However a particular concerning item may be the "Stripe ID" column. Even if this doesn't expose any additional private information, the combination of this identifier with the name, email and phone number may lead to additional attacks such as phishing attacks.

## The Interview

We have managed to get in touch with the alleged attacker and conduct a structured interview, in order to obtain more insights regarding this data breach.

Q - **First of all, thank you for accepting this interview. As said above Substack is considered a huge platform, home of several influential people, along with their private information as you have shown to us. It appears that you didn't violate the database directly but you may have abused some portion of the authentication process or a defective API endpoint in order to make it reveal more information than it should have, is this correct?**

A - _Yes, I used several API vulnerabilities to scrape the data you see in the leak._

Q - **I see, these attacks seems to become more relevant. If I remember correctly Twitter was breached in 2022 in a similar way. However, may I ask the reason why you weren't able to retrieve even more information? Were you relying on an email list for the scrape or did your method stopped working?**

A - _The vulnerability I discovered required me to invite the victim to my Substack team, which would then trigger an email to them. In response, Substack quickly added a rate limit on the endpoint I was using to add people to a team via their user ID. However the core vuln was still there: hitting the team invites (`api/v1/publication_user_invite`) endpoint would expose the data on accounts invited you see in my breach. It wasn't until I publicly posted the breach that Substack became aware of the issue and patched it._

Q - **What do you believe Substack and other companies should do in order to prevent the leak of sensitive information? Do you think they should invest more in their security? Do you have any comments regarding Substack's response to the incident?**

A - _I believe companies should invest in paid bug bounty programs. It's much cheaper to pay some ethical hacker 10K–30K for finding a critical bug than to risk millions in ransom if someone like me finds it. In addition, red teaming and anti-phishing training is useful. Ultimately, it's only a matter of time before a company gets hacked the key is really their incident response._

Q - **What are your favourites programming languages, libraries or tools that you use for your activities?**

A - _I mainly use python and bash for writing exploits and scripts, some of my favorite tools are burp suite, ffuf, trufflehog, amass, and custom tooling ive made._

Q - **Breach Forums is also known along with Telegram, Discord and other forums for being a gathering place for "The Com", a cybercrime community which has raised many alarms for the young age of their members. Are you familiar with them?**

A - _Yes, I'm familiar with it. However, I find many "com kids" to be cringe unskilled skids. There are many different "coms" within the broader cybercrime scene, and I think BreachForums/hacking forums tend to attract more skilled people compared to communities like the "fraud com" on Telegram._

Q - **Would you say the platforms above are useful for acquiring possible team members, sharing knowledge and tools, or just hanging out according to your personal experience?**

A - _I like to do things solo, but sometimes I can learn things on forums or download other members breaches for later use._

Q - **Is breaching a platform very profitable? Or do you have different motives such as gaining notoriety and fame or improving your abilities?**

A - _It can be. Half of what I do is for notoriety or pseudo-hacktivism, and half is for profit._

## Conclusions

We would like to sincerely thank “W1kkid” for taking the time to participate in the interview. We are now able to have a much clearer understanding of how everything unfolded, as well as an interesting look into his personal perspective.
