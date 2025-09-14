Passban IDS: Comprehensive Security Analysis & Vulnerability Assessment

Research Overview
This repository contains my MSc Cybersecurity dissertation analyzing Passban, an anomaly-based Network Intrusion Detection System designed for IoT edge devices. Through systematic experimental validation, I uncovered critical flaws in detection capabilities, training methodology, and practical deployment challenges that weren't documented in the original research.
Completed: 2022 | Degree: MSc Cybersecurity | Duration: 6 months of hands-on testing
What I Actually Discovered
Rather than simply validating existing claims, my research revealed significant gaps between Passban's theoretical capabilities and real-world performance. I conducted over 100 attack scenarios using professional penetration testing tools to evaluate detection accuracy, false positive rates, and system reliability.

Technical Methodology & Tools

Experimental Setup
Hardware: Raspberry Pi 4 Model B Rev 1.2 (edge device simulation)
Deployment: Docker containerization for reproducible testing
Network Configuration: Isolated lab environment with controlled attack scenarios
Power Analysis: Multimeter measurements during various attack states

Attack Simulation Tools
Network Scanning: Nmap (17 different scan types evaluated)
Brute Force Attacks: Hydra, Nikto
Traffic Flooding: Hping3 (SYN, UDP, ICMP floods)
Traffic Analysis: Wireshark, NetMate
Network Manipulation: Arpspoof, custom scripts

Machine Learning Analysis
Algorithms Tested: Isolation Forest, Local Outlier Factor (LOF)
Training Validation: Custom attack scenarios during training phases
Performance Metrics: Detection rates, false positives, resource consumption

Attack Detection Performance
Successfully Detected Attacks:
Passban reliably identified HTTP brute force attacks against web interfaces, consuming 4.7-5.0 watts during detection. SSH brute force attempts targeting the secure shell service were consistently flagged, with power consumption ranging from 4.1-4.3 watts. VNC brute force attacks against the remote desktop protocol were also detected effectively, using 3.9-4.0 watts of power during the process.
Partial Detection Capabilities:
Network reconnaissance proved problematic for Passban. Out of 17 different Nmap scan types tested, only 6 were successfully identified. The system detected version detection scans, aggressive scans, script scans, IP protocol scans, and UDP scans, but missed critical reconnaissance techniques including stealth SYN scans, null scans, FIN scans, XMAS scans, and ACK scans. Power consumption during scanning activities ranged from 3.6-4.5 watts.
Complete Detection Failures:
Flooding attacks exposed significant blind spots. SYN flood detection was inconsistent at best, working only during initial system deployment but failing on subsequent attempts despite consuming 4.9-5.3 watts. UDP flooding attacks went completely undetected while consuming 5.3-5.7 watts, representing the highest power usage observed. ICMP flood attacks similarly bypassed detection entirely, consuming 4.9-6.0 watts. ARP spoofing attacks, which enable man-in-the-middle scenarios, were not detected despite consuming 3.8-4.7 watts of power.

1. Training Module Failure

Attacks performed during training are still flagged as anomalies post-training
Machine learning model fails to incorporate new "normal" behavior
Web interface bugs prevent proper training session management

2. False Positive Issues

Legitimate UPnP/SSDP multicast traffic flagged as attacks
Normal web requests (CSS files) are marked as suspicious
A high false alarm rate would cause alert fatigue in production

3. Stealth Attack Blindness

Most reconnaissance scans go undetected
Sophisticated attacks using normal traffic patterns bypass detection
Limited effectiveness against advanced persistent threats

Technical Contributions
Original Research Elements

Comprehensive Nmap Analysis: First systematic evaluation of 17 scan types against Passban
Power Consumption Validation: Confirmed edge deployment viability (3.3W baseline)
Training Methodology Critique: Discovered fundamental ML model update failures
False Positive Documentation: Identified specific benign traffic patterns causing alerts
Extended Attack Surface: Tested attacks beyond the original paper scope

Practical Security Insights

Detection Gap Analysis: Quantified blind spots in anomaly-based detection
Resource Efficiency Validation: Proved suitability for resource-constrained devices
Deployment Readiness Assessment: Identified barriers to production deployment

Technologies & Skills Demonstrated
Cybersecurity Expertise:

Penetration testing methodology and execution
Network traffic analysis and pattern recognition
IoT security assessment frameworks
Machine learning security applications
Vulnerability research and documentation

Technical Skills:

Docker containerization and deployment
Linux system administration and networking
Python scripting for automation
Hardware security testing procedures
Statistical analysis of security metrics

Tools Proficiency:

Network reconnaissance (Nmap, Nikto)
Attack simulation (Hydra, Hping3, Arpspoof)
Traffic analysis (Wireshark, NetMate, tcpdump)
System monitoring and performance analysis

Real-World Impact
This research provides a framework for rigorously evaluating IoT security solutions before deployment. The methodology can be applied to assess other edge computing security tools, helping organizations make informed decisions based on actual performance rather than vendor claims.
Key Takeaways for Industry

Anomaly-based IDS requires careful tuning for diverse IoT environments
Academic security solutions need extensive validation before production use
Edge security tools must balance detection accuracy with resource constraints
False positive management is critical for practical security operations

Conclusion
While Passban represents an important step toward lightweight IoT security, this research identified significant limitations that prevent effective real-world deployment. The findings highlight the need for more sophisticated anomaly detection algorithms and robust training methodologies in edge computing security.
This analysis demonstrates that rigorous, hands-on security testing is essential for validating academic research claims and ensuring security tools actually protect the systems they're designed to defend.

Research Context: MSc Cybersecurity Dissertation, 2022
Testing Environment: Controlled laboratory setup using ethical hacking principles
Full methodology and detailed findings available upon request
