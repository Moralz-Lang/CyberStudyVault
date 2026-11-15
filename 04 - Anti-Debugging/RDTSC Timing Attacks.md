# RDTSC Timing Attacks

### 1. High-Precision Hardware Timing Checks
* When a malware sample is analyzed inside a debugger, its execution rate drops significantly due to human analysis latency, stepping through instructions, and debugger breakpoint handling.
* Malware uses the native assembly instruction **`RDTSC` (Read Time-Stamp Counter)** to detect this latency and identify the presence of an active debugger or automated sandbox analysis environment.

### 2. Delta Execution Analysis Implementation
* **Mechanism:** The malware executes an initial `RDTSC` call to record the CPU's current cycle count. It then runs a short block of code, followed immediately by a second `RDTSC` instruction to capture the updated cycle count.
* The program calculates the difference (delta) between the two timestamp values. If the calculated delta exceeds an expected runtime threshold, the malware assumes it is running inside an analysis environment and terminates or alters its execution flow to hide its malicious payload.

```assembly
; Visualizing RDTSC Timing Check Logic
rdtsc                   ; Query cycle counter (Populates EDX:EAX)
mov ecx, eax            ; Store low-order bits of initial timestamp
; --- Target Code Block Executed Here ---
rdtsc                   ; Query cycle counter again
sub eax, ecx            ; Calculate runtime cycle delta
cmp eax, 0xFFF          ; Compare against expected threshold
ja target_evasion_exit  ; Jump and exit if execution latency indicates an active debugger

#topic/anti-debugging #topic/malware #status/hardened