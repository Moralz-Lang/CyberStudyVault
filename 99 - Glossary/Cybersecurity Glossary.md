# Cybersecurity Glossary

* **Leaf Function:** An optimized function that contains no calls to external subroutines, allowing the compiler to bypass standard stack frame generation.
* **Frame Pointer Omission (FPO):** A compiler optimization that frees the `EBP` register from serving as a fixed frame pointer, allowing it to be used as a general-purpose register while local variables are tracked via `ESP`.
* **Stack Canary / Cookie:** A randomized security value placed on the stack during the function prologue to detect buffer overflows and prevent return address hijacking.
* **Unpacker Stub:** The un-obfuscated initialization code embedded within a packed executable that handles payload decryption and transfers execution to the Original Entry Point (OEP).
* **Original Entry Point (OEP):** The original entry point of a packed executable where code execution begins after the unpacker stub decompresses or decrypts the main payload.
* **Reverse Proxy Phishing:** An attack vector where a malicious proxy server is positioned between a victim and a legitimate service to capture credentials and session cookies in real time, bypassing standard MFA.
* **Tokenization:** A data protection method where sensitive data elements are replaced with non-sensitive placeholders (tokens) to clear plain text data from processing environments.
* **Recovery Time Objective (RTO):** The maximum acceptable duration of system downtime before a service or business process must be restored after a disruption.
* **Recovery Point Objective (RPO):** The maximum acceptable age of data that can be lost following an outage, defining required backup frequencies.
* **Data Minimization:** A privacy principle requiring organizations to limit data collection to the absolute minimum necessary to fulfill a specific business objective.

#topic/glossary #status/hardened