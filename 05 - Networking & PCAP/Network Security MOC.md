
### 1. Passive/Active Infrastructure Reconnaissance
* **Reverse Query Lookup Engine:** The command syntax `dig -x <IP_ADDRESS>` is used to initiate a reverse DNS query to discover the domain mapping for a target infrastructure asset.
* **System Lookup Tool:** `nslookup` is used to run forward domain name queries and reverse IP address infrastructure lookups.
* **Zone Transfer Exploitation:** Adversaries use zone transfer queries to enumerate internal hostnames, subdomains, and network topology mapping from misconfigured nameservers.

```bash
# Zone Transfer Enumeration Syntax
host -t axfr domain.name dns-server
dig axfr @dns-server domain.name

### 2. Advanced Active Subdomain Mapping Architecture
The AMASS Mapping Platform: Used for automated open-source passive reconnaissance, subdomain identification, and brute-force routing mapping. It includes an internal database module (AMASSDB) to store API keys and manage historical infrastructure scans.

Bash
# Automated Subdomain Discovery Syntax
amass enum -passive -o wasporg.rec
amass enum -active -o wasp.org.rec
DNS Dumpster: A web-based passive reconnaissance platform used to discover MX mail exchange settings, domain subdomains, and host infrastructure records.

Censys Engine Automation: Performs passive scanning and automated queries across public networks to identify exposed database interfaces, exposed services, and open ports.

### 3. Active Packet Captures & Protocol Evaluation (PCAP)
The tcpdump Engine: Command-line packet capture engine used to sniff network traffic and capture raw data frames.

Wireshark Optimization Filters: Used to parse captured network packets. Effective analysis requires configuring precise capture and display filters, tracking network packet timestamps, and splitting HTTP requests, URI objects, and responses into distinct analysis streams.

### 4. Adversary-in-the-Middle (AitM) Reverse Proxy Phishing
Mechanism: Reverse proxy phishing setups position an attacker-controlled proxy server directly between the victim and the legitimate authentication server. The proxy handles and relays network requests in real time, capturing entered user credentials and active session tokens.

MFA/2FA Circumvention Vector: Standard multi-factor authentication systems (such as SMS codes, TOTP app tokens, or push notifications) validate a user's identity at the moment of login. Because the reverse proxy handles the live session traffic, the victim completes the valid MFA challenge directly through the proxy interface. The attacker intercepts the finalized session cookie from the response traffic, allowing them to impersonate the authenticated user and bypass MFA protections.

[ Victim Browser ] <=======> [ Reverse Proxy Server ] <=======> [ Legitimate Auth Provider ]
                                  (Interceptors)
                             * Captures Plain Text Credentials
                             * Steals Finalized Session Cookies
Defensive Mitigation & Remediation:

FIDO2 / WebAuthn Implementation: Deploy phishing-resistant authentication mechanisms. Hardware keys bound to specific domain names prevent browsers from submitting authentication credentials to a proxied or lookalike URL.

Conditional Access Policies: Configure network rules to restrict session generation based on explicit device compliance parameters, trusted corporate IP ranges, or behavioral anomaly indicators.

#topic/networking #topic/recon #status/hardened