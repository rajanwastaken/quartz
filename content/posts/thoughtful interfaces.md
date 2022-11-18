---
title: Designing Collective Community Interfaces
date: 2022-10-19
tags:
- work
- community
---

At my school, clubs develop teams to streamline workflows and produce content as quickly as possible. One of the most common positions was **web and tech**, providing students the opportunity to take technical challenges in designing websites and configuring AV equipment. While websites like these help provide a cohesive set of information for each club, it brings **brand new complications in the communication of new knowledge**.

This year, for my school, I decided to get rid of the need for separate websites that require high-maintenance and build a cohesive platform for all students. In conversation with several students, there were a few postulates:
1. This should also act as a club directory. Students want to know what clubs are available and how to learn more about them. This includes a status, descriptions and team details.
2. Only students with specific email addresses should be allowed to access the platform, as a security issue. It was also recommended to use email-link login to ensure only the user can access their platform.
3. Club executives should be able to post and manage content as administrators. One could have member access, writing access or administrator access.
4. Content should be divided **[[thoughts/Atomic Design|atomically]]**. Organizations are divided into repositories, each of which with notebooks consisting of indiviudal posts. 

![[images/Pasted image 20221117094111.png|Home View]]

The primary issue with education is that it’s standardized—means for self-study are absolutely critical to turn weekly club lessons into meaningful interactions. Within my school, I experimented with productive tools that inevitably resulted in the production of a school-wide platform.

Following my internship at [[camp-social|Camp Social]] and work at [[hack club|Hack Club]], I felt comfortable designing and producing large-scale platforms. In the platform, similar to Slack or Snapshot, you can view all communities on the left hand side. The default page is a club directory. Within each page, there are customized repository views based on the club's themes and objectives. Individual organizations/clubs look like this:

![[images/Pasted image 20221117175415.png]]

Currently, I am working to implement this platform with several other schools within my area and globally. I hope that this tool can make the communication of knowledge to teens like myself easier, for ambitious students ready to learn and teaching coordinators prepared to share what they're good at. 

As of now, there are hundreds of users on the platform, **with ~100 daily active users**. Once the expansion launches, the platform will handle thousands of students internationally. 

### Previous Iterations

The very first iteration was meant for a single club. Ironically, it became a platform for a single-use case that we would never use. 

![[images/Pasted image 20221117174807.png]]

Following countless design iterations, it started to come together. The primary feedback for this iteration was customizing colours and making it less cluttered, especially for those with smaller screen sizes.

![[images/Pasted image 20221117174650.png]]

Before this idea began, there were several sources of inspiration that existed in different mechanisms. In each stage, I developed further insights from core users that would be genuinely interested.

### Stage 1: Health Science Platform

The goal was to streamline education and centralize all the content needed. While the content was not intensive, there were four key advantages for teachers & students.

1.  All content existed on a single platform, making case studies, terminology and weekly curriculum a constant. This often could replace the need for slideshows, or in other times make pre-existing slideshows more accessible during independent study.
2.  The content was hosted on a single database, meaning adding content was incredibly simple—all information was dynamically updated, meaning instructors can add anything they need immediately.
3.  This enabled diversified content that was readily accessible—a successful replacement to subsequent Google Classroom posts. Weekly content is easily organized and separated from the resources, making access to previous lessons simple and finding quick resources (ie case studies, exemplars & terminology) simple.
4. It scaled. New features (ie semantic search, adding individual rooms, authentication and on-site posting) were implemented on the same database at extremely low maintenance.

![[images/Pasted image 20221117090616.png]]

### Stage 2: Discussion

I hosted conversations with several students who sought value in digital platforms. 

Overall, I came to three conclusions:
1. Students that were new to clubs wanted a place for self-study, as they were unable to sufficiently particpiate nor fare well in competitions. Clubs are often very niche, making it difficult to apply general knowledge.
2. For students that had a few skills did not find motivation to come to classes as knowledge was often repeated.
3. Students that had a lot of experience wanted to get ahead, but did not have the facilities to learn more content than what was taught to them in previous years.

### Stage 3: Sample Platform

For our school's coding club, I wanted to build a platform where students could access stream-based content and upload coding solutions. While it never went live, it provided insights into:
1. Make sure knowledge is available within a few clicks—if it takes too long to find information, then the knowledge does not hold the same value
2. Segment and classify all information. Make sure that information is shared methodically.

![[images/Pasted image 20221117180542.png]]

Within our school, platforms as such have changed the way that I understand the communication of information that — to me — often felt standard. I foresee this platform being used to streamline interactions within several schools & seeing new variations being deployed by young developers.

---