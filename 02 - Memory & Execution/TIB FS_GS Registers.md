
# FILE: 02 - Memory & Execution/TIB FS_GS Registers.md


# TIB FS_GS Registers

### 1. User-Mode Structure Thread Targeting
* In 32-bit Windows operating systems (`x86`), the specific hardware segment register `FS` is designated by the kernel to point directly to the base address of the **Thread Information Block (TIB)**.
* Malware developers and reverse engineers read this structure directly to bypass high-level Win32 monitoring APIs entirely, allowing them to locate essential operating system parameters without triggering API monitoring hooks.

### 2. Manual Process Environment Block (PEB) Pointer Extraction
* **The FS Base Pointer Offset:** The specific memory address pointer located at `FS:[0x30]` maps directly to the user-mode base address of the **Process Environment Block (PEB)**.
* **Parsing Target Offsets:**
    * `PEB + 0x02` $\rightarrow$ Points directly to the `BeingDebugged` flag tracking byte.
    * `PEB + 0x68` $\rightarrow$ Points directly to the 32-bit `NtGlobalFlag` registration mask.

```assembly
; Manual Assembly PEB Extraction Sequence
mov eax, fs:[0x30]      ; Extract the base address of the PEB structure
movzx ebx, byte ptr [eax + 2] ; Read the precise byte value of the BeingDebugged flag

#topic/low-level #topic/windows-internals #status/hardened

