# Master Study Path
This path maps out the mandatory prerequisite sequencing needed to review and process the technical elements of this vault.

[Low-Level Fundamentals] ──> [Assembly Logic] ──> [Evasion Mechanics] ──> [Defensive Monitoring]
│                          │                     │                       │
Memory Layout              Bitwise/Shifts         Packers/PEB             SOC/GRC Alignment

### Phase 1: Foundations of Execution Memory
* Review [[Process Memory Layout]] to understand stack configurations, argument passing, and stack frame optimization.
* Analyze [[TIB FS_GS Registers]] to identify user-mode environment tracking structures.

### Phase 2: Assembly Subroutines & Bitwise Processing
* Analyze the logical structures inside [[String Obfuscation]] to master register-clearing hacks and bitwise operations (`AND`, `OR`, `XOR`, `NOT`).
* Incorporate condition checking structures, logic shifting (`SHL`, `SHR`, `SAL`, `SAR`), and rotation mechanics.

### Phase 3: Defensive Evasion & Malware Reversing
* Study the lifecycle inside [[Packing & Unpacking]] to identify how unpacker stubs drop memory blocks into the execution stream.
* Deconstruct anti-analysis protections via [[IsDebuggerPresent & PEB Checks]], [[RDTSC Timing Attacks]], and [[Hardware Breakpoints Detection]].

### Phase 4: Threat Vector Ingestion & Governance Integration
* Implement live network sniffing tactics via [[Network Security MOC]] and database hunting loops using [[Database Recon and Exploitation]].
* Tie discovery parameters to active blue team environments via [[SOC & Incident Response MOC]] and governance controls within [[ISO NIST COBIT]].

