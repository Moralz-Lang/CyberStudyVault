# FILE: 99 - Glossary/Master Flashcards.md

1. Q: What optimization is automatically applied to a Leaf Function if variables fit in registers?
   A: The compiler skips creating a standard stack frame, bypassing the standard prologue and epilogue sequences.
2. Q: How are local variables accessed when Frame Pointer Omission (FPO) is active?
   A: They are referenced via static mathematical offsets calculated directly from the Stack Pointer register (`ESP`).
3. Q: What is the argument loading order for the first four parameters in an x64 Fastcall environment?
   A: 1st -> RCX; 2nd -> RDX; 3rd -> R8; 4th -> R9.
4. Q: Which assembly instruction allows manual user-mode parsing of the PEB base address on x86 platforms?
   A: `mov eax, fs:[0x30]`.
5. Q: Where is the `BeingDebugged` flag byte located inside the Windows Process Environment Block?
   A: At the `PEB + 0x02` memory offset address.
6. Q: What phase of a packed executable lifecycle handles payload decompression and transfers execution to the OEP?
   A: The Unpacker Stub.
7. Q: How does malware use the `RDTSC` instruction to detect an active debugger or sandboxed analysis environment?
   A: It measures execution cycle counts before and after a block of code; an abnormally high delta indicates debugger stepping or latency.
8. Q: Which Win32 API function allows a process to inspect CPU debug registers `DR0` through `DR7` for hardware breakpoints?
   A: `GetThreadContext`.
9. Q: Why are AitM reverse proxy phishing attacks able to bypass standard Multi-Factor Authentication (MFA) mechanisms?
   A: The proxy relays traffic in real time, allowing the user to complete the valid MFA challenge before capturing the finalized session cookies.
10. Q: What is the primary operational advantage of Tokenization over standard data encryption for financial transactions?
    A: It replaces sensitive data with non-sensitive placeholders, removing plain text cardholder data from processing systems and reducing PCI DSS compliance scope.