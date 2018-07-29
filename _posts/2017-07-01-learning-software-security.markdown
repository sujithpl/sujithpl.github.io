---
layout: post
title:  "Learning about Software Security"
date:   2017-07-01 00:00:00 -0500
categories: professional
tags: [java, programming, security]
---
Before I started my journey to become a Software Engineer, I did not think about software security much beyond installing a good anti-malware product on individual computers and configuring the wireless network with the most advanced security options. As an ordinary user, I just had to use strong and unique passwords for each of my online accounts.

Of course, now I realize that there is a lot more to it all than just following the above guidelines. I like to classify the topic of software security into three areas.

- **Network security:** Set of measures to protect the underlying network, computing and data resources from unauthorized access and service disruption.
- **Application security:** The entire gamut of technical concerns such as SQL injection, buffer overflow to permissions of files deployed in production.
- **Logical security:** The business rules controlling user role based access to application functions and data.
I was recently able to dive deeper into the application security aspect of software security through a few different means.

At work, I freed up a little bit of time to go back and complete a couple of online training courses that I had scheduled a while ago. The [first course](https://www.synopsys.com/software-integrity/training/software-security-courses/foundations-of-java-platform-security.html) was a comprehensive introduction to application security for a Java developer. It covered a range of topics from the [OWASP Top 10](https://www.owasp.org/index.php/Category:OWASP_Top_Ten_Project) and [PCI DSS](https://www.pcisecuritystandards.org/document_library?category=pcidss&document=pci_dss) to cryptography and [vulnerabilities within the Java language](https://wiki.sei.cmu.edu/confluence/display/java/SEI+CERT+Oracle+Coding+Standard+for+Java). The [second course](https://www.optiv.com/services/security-awareness-training/elearning) was specifically about web application security concepts. This is the stuff developers usually think of when hearing the term “software security”.

Both the courses helped me get a better grasp of the fundamentals of software security. I began to see how I could incorporate the lessons from them into my own development practices.

Then, I had the opportunity to attend two Meetups on associated topics within a couple of weeks of each other. I gained a further understanding of the practical aspects of software security from these sessions. I decided to document my takeaways from them in this post.

## [Introduction to Ethical Hacking by Mike Erman](https://www.meetup.com/RVA-Software-Development-User-Group/events/239684172/)
- The biggest security threats originate from inside the organization’s network, not from outside. Most of the damage occurs when people fall victim to phishing or social engineering attacks.
- Default configurations of many Operating Systems and Networking Software used in companies are insecure.
- Even if the configurations are secured, patches or upgrades to the components above may revert them back to insecure settings.
- Once inside a network, malicious hackers can use powerful command line tools – that are openly available – to scan other connected resources and compromise them.

## [Secure Coding – Lessons Learned by Bill Smith](https://www.meetup.com/Richmond-Java-Users-Group/events/239299206/)
- Security cannot be bolted on at the end of the development cycle. It needs to be incorporated into every step of the process.
- Perform threat modeling and risk assessment during the initial stages of a project.
- Build security related deliverables into the product backlog.
- Some of the risk mitigation measures may have to be deferred to the clients using the product.
- Code signing and certificate management get really complicated in CI environments.
- Keep IOT/embedded devices off the internet.
- Both the JDK and popular third party libraries have vulnerabilities. Those might not always get fixed immediately after they are discovered.

Overall, I walked away with a great appreciation for the importance of software security and the amount of responsibility developers have to ensure that the software they develop is secure.
