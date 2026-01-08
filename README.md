<img width="541" height="390" alt="IOE drawio" src="https://github.com/user-attachments/assets/86355cc4-4020-4765-99a7-74605fa95135" />
# Intelligent Offensive Engineering

## Objective

Developed an Intelligent Offensive Engineering framework designed to augment human penetration testers by providing a predictive "advisory" layer during engagements. Using Metasploitable 2 as a target environment, I engineered a Human-in-the-Loop (HITL) system that performs Machine Learning Inference on network reconnaissance data to prioritize attack surfaces. The system serves as a strategic assistant, utilizing a pre-trained model to recommend high-probability exploit paths with associated confidence scores. This framework maintains strict human oversight by requiring manual authorization for any offensive actions, which are then programmatically executed via the Metasploit RPC API, ensuring safe and controlled validation of vulnerabilities.

### Skills Learned


- Human-in-the-Loop (HITL) Orchestration: Designed an interactive system that pauses for human validation, ensuring that high-risk exploits are only executed after manual review of AI-generated confidence scores.
- Augmented Decision Making: Developed the ability to interpret Machine Learning Inference (success probabilities) to make data-driven tactical decisions during an engagement.
- Explainable AI (XAI) for Security: Gained experience in interpreting why a model predicts a high success rate (service version matches a known high-reliability exploit), which is critical for justifying actions to stakeholders.
- Probability-Based Triage: Mastered the use of ML to filter out "low-signal" vulnerabilities, focusing limited human attention on attack vectors with the highest statistical likelihood of success.
- Adversarial Inference Analysis: Mastered the ability to interpret model output scores to prioritize the most efficient attack paths within a legacy infrastructure.
- Strategic Feature Engineering: Learned to translate complex, text-based Nmap scan data into structured numerical inputs for a machine learning model to enable rapid assistant-led triage.
- Safe Adversarial Operations: Focused on "Informed Exploitation" to ensure system stability, using predictive scores to avoid "unstable" or "noisy" exploits in sensitive legacy environments.
- Contextual Awareness & Override: Developed the expertise to manually override AI recommendations based on environmental knowledge (knowing a specific service is mission-critical even if the AI suggests it is vulnerable).
- Evidence-Based Reporting: Learned to document the "Logic Path" taken by the AI/Human team, providing a clear audit trail of why specific actions were chosen for remediation and defense.
- Continuous Security Validation: Leveraged the assistant framework as a repeatable "stress test" for defensive controls, using AI to consistently find the most likely paths an attacker would take.
- Risk-Based Exploitation: Prioritized business continuity by selecting exploits based on their impact-to-stability ratio, a key skill for professional penetration testing and SOC engineering.

### Tools Used


- Kali Linux: The primary Debian-based operating system used for hosting the attack infrastructure and the Python orchestration environment.
- Metasploitable 2: A purposely vulnerable Linux virtual machine acting as the isolated target for validating the assistant's predictions.
- Metasploit Framework (MSF): The core exploitation engine used to deliver payloads and manage active sessions once a path is approved.
- Nmap (Network Mapper): The reconnaissance tool used to discover open ports and service versions, providing the raw data for the ML model.
- Metasploit RPC (msfrpcd): The service that allows the Python assistant to programmatically trigger exploits on the target after human authorization.
- Python 3: The primary language used to build the data pipeline, load the ML model, and manage the user interface.
- Scikit-Learn / XGBoost: The machine learning frameworks used to run the pre-trained predictive model that calculates exploit success probabilities.
- Joblib / Pickle: Libraries used for model serialization, allowing the script to "load" the pre-trained brain instantly into memory.
- Pandas & NumPy: Data manipulation libraries used for Feature Engineering—transforming Nmap text output into the numerical format required for inference.
- pymetasploit3: The bridge library used to interface the Python logic with the Metasploit RPC API.
- Custom CLI Decision Menu: A human-centric interface that displays the AI’s ranked recommendations and success scores, pausing for manual user input.
- TShark / Wireshark: Used to capture and examine network traffic to manually verify the "noise" and behavior of an approved exploit.
- Linux Log Analysis: Manual examination of target logs (/var/log/syslog) to provide the final "ground truth" on whether the assistant's prediction was correct.



## Steps


*Ref 1: Intelligent Offensive Engineering

<img width="541" height="390" alt="IOE drawio" src="https://github.com/user-attachments/assets/661a38a7-7351-4ddc-a8f6-9e4d06451c6e" />

