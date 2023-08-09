# Network-Hacking

Project Report
Each group member should report on what they accomplished in the project.
Johnathan Casanova: Report (300-400 words)
This intense and enlightening project focused on creating a Python Flask web application purposefully susceptible to network-based attacks. It allowed us to understand the real-world implications of reverse shell vulnerabilities and remote code execution, which an attacker could exploit by leveraging the Python module Scapy.
The developed application is a simple search feature that looks through a collection of book titles. Despite its straightforward functionality, we intentionally integrated a considerable security flaw, demonstrating the vulnerability to reverse shell and remote code execution attacks. We left the debug mode active, which, when exploited, permits arbitrary Python code execution - a significant security risk.
My role involved creating multiple Python scripts: arp_spoofing.py, http_sniffing.py, scan_network.py, and net_interfaces.py. These scripts formed the backbone of our network-based attacks, leveraging Scapy's capabilities. Additionally, I developed parts of the main application file, app.py. This involved implementing the function to search the book list and introducing the command execution vulnerability.
Additionally, I was responsible for setting up the target machine (a web server) and the attacker machine (a Kali Linux instance). This required a deep understanding of both systems to ensure they interacted correctly and that the attack scenarios were authentic.
An integral part of my role was researching and implementing network-based attacks. Through rigorous testing, I ensured the accuracy of our simulated attacks and the overall effectiveness of the project. This hands-on experience of exploiting application vulnerabilities was genuinely eye-opening, emphasizing the importance of following robust security practices.
In conclusion, this project successfully achieved its objective by creating a deliberately vulnerable Flask application. The project underscored the significance of securing applications and highlighted the potential consequences of lax security measures. It's worth reiterating that this project was designed strictly for educational purposes, helping us better understand and mitigate potential security risks in real-world applications.
Md Jayadul Islam: Report (300-400 words)
In this project, I was responsible for constructing and hosting the web application locally. I initially planned to develop the web app using HTML, CSS, and JavaScript. However, during the project's creation, I encountered several challenges. The primary constraint was that hosting on the internet was not allowed; we could only host and carry out the attack within our local network. This restriction prompted me to consider using Docker as a potential solution.

Consequently, I created a Docker container and hosted it on the Apache HTTP server, which I found on the Docker Hub (link: https://hub.docker.com/_/httpd). This marked my first experience with Apache on my local host, and I began familiarizing myself with the Apache HTTP server. However, I encountered difficulties running it on Apache, which led me to explore other options for web application hosting that would enable us to launch the attack effectively.

During the project, our primary objective was to exploit vulnerabilities in the web application server. Therefore, hosting the web application was a critical aspect. To address this, I discussed the matter with my teammate Johnathin, who offered a simple solution. He recommended using the Python library Flask (link: https://flask.palletsprojects.com/en/2.3.x/). I delved into Flask's Documentation and watched some YouTube videos. Within a day, I successfully set up my first web application on my local host using Flask. Subsequently, I proceeded to develop my webpage.

Hosting on the Flask process was smooth and straightforward at this stage. I designed the webpage using HTML and CSS while the functionality was implemented in Python, with the Flask library being imported. Per our project's requirements, the web application needed to be vulnerable, and the webpage featured a search box to receive user input. We simulated the web application as a search library for programming books like C++, Python, Java, or SQL. We purposely didn't sanitize user input in the search box, creating a vulnerability enabling us to execute the attack on the web application server.

Sourov Das: Report (300-400 words)
Testing Report: Web Application Attacks using Local Network Scanning, ARP Spoofing, and HTTP Sniffing
This testing report details the findings and recommendations of the web application's security evaluation using local network scanning, ARP spoofing, and HTTP sniffing techniques. This assessment's primary target was to identify any potential security concerns and flaws in the web application, especially in the context of attacks within the local network.

Environment Setup: 
The testing environment was configured with the following components:

Target Web Application: The web application under examination.
FlaskApp: Python library for network scanning, ARP spoofing, and packet analysis.
Local Network: A controlled private network comprising various devices, including the system executing the test scripts, the web application server, and other devices.

Testing Techniques:
The assessment involved the following techniques:

1.	Local Network Scanning
The FlaskApp was used to run a local network scan to find open ports and active hosts. The objective was to recognize potential entry points for attackers. 

2.	ARP Spoofing
ARP spoofing was employed to manipulate the local network. This technique aimed to intercept network traffic, redirecting it through the attacker's system, allowing packet inspection and analysis.

3.	HTTP Sniffing
  HTTP sniffing was used to record and examine HTTP traffic within the local network using Python programs and the Scapy package. The goal was to locate sensitive data, session tokens or login information.

Findings

1.	Local Network Scanning
The local network scanning yielded the following findings:
The target web application server IP address:192.168.1.25 was identified with the following open ports:

Port 8585 (HTTP): Open
Port 8686 (Python HTTP): Open
Other active devices on the network were discovered, including:
192.168.1.53

Open ports on various devices expose potential attack surfaces, warranting further analysis and validation to ensure these ports are secure and not susceptible to exploitation.

2.	ARP Spoofing
During the ARP spoofing process, we observed the following outcomes:
ARP tables of target devices were successfully spoofed, redirecting their traffic through the attacker's system. Network packets were intercepted and relayed successfully.

3.	HTTP Sniffing
Numerous HTTP requests containing plaintext credentials were captured, indicating a severe security risk. Session tokens and sensitive data were found in some HTTP headers, potentially facilitating unauthorized access.

Recommendations

Based on the findings, we recommend ensuring the web application enforces HTTPS with HTTP Strict Transport Security (HSTS) to encrypt data transmission and prevent man-in-the-middle attacks., to reduce the risk of credential theft. Encrypt Sensitive Data in Transit.
We also recommend conducting periodic security audits to identify and address new vulnerabilities and Conducting regular security awareness training for employees to educate them about potential ARP spoofing and HTTP sniffing attacks.

Conclusion

The combination of local network scanning, ARP spoofing, and HTTP sniffing techniques using the Scapy library exposed significant vulnerabilities in the web application's security posture. Addressing the identified issues and implementing the recommended measures will enhance the web application's resilience against potential attacks originating from within the local network.

Project Debrief
What challenges did you face in the project? How did you solve them? 
As we faced challenges, we remained determined in troubleshooting and debugging to ensure our web application worked flawlessly. Together, we conducted thorough testing to identify and resolve any potential problems, making our application more resilient and meeting the expected requirements.

In our quest to develop and host our web application, we encountered a challenge while using Docker. Although Docker provided a robust platform for containerization and deployment, setting up the Apache httpd server within the Docker container proved to be more complex than expected. We faced difficulties configuring the server and establishing smooth communication between the container and the local host. This hindered the seamless execution of our web application on the Apache server within Docker.
Fortunately, the remedy to this challenge came in the form of Flask, a Python web framework. As we delved into Flask's Documentation and explored its features, we quickly realized its potential as a user-friendly and efficient hosting solution. Unlike Docker, Flask offered a straightforward approach to building web applications, allowing us to focus on the application's functionality and development rather than complex container configurations.
With Flask, we could easily create routes, define functionalities, and render templates to build the web application. Flask's simplicity and minimalist design provided a breath of fresh air, enabling us to set up the application quickly and effortlessly on our local host.
Flask's built-in development server also allowed us to run and test the application directly without needing external server setups. This convenience streamlined the development process, empowering us to focus on the application's core features and security. By purposely leaving the search box unsanitized, we created an avenue to execute the planned attack on the web application server, mimicking real-world scenarios for vulnerability analysis.
In essence, Flask was the perfect remedy to the Docker challenge, as it facilitated the smooth development and hosting of the web application. Its user-friendly interface and powerful capabilities resolved the Docker complexities and accelerated the overall development process. As a result, Flask became the backbone of our project, enabling us to delve deeper into web application security, all while providing a rich learning experience in web development.

What did you learn by doing this project?
Throughout this project, we have gained substantial knowledge and conducted extensive research. From the project's inception, we have maintained ongoing discussions, engaging in regular Zoom meetings and exchanging WhatsApp messages. Our collaboration has been invaluable in successfully strategizing, developing, and implementing the project. While each member was assigned specific tasks within the group, we actively worked together to identify challenges and their solutions. As we embarked on the project, we familiarized ourselves with local web hosting using Apache httpd and explored the Python library Flask.
In this project, we also delved into various aspects of network architecture, understanding the intricacies of data transmission, routing protocols, and network security. As a valuable addition to our learning journey, we also explored the Python library Scapy. Before diving into Scapy, we recognized the importance of having a solid foundation in networking fundamentals. Concepts like protocols, IP addresses, and data flow in networks became essential building blocks for our understanding of Scapy's functionalities.Our proficiency in Python played a crucial role in effectively leveraging Scapy. As Scapy operates as a Python library, familiarity with Python syntax, data structures, and programming techniques proved indispensable in making the most of this powerful tool. With a solid understanding of networking and Python skills, we embarked on a hands-on learning journey with Scapy. Throughout our exploration of Scapy, we also discovered the importance of responsible and ethical usage, especially in the context of network security. By integrating Scapy into our learning arsenal, we gained practical insights into network analysis and cybersecurity. 

Moreover, it emphasized the importance of handling user inputs securely. We've seen first-hand how a seemingly innocent feature (like a search bar) could be manipulated into a potential attack vector by exploiting the improper handling of user-generated inputs.
The project also underlined the significance of thoroughly reviewing and understanding every line of code before deployment. Leaving the application in debug mode may seem harmless, but as demonstrated in this project, it can lead to potentially catastrophic consequences.
This exercise was an invaluable lesson in the importance of robust application security and will certainly inform our development practices moving forward. By creating and exploiting our vulnerability, we have gained a practical understanding of the importance of application security, something that will be beneficial in all our future projects.

Final Work

Include your final research, documentation, code developed, code demos. 
Research on technology background (2-3 pages, double-spaced, include in-text citations to any sources used) (6 points)

1.	Docker Apache httpd vs Python Flask Library -
Docker Apache httpd and Python Flask are two distinct technologies used in web development, each playing a unique role in the web application stack. Docker Apache httpd involves hosting the Apache HTTP server within a Docker container, providing a self-contained environment for deploying web applications with ease and consistency across different environments. This containerization approach allows for horizontal scaling and efficient load balancing, making it a suitable choice for projects requiring scalability. However, setting up Docker Apache httpd may require some initial learning about Docker concepts.(httpd - Official Image | Docker Hub. (n.d.). https://hub.docker.com/_/httpd ).
Flask is a web framework for Python that facilitates communication between software applications over the internet. It provides tools and principles for designing web services, enabling developers to build and manage web applications and APIs efficiently. Flask operates on the basis of URLs, identifying different resources and employing standard HTTP methods for performing operations on these resources. The framework follows an architectural style known as Representational State Transfer (REST), emphasizing statelessness in client-server interactions. By adhering to REST principles, Flask simplifies server design and enhances scalability. With its ease of use and seamless integration with Python, Flask has become a popular choice among developers for building web applications and APIs, supporting diverse projects in web development and beyond.
Overall, Flask's user-friendly interface, lightweight structure, and seamless Python integration make it an excellent choice for developers looking to build efficient and scalable web applications. Its philosophy of simplicity and the ability to adapt to various project sizes and requirements have contributed to its popularity and position as one of the leading web frameworks in the Python ecosystem.
2.	Python Scapy -
Python Scapy is a powerful packet manipulation library for Python, serving as a fundamental tool for network analysis and security tasks. It equips users to explore and interact with network packets, enabling developers to create, modify, and send packets across a network while also capturing and analyzing network traffic. Scapy supports many protocols and packet types, facilitating seamless work with networking technologies such as Ethernet, IP, TCP, UDP, DNS, ARP, and more. Its flexible and interactive shell empowers users to craft custom packets and observe real-time network traffic, allowing for network simulation, performance analysis, and troubleshooting. A key advantage of Scapy lies in its ability to operate at a low level, providing granular control over individual packets. This feature makes it particularly valuable to network engineers, security professionals, and anyone seeking to understand and manipulate network traffic in a precise manner.
Overall, Python Scapy is a valuable asset for network exploration and manipulation, offering a comprehensive toolkit for tackling network analysis and security challenges. It is versatility and low-level control capabilities position it as a crucial resource for professionals in the networking domain, enabling them to interact with network packets effectively and gain valuable insights into network operations.
3.	Arp spoofing -
ARP spoofing is a type of cybercrime in which the hacker sends spoofed ARP messages to link their Media Access Control address or MAC address with the target's IP address. This way, the hacker gains access to the victim's device's communications, including sensitive data such as passwords and credit card information. ARP spoofing occurs when an attacker manipulates the relationship between Media Access Control (MAC) addresses and Internet Protocol (IP) addresses. ARP spoofing attack occurs on a local area network. 
ARP spoofing is considered dangerous as it's used to initiate attacks like DoS and session hijacking. It's just a starting point, and like any man-in-the-middle attack, can act as a starting point to more serious intrusions. Once the victim's device is corrupted, the attacker steers traffic toward them, using such information for the wrong actions.
The best way to stop ARP spoofing is to use VPN. VPN is a technology that encrypts the internet traffic and alters your online identity for secure browsing. 
4.	Http sniffing -
A technique used to record and examine HTTP communication between a client such a web browser and a web server is known as HTTP sniffing, also known as HTTP traffic sniffing or packet sniffing. This kind of cyberattack involves the interception and inspection of data packets traveling over the network by an attacker in order to retrieve sensitive data such as login passwords, session tokens, or other sensitive information sent in plaintext. The attacker could potentially obtain unauthorized access to sensitive information by listening in on unencrypted HTTP traffic using tools like packet sniffers or network analyzers. Web applications should use secure communication protocols like HTTPS, which encrypt data during transmission and make it more difficult for attackers to capture and decrypt sensitive data, to guard against HTTP sniffing attacks. 
5.	Reverse shell (Netcat) -
In network security and penetration testing, a reverse shell is a potent tool for gaining remote access to and control over a compromised system. Instead of the usual technique, when the attacker connects directly to the target, it involves the construction of an interface from the target system to an attacker-controlled machine. Due to its ease of use and accessibility, Netcat, sometimes known as "nc," is a flexible command-line utility that is frequently used to build reverse shells. On the attacker's computer, a Netcat listener begins to watch for incoming connections. The attacker afterward installs a payload on the target system, generally, a shell script or malware, which establishes a connection with the Netcat listener. As soon as the connection is made, the attacker gains a command prompt on the target machine, enabling them to execute various commands and perform malicious activities remotely. 
Netcat, frequently referred to as "nc," is a flexible networking tool that can be found in many different operating systems. It can read and write data throughout network connections and functions utilizing both the TCP and UDP protocols. It is a sophisticated tool for file transfers and managing networks, as well as a simple network scanner, port listener, and chat server. Netcat is frequently used in security audits and penetration tests to develop backdoors and create reverse shells on compromised systems. 

References

httpd - Official Image | Docker Hub. (n.d.). https://hub.docker.com/_/httpd
Welcome to Flask — Flask Documentation (2.3.x). (n.d.). https://flask.palletsprojects.com/en/2.3.x/)
Fadheli, A. (2019, July 28). Getting Started With Scapy: Python Network Manipulation Tool - Python Code.https://www.thepythoncode.com/article/getting-started-with-scapy
What is Arp spoofing - https://easydmarc.com/blog/what-is-arp-spoofing-and-how-to-prevent-it/
Praveen. (2023). What Are Sniffing Attacks, and How Can You Protect Yourself? Cybersecurity Exchange. https://www.eccouncil.org/cybersecurity-exchange/ethical-hacking/what-are-sniffing-attacks/
Stapel, G. (2001, August 3). What Is a Reverse Shell | Examples & Prevention Techniques | Imperva. Learning Center. https://www.imperva.com/learn/application-security/reverse-shell/



#Documentation (sources used for research on the technology and technical Documentation for tools, libraries, etc.) (4 points)

Docker Apache httpd - 
1.	Official Documentation - https://hub.docker.com/_/httpd
2.	Official Image - https://www.youtube.com/watch?v=WLBB1CZ9vo0
3.	Youtube Tutorial - https://www.youtube.com/watch?v=mO93QRna8ws&t=128s
Python Flask - 
1.	Official Documentaion - https://flask.palletsprojects.com/en/2.3.x/
2.	Official Library - https://pythonbasics.org/what-is-flask-python/
3.	Youtube Tutorial - https://www.youtube.com/watch?v=5aYpkLfkgRE
Python Scapy - 
1.	Official Documentation - https://www.thepythoncode.com/article/getting-started-with-scapy
2.	Official Library - https://scapy.net/
3.	Youtube Tutorial - https://www.youtube.com/watch?v=EuTAmtMGdNU
Arp spoofing -
1.	Sources - What is ARP Spoofing and How to Prevent It? | EasyDMARC
2.	Source - https://rb.gy/s8hjq
3.	Youtube Tutorial - https://www.youtube.com/watch?v=iEqq-6YDOlc
Http sniffing -
1.	Sources - https://rb.gy/by0bb
2.	Sources - https://rb.gy/vddqe
3.	Youtube Tutorial - https://www.youtube.com/watch?v=-rSqbgI7oZM
Reverse shell (Netcat) -
1.	Sources -  https://rb.gy/84lpv
2.	Sources - https://rb.gy/b4koi
3.	Youtube Tutorial - https://www.youtube.com/watch?v=KlzSBk7VMss
