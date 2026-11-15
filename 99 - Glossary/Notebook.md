# FILE: 99 - Glossary/Analyst Core Notebook.md

### 🧠 Critical Exam Prep Tips
* *Calling Conventions:* If the assembly showing `add esp, X` occurs immediately *after* an external function call, it is a `cdecl` environment (caller cleans stack). If the return statement inside a function is formatted as `ret X`, it is a `stdcall` convention (callee cleans stack).
* *GRC Framework Selection:* Use `ISO 27001` when asked to implement an overarching Information Security Management System (ISMS) framework. Select `COBIT` for IT Governance alignment, and `NIST SP 800-53` for technical security control implementation.
* *Disaster Recovery Tiers:* When evaluating low-cost recovery solutions that tolerate multi-day recovery timelines, choose a `Cold Site`. For immediate failover with low RTO/RPO requirements, select a `Hot Site`.

### 🕵️ Threat Hunting Scenarios
* *Hardware Breakpoint Monitoring:* Monitor for unauthorized or unexpected processes initiating `GetThreadContext` calls against active worker threads. This is a common indicator of malware trying to detect analyst hardware breakpoints.
* *Evasion & Packing Indicators:* Configure Endpoint Detection and Response (EDR) rules to flag processes that execute rapid bitwise `XOR` loops across consecutive memory sections followed immediately by a long `JMP` or `CALL` to a dynamically allocated memory region.
* *AitM Session Theft:* Hunt for anomalous login events where a single session cookie originates from multiple geographically disparate IP blocks within a short window, indicating potential session hijacking via an AitM proxy server.

### 💻 Live Python Coding Fixes
The raw handwritten notes contained explicit code logic bugs that required remediation during ingestion. The original and corrected implementations are documented below:

* **Scenario 1: System Inventory Counter Loop**
    * *Incorrect Logic:* The original code attempted to sum the values within an inventory dictionary by passing the global dictionary handle back into the tracking loop index, resulting in an unmappable hash type error.
    * *Corrected Implementation:*
        ```python
        def total_inventory(inventory_dict):
            total = 0
            for item in inventory_dict:
                total += inventory_dict[item] # Access values using the current loop key
            return total
        ```
* **Scenario 2: Low-Score Calibration Function**
    * *Incorrect Logic:* The original function attempted to assign a value directly within a conditional logic evaluation statement (`return record["score"] = 50`), leading to a syntax termination error.
    * *Corrected Implementation:*
        ```python
        def boost_low_scores(records_list):
            for record in records_list:
                if record["score"] < 50:
                    record["score"] = 50      # Correctly assign the minimum threshold value
            return records_list
        ```