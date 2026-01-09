# ML-Assisted Offensive Security

## Objective

Developed an ML-Assisted Offensive Security framework designed to augment human penetration testers by providing a predictive "advisory" layer during engagements. Using Metasploitable 2 as a target environment, I engineered a Human-in-the-Loop (HITL) system that performs Machine Learning Inference on network reconnaissance data to prioritize attack surfaces. The system serves as a strategic assistant, utilizing a pre-trained model to recommend high-probability exploit paths with associated confidence scores. This framework maintains strict human oversight by requiring manual authorization for any offensive actions, which are then programmatically executed via the Metasploit RPC API, ensuring safe and controlled validation of vulnerabilities.

### Skills Learned


- API Integration: You learned how to use the pymetasploit3 library to bridge the gap between a custom Python environment and the Metasploit Framework.
- Algorithmic Logic: You developed a "Decision Engine" that filters and ranks potential exploits based on metadata (ranking, reliability, and service info).
- Automated Data Processing: You utilized pandas to read local CSV feature files and loop through data points for automated analysis.
- Metasploit RPC Management: You gained experience managing msfrpcd, including setting passwords, managing ports (55553), and configuring SSL/No-Database modes.
- Exploit Matching: You learned to search for and select specific modules (like vsftpd_234_backdoor) based on version detection.
- Service Version Identification: You used Nmap (-sV) to extract the "features" (names and versions) required for vulnerability matching.
- Virtualization: You managed a dual-VM lab environment using VirtualBox, ensuring connectivity between a Kali Linux attacker and a Metasploitable target.
- Network Addressing: You mastered the concept of IP/Port notation and the importance of static IP assignment in a virtual network.

### Tools Used


- Kali Linux: The primary Debian-based offensive OS used to host the attack infrastructure, the Python orchestration environment, and the MSF database.
- Metasploitable 2: A purposely vulnerable Linux VM acting as the isolated "Ground Truth" target for validating the AI assistant's predictive accuracy.
- Nmap (Network Mapper): The primary reconnaissance engine used for Service Version Detection (-sV), providing the raw high-fidelity text features required for the model.
- Scikit-Learn / XGBoost: The core ML frameworks used to execute the pre-trained predictive model, calculating exploit success probabilities based on service features.
- Pandas & NumPy: Data manipulation libraries used for Feature Engineering—transforming unstructured Nmap text into the numerical vectors required for model inference.
- Joblib / Pickle: Model serialization libraries used to load the pre-trained "Brain" into active memory for real-time decision-making.
- Python 3: The primary "glue" language used to build the data pipeline, manage the ML inference logic, and handle the user interface.
- pymetasploit3: The bridge library used to translate Python logic into API calls that the Metasploit Framework can understand.
- Metasploit Framework (MSF): The core exploitation engine used to deliver weaponized payloads and manage incoming shell sessions.
- Metasploit RPC (msfrpcd): The daemonized service that exposes MSF's capabilities via an API, allowing the Python script to trigger exploits programmatically.
- PostgreSQL: The backend relational database used by the Metasploit Framework to store host data, service version history, and discovered vulnerabilities. In the project, it acts as the Data Warehouse, ensuring that your Nmap scan results are persistent and searchable for the ML model.


## Steps


*Ref 1: ML-Assisted Offensive Security

<img width="541" height="390" alt="IOE3 drawio" src="https://github.com/user-attachments/assets/afa1b606-e1ec-48ce-9918-345c7bc657f1" />


This project integrates Machine Learning Inference into an offensive security pipeline to optimize vulnerability exploitation within a secure, Host-Only virtual network. An Inference ML Model (Strategic Advisory AI) analyzes a Metasploitable 2 target to identify high-probability entry points and predict attack success rates. This Human-in-the-Loop architecture enables the Kali Linux operator to transition from trial-and-error to a data-driven strategy, executing attacks only after the AI determines the most successful approach.


*Ref 2: ML-Assisted Offensive Security

<img width="628" height="403" alt="Screenshot 2026-01-08 180825" src="https://github.com/user-attachments/assets/59f17071-71d3-4ef1-a568-2fb838927c0c" />


Constructed an automated decision engine by integrating a Python machine learning pipeline with the Metasploit Framework to streamline exploit selection. By using Pandas for feature engineering and msfrpcd for orchestration, I transformed raw Nmap reconnaissance data into actionable intelligence through a high-reliability XGBoost predictive model. Along the way, you mastered critical troubleshooting skills, resolving RPC connection failures by aligning ports and protocols to successfully bridge the gap between data science and offensive security.




*Ref 3: ML-Assisted Offensive Security




<img width="347" height="372" alt="Screenshot 2026-01-08 182725" src="https://github.com/user-attachments/assets/334aa0da-39a3-49d6-a82e-896ad2a5ba1d" />


In this project, I engineered an automated cybersecurity orchestration pipeline that bridges a Python-driven machine learning workflow with the Metasploit Framework. By transforming raw network reconnaissance into prioritized, high-probability attack vectors, the system effectively accelerates the exploitation lifecycle through data-driven intelligence.



*Ref 5: ML-Assisted Offensive Security




<img width="346" height="277" alt="Screenshot 2026-01-08 182916" src="https://github.com/user-attachments/assets/5ee10f23-e3eb-45e1-b105-ab10e961cfa6" />



The output displayed in your final screenshots represents the Execution and Verification phase of the pipeline. At this stage, the "Brain" has moved past raw data processing and is providing a prioritized security posture of the target.


*Ref 6: ML-Assisted Offensive Security


<img width="355" height="446" alt="Pic attack" src="https://github.com/user-attachments/assets/d83cdacf-82a7-4468-a1ac-0294a5749c10" />



Executing a post-script scan demonstrates a high level of Operational Maturity. It proves that as an engineer, you do not rely solely on automation; you use industry-standard tools to verify that the automated system's "vision" aligns with the physical reality of the network.





