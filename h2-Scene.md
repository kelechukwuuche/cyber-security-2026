# Darknet Diaries - Podcast Summary

### Podcast: Darknet Diaries. 
### Host: Jack
### Guest: Tanya
### Topic: AppSec, Security Incidents, Security Awareness

# Summary
I selected an episode of Darknet Diaries featuring Tanya, an application security specialist. In this episode, she discusses her work in software development, penetration testing, and cyber security incident response.

What I learned from the podcast:
* Security policies should be easy to find and understand. The host recalls when he worked for a different organization, and employees could not find the company's security policy even if it was present and the organization passed security audits consistently. This demonstrates that simply because the company passed the security audit, it does not mean that the employees were 'aware' of the security procedures in place and were compliant with them.
* Software should be created with security in mind. Tanya became interested in security when someone demonstrated a SQL injection vulnerability on one of her team's applications. It showed how an attacker could take advantage of application vulnerabilities to access or information.
* Penetration testing may require prior approval/clearance. Tanya's first penetration test crashed a production server and corrupted database records. She later learned that the client was unaware of her testing activities. This illuminates the importance of good communication and well defined testing scope and rights.
* SQL injection is a hacker method that can result into data leakage. Tanya mentioned an example where a Canadian government application was attacked by blind SQL injection to obtain the database information. Attackers were able to slowly pull data from the database by sending true/false database queries. The incident also revealed shortcomings in application-security logging and inventory.
* In the incident response, proper investigation should precede accusations. Another time, employees thought an entire office building was infested with malware. However, Tanya's team found that employees were streaming the Winter Olympics all at once, which slowed the network. This reveals the importance of analyzing the technical evidence before making a security incident claim.
* Digital evidence must be protected. For example, in the podcast one of the IT help desk staff found illegal content on a computer but deleted the files and formatted the hard drive. This destroyed evidence and prevented a successful prosecution. The lesson here is to escalate any suspicious or possible criminal activities to the relevant incident response team without unnecessarily tampering with evidence.
* Tanja made it clear that Awareness and training for cybersecurity is so key. Help desk staff should be trained in the basics of security incident recognition and escalation flag. Employees should be encouraged to report suspicious activity, even if it is a false alarm.
* When security and development teams collaborate, they develop more secure applications. Tanya recalled a development manager who had refused to allow security testing of his application's code. But then one of his team's apps succumbed to a problem that turned into a costly security debacle and turned this manager into a champion of security testing and secure coding.


### Idea/ question in my mind:
I believe as a software quality engineer that security testing should be a part of the software development process and shouldn't be treated as an isolated activity that has to be performed prior to product deployment. The automated security checks and secure coding practices, as well as collaboration between QA engineers, developers, and security folks, can catch the vulnerabilities earlier and reduce the cost of the remediations.

Question: What are some of the best ways for organisations to automate security tests that are going into their CI/CD pipes immediately without impacting their speed of delivery on the software?

### Conclusion
Podcasts have taught me that cybersecurity is more than simply technical tools and blocking attacks. It's also about people, processes, communication, and the culture of an organization. Good security also requires cooperation of developers, testers, security professionals, and management in ameliorating the security practices, identifying risks, and responding to incidents.





# B

### Blog: Schneier on Security
### Article: We are still unable to secure LLMs from malicious inputs
### Author: Bruce Schneier


### What I have learned from this article:
* Prompt injection is a type of AI abuse in which attackers manipulate AI assistants into running malicious commands contained in documents or other input.
* Data security risks: Malicious instructions can manipulate AI assistants into accessing or exposing sensitive information, such as API keys.
* Trust boundaries: Typical AI systems have a hard time separating good user instructions from untrusted external content.
* AI agents also raise security concerns, and AI assistants with access to files, applications, and external tools could exacerbate the impacts of security vulnerabilities.
* Security constraints: Existing AI security measures do not always succeed in preventing all instances of prompt injection attacks.

### My idea/question
As a software quality engineer, I believe the testing of artificial intelligence's security aspect should be a part of the software development life cycle. Automated prompt injection test, restricting access, and constant surveillance could reduce security risks.
Question: If the AI models can produce different answers for the same inputs, then how do QA teams automate prompt injection testing in CI/CD pipelines?



# C

In my H1 CyberScience assignment, I reviewed a research article exploring how reinforcement learning (RL) can be used to automate penetration testing. I can connect this research to the Darknet Diaries episode featuring Tanya, where she shares her experiences with penetration testing, SQL injection vulnerabilities, and cybersecurity incidents.


* Manual vs. autonomous penetration testing: Tanya describes how she manually discovered vulnerabilities by experimenting with application inputs. Reinforcement learning research explores how AI agents could automate similar testing activities by learning from interactions with their environment.
* Learning through feedback: Tanya's experience demonstrates how penetration testers learn from application responses. Similarly, RL based systems use feedback and rewards to improve their decisions and identify potential attack paths.
* Real-world limitations: Tanya accidentally crashed a production server during an early penetration test. This highlights the importance of safe testing environments, which is also a challenge discussed in the research article.
* Automation challenges: The research identifies difficulties such as large action spaces, limited feedback, and poor generalisation to unfamiliar environments. These challenges suggest that autonomous penetration testing still requires careful evaluation before real-world deployment.


### My takeaway

As a software quality engineer, I believe autonomous penetration testing could complement traditional security testing by helping teams identify vulnerabilities earlier and improve testing efficiency.
However, AI-driven testing should operate within clearly defined boundaries, with appropriate human oversight to avoid unintended damage to production systems.


### References
* Liu, J., et al. (2026). Autonomous penetration testing using reinforcement learning: A review and perspectives. Expert Systems with Applications, 300, 130219. https://doi.org/10.1016/j.eswa.2025.130219
* Darknet Diaries. (2025). Episode 165: Tanya. https://darknetdiaries.com/episode/165/
