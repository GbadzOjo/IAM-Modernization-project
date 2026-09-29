# IAM-Modernization-project
Designing, auditing, and securing an identity management framework for a growing tech company.
Part 1: Identity Inventory & Taxonomy
<img width="915" height="273" alt="Screenshot 2026-09-29 022748" src="https://github.com/user-attachments/assets/45261dc1-17bd-442f-8ad5-0e6fd507e3c1" />
Part 2: Designing a Least-Privilege Access Matrix (Authorization)
<img width="940" height="293" alt="Screenshot 2026-09-29 024318" src="https://github.com/user-attachments/assets/d8ac0009-9b0f-46f4-badd-60a4c8c45a15" />
Part 3: Incident Investigation & Audit Analysis (Accounting)
Answer the following forensic questions using the AAA framework principles:
1. Identification & Authentication: Did a human directly log in, or was a workload identity used? Which account/role was invoked? A workload identity with DevOps-Deployment-Role was used to access the resources
2. Authorization: Was the action permitted by default, or was there an explicit policy allowing it? The action was permitted by default
3. Accounting/Forensics: Based on the source IP and timestamp, what anomaly or red flag stands out that suggests a security incident? (Hint: Think about when developers usually deploy code and where traffic originates). Based on the access time, it suggests a possible insider threat or a DevOps engineer's compromised account.

   
Part 4: The Zero Trust Transition Strategy: Write a brief executive summary on why the Old network firewall cannot protect the cloud infrastructure.

The legacy Castle-and-Moat security model relied on a hard network perimeter—like our traditional firewall—to keep threats out while trusting everything inside. In cloud infrastructure, however, this physical perimeter no longer exists. Cloud assets, remote employees, and third-party SaaS integrations sit outside our traditional network boundary. Relying solely on network firewalls leaves critical visibility gaps and creates a single point of failure: once an attacker bypasses the perimeter (e.g., via stolen credentials or phishing), they gain unchecked lateral access to critical cloud data.
Shifting to Identity as the Perimeter establishes identity, context, and access controls as our primary security boundary. Instead of trusting devices based on their network location, every user, workload, and request is continuously authenticated, authorized, and evaluated using strong Identity and Access Management (IAM), Multi-Factor Authentication (MFA), and Least Privilege policies. This eliminates implicit trust, neutralizes credential-based attacks, and ensures that even if a breach occurs, access is tightly restricted to specific resources, protecting our multi-cloud ecosystem from compromise.


Implementation of the Separation of duty design for the different Users

Two S3 buckets created for each of the user groups 
<img width="892" height="187" alt="Screenshot 2026-09-29 025354" src="https://github.com/user-attachments/assets/bff602d6-c664-42b0-8cda-0c3fc365e9cc" />

Two different policies were created in the IAM policy console for the two different user groups, ensuring separation of duties
<img width="1439" height="128" alt="Screenshot 2026-09-29 025552" src="https://github.com/user-attachments/assets/0ba08e28-ece6-425d-9974-0349a14548e2" />
Performed tests to confirm that users cannot access the S3 bucket of the other team and vice versa
User Bob in the DB team is unable to access the S3 bucket of the Dev Team
<img width="1909" height="876" alt="Screenshot 2026-09-27 202404" src="https://github.com/user-attachments/assets/b8a6d0a5-ed67-4a60-babd-fc0d7a47aac0" />
User Sarah in the Dev team is unable to access the S3 bucket of the DB Team
<img width="1895" height="829" alt="Screenshot 2026-09-27 201956" src="https://github.com/user-attachments/assets/36928866-fccd-421f-823e-093a9fde58fb" />








