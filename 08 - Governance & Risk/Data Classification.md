# Data Classification

### 1. Data Processing States
* **Data at Rest:** Data stored persistently on physical media (such as hard drives, SSDs, storage arrays, or backup tapes). Protected using full-disk encryption or file-level encryption.
* **Data in Transit:** Data moving across a network connection (such as traversing public internet channels or internal network zones). Protected using secure transport protocols like TLS or IPSec VPN tunnels.
* **Data in Use:** Data actively loaded into processor registers or system memory (RAM) while being processed by an application.

### 2. Information Sensitivity Classifications
* **Public:** Non-sensitive information that poses no operational or financial risk to the organization if disclosed to the public.
* **Internal:** Proprietary information intended for internal use only; disclosure may cause localized operational disruption or minor financial impact.
* **Confidential:** Sensitive corporate or customer information; unauthorized disclosure can lead to severe operational damage, financial losses, or regulatory penalties.
* **Top Secret:** Highly critical strategic or operational assets; compromise or unauthorized disclosure can cause catastrophic damage to the organization or national security infrastructure.

### 3. Data Protection and De-Identification Controls
* **Masking / Redaction:** The process of obscuring specific portions of a sensitive data field (e.g., masking a credit card number to show only the final 4 digits) to restrict visibility.
* **Tokenization:** A data protection method where a sensitive data element is removed from a database and replaced with a non-sensitive placeholder value called a **token**. This technique is widely used in the financial services and payment card industries to clear plain text cardholder data from processing environments, significantly reducing compliance scope under standards like PCI DSS.

#topic/grc #topic/data-protection #status/hardened