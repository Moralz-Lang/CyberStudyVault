
### 1. Critical Forensic Artifact Tracking
* **Shellbags Analysis Architecture:** Windows registry keys known as Shellbags track a user's folder exploration history, directory views, and file access patterns. This data resides within the user's `NTUSER.DAT` registry hive: `HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Bags`. Analysts extract this data during investigations to confirm user access to specific sensitive file directories and identify any manual cleanup or file deletion attempts.
* **Amcache Processing Engine:** Tracks application execution history and records execution timestamps, installation paths, and SHA-1 file hashes for run binaries. This forensic data is used to identify unauthorized or malicious executables that have run on an endpoint.
* **Shimcache Tracking (AppCompatCache):** A Windows kernel component used to track application compatibility parameters. It records snapshots of executed binaries, file modification dates, paths, and process execution flags, providing analysts with a chronological timeline of program execution on the system.

### 2. Active Networking Endpoint Analysis Commands
* Analysts use command-line tools to audit network connections, view active routing tables, and identify unauthorized communication channels on compromised endpoints.

```bash
# Windows Endpoint Connection Analysis Commands
netstat -o  # Displays active TCP/UDP connections along with their owning Process ID (PID)
netstat -nr # Prints the active IP routing table details
netstat -e  # Displays interface statistics (bytes sent/received, packet errors)

3. Log Source Identification & Infrastructure Mapping
Log Ingestion Surfaces: To identify and track adversary behavior, SOC analysts must maintain continuous visibility across key log sources:

OS Event Logs: Monitor endpoint account creation, process spawning, and privilege escalation events.

Firewall & WAF Logs: Track external connection attempts, blocked web attacks, and network mapping traffic.

Proxy Server Logs: Analyze outbound HTTP/HTTPS requests to identify command-and-control (C2) communications and unauthorized data egress channels.

Attack Modeling Frameworks: Security teams align detection rules and response workflows with industry attack frameworks like the Diamond Model of Intrusion Analysis and the Lockheed Martin Cyber Kill Chain to track and categorize adversary behavior.

#topic/soc #topic/forensics #status/hardened