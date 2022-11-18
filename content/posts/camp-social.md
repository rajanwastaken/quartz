---
title: "Interning at Camp Social"
date: 2022-10-31
tags:
- work
---

![[images/Pasted image 20221117232128.png]]

Communities form to coordinate efforts, share resources, and achieve positive-sum outcomes. While aligning the value received by community leaders and participants has always been important, modern communities can go further to establish a tighter connection between the value to members and the overall organization’s worth.

What we really desire is a place where we feel the sense of belonging that we felt in our childhoods. A place that was structured yet full of freedom and excitement. It was a place where we created memories and relationships that lasted a lifetime; where we could engage with others without feeling that stakes were high. 

_**Remember summer camp?**_

When I first met [Zvi Band](https://zvi.band), I was introduced to Camp Social — when introduced to the loneliness crisis that tools like Discord or Telegram might enable, it raised questions as to how we can restore humanity in digital connections. To me, Camp Social was the platform that enabled social contribution and recognized individuals for doing so. 

This summer, I interned as a Software Engineer with the intention to restore humanity on the internet — it was so much more. Through these five months, I **wrote & pushed 3245 lines of code, built microservices with Ruby on Rails, Solidity and Typescript and listened to 100+ hours of music** along the way. 

![[images/Pasted image 20221117235345.png]]

### There were two fundamnetal parts of the application that I worked on:

**The infrastructure to allow community members to meet and connect with each other through shared social activities, online or offline.**
- Employing [[thoughts/Atomic Design]] helped organize communities, broken down into individual events, each of which broken into user video conferences.
- We wanted to recreate the feeling of being in camp; this theme was critical to isolating and interacting with features of the platform. 
- We wanted to focus on making individuals feel valued and rewarded for their contributions. A common case study we drew from was [Project Aristotle](https://www.inc.com/justin-bariso/after-years-of-research-google-discovered-secret-weapon-to-building-a-great-team-its-a-lesson-in-emotional-intelligence.html)
- One can host small group sessions or facilitations of larger groups which follows our workflow: *members can post any kind of activity they want to host, others can RSVP, and attendance is tracked and rewarded.*

![[images/Pasted image 20221117235533.png]]

**A recognition and incentive mechanism to reward members to host and participate in those shared activities.**
- With a primary market in DAOs, incentivization was primarily on-chain. I wrote/modified Smart Contracts, and built microservices to wrap & interact with them.
- Wrote an API to connect with incentivization mechanisms and reward activity on the platform
- By tokenizing communities we would (1) reward bottoms-up social contribution (2) enable proof of participation mechanisms (3) identify individuals interested in socials for future engagement
- In reference to [Vitalik's interpretations of souldbound governance](https://vitalik.ca/general/2022/01/26/soulbound.html): *there are very bad things that can easily happen to governance mechanisms if governance power is easily transferable*. Hence, Camp Social aims to implement non-transferability in practice.

![[images/Pasted image 20221117235838.png]]

What we seek in communities is a sense of belonging to a greater whole. Unfortunately, the current experience in digital communities leaves a lot to be improved. The ability to form individual connections with other members is vital to the strength of the community. A noisy chat server does not help needed personal connections between community members - instead, it can feel like everyone’s shouting at each other across a crowded room. 

Overall, I was able to engineer features to a product that aims to restore humanity in the way we connect and interact on the internet. It challenged me to learn Ruby on Rails from scratch in one week, as well as take on a new endeavour in the field of tokenomics. The code that I shipped will help reward the ambitious and connect the those that want a break from the chaos we call the internet.

---
