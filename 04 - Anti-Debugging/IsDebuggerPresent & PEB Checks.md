
### 1. Automated OS API Instrumentation
* **IsDebuggerPresent():** A standard Win32 API that queries the environment to check for an active debugger. Internally, this function reads the calling process's user-mode `Process Environment Block (PEB)` and extracts the value of the `BeingDebugged` flag byte.
* **CheckRemoteDebuggerPresent():** A separate kernel-level API query used to check if the target process is being monitored by an external user-mode debugger or kernel debugging instance.

### 2. Manual User-Mode PEB Structural Parsing
* To bypass security tools that monitor high-level API calls, malware can manually parse the `PEB` structure via the thread's segment registers to extract debugging status flags.
* **Target Verification Address Points:**
    * `FS:[0x30]` $\rightarrow$ Maps directly to the process's base `PEB` address location on 32-bit (`x86`) systems.
    * `PEB + 0x02` $\rightarrow$ Points to the `BeingDebugged` flag tracking byte. If this byte is non-zero, an active user-mode debugging instance is attached.
    * `PEB + 0x68` $\rightarrow$ Points to the 32-bit `NtGlobalFlag` registration mask. When a process is started by a debugger, this mask is populated with specific system flags, such as `FLG_HEAP_ENABLE_TAIL_CHECK` (0x10), `FLG_HEAP_ENABLE_FREE_CHECK` (0x20), and `FLG_HEAP_VALIDATE_PARAMETERS` (0x40).

#topic/anti-debugging #topic/malware #status/hardened