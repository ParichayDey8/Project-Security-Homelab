Cybersecurity Homelab Overview
In this homelab setup, we have created a realistic, enterprise-level environment that mimics a typical corporate network, complete with Windows and Linux systems, security monitoring tools, and attack simulation capabilities. Here's an overview of the key components and their roles within your lab:
________________________________________
1. Windows Server 2025 (Domain Controller with Active Directory)
•	Role: The Windows Server 2025 acts as the Domain Controller (DC), managing the network's identity and security. It hosts Active Directory (AD), which is responsible for authentication, centralized management of users, groups, and devices, as well as handling DNS, DHCP, and Single Sign-On (SSO) services.
•	Functions:
o	Centralized Identity Management: AD allows for the management of user credentials, permissions, and group policies across the domain.
o	Network Security: The server helps control access to resources, enforce security policies, and monitor network traffic.
o	Key Role in Security Simulation: As the backbone of your simulated corporate environment, this server supports various attack vectors, such as privilege escalation, domain-joined device vulnerabilities, and lateral movement scenarios.
________________________________________
2. Linux Client with Wazuh Agent
•	Role: The Linux Client simulates a user workstation running Ubuntu, which is typically used for tasks like software development, office work, and networking.
•	Security Configuration:
o	Wazuh Agent is installed on the Linux machine to monitor system activity, detect security incidents, and report data back to the Wazuh Manager on the security server.
o	Features: Wazuh collects logs, performs real-time intrusion detection, file integrity monitoring (FIM), and vulnerability scanning to ensure the Linux system remains secure and compliant.
•	Key Use Case: The Linux client helps test the security posture of open-source operating systems in a corporate environment and ensures that any compromise attempts are detected by Wazuh.
________________________________________
3. Windows Client with Wazuh Agent
•	Role: The Windows Client represents a typical employee machine in a corporate environment running Windows 11 Enterprise.
•	Security Configuration:
o	Like the Linux client, the Wazuh Agent is installed to provide continuous monitoring and send security alerts back to the central Security Box (Wazuh server).
o	Features: Real-time detection of suspicious activity, auditing Windows events, monitoring user behavior, and identifying potential threats like malware, unauthorized access attempts, and privilege escalation.
•	Key Use Case: The Windows client allows you to simulate common threats targeting Windows systems, such as malware infections, phishing attacks, and unauthorized system access, while leveraging Wazuh for detection and analysis.
________________________________________
4. Ubuntu Corporate Server
•	Role: The Ubuntu Corporate Server serves as the email server for your environment, emulating a critical part of the corporate infrastructure. This server is likely hosting essential services like email, file sharing, and possibly web applications.
•	Security Configuration: The server is hardened to simulate real-world configurations in enterprise environments. It is configured with necessary monitoring agents, such as Wazuh, to detect potential compromises in network traffic, system logs, and other sources of evidence.
•	Key Use Case: The corporate server tests the security of backend infrastructure, email systems, and the integration of Linux servers in a mixed-OS environment. It is also a potential attack vector that you can simulate exploitations on.
________________________________________
5. Security Box with Wazuh Configuration
•	Role: The Security Box is a dedicated security server where your Wazuh Manager is deployed. This server plays a critical role in monitoring and analyzing logs from all machines in the network—whether they’re Windows, Linux, or Ubuntu.
•	Security Configuration:
o	Wazuh: This open-source security monitoring tool is configured on the Security Box to manage log analysis, file integrity monitoring (FIM), intrusion detection, and vulnerability detection across the entire network.
o	Centralized Security Management: The Wazuh server is key to detecting real-time threats, responding to incidents, and enforcing security policies across the network.
•	Key Use Case: The Security Box acts as the centralized point of security monitoring and alerting. It allows you to simulate a real-world Security Information and Event Management (SIEM) system, ensuring that all suspicious activities are detected and logged.
________________________________________
6. Kali Linux Attacker Machine
•	Role: The Kali Linux Attacker Machine is the offensive testing platform used to simulate various cyberattacks on the environment. Kali Linux comes preloaded with a wide range of penetration testing tools, allowing you to assess the security of your network.
•	Security Configuration:
o	Kali Linux is a penetration testing tool that allows you to perform various ethical hacking operations, such as vulnerability scanning, password cracking, exploitations, and attack simulations like phishing, RDP brute-force attacks, web application testing, and network exploitation.
•	Key Use Case: The Kali machine is used for simulated attacks to identify vulnerabilities, test system defenses, and analyze how well the Wazuh security tools respond to various attack methods. You can simulate everything from initial access to lateral movement and privilege escalation.
________________________________________
Overall Lab Architecture and Flow
•	Domain Controller manages users, groups, and devices across the network, with centralized security policies and access controls.
•	Wazuh Agents installed on the Linux client, Windows client, and security servers monitor and report back to the Security Box, providing a real-time analysis of system logs, file integrity, and potential threats.
•	The Ubuntu Corporate Server adds a layer of simulated backend services and acts as an attack surface for network and email-related vulnerabilities.
•	The Kali Linux Attacker Machine continuously attempts to exploit potential vulnerabilities in the system and assess the effectiveness of the security setup.
Together, this homelab provides a comprehensive platform to test, defend, and attack network systems, offering a hands-on learning environment for cybersecurity professionals to practice detection, response, and penetration testing. It also mimics a real-world enterprise setup, simulating a variety of attack vectors and security defenses.



