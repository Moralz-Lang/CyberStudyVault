# RTO vs RPO

### 1. Business Continuity Metrics
* **RTO (Recovery Time Objective):** The maximum acceptable duration of downtime before an application or business process must be successfully restored following a service disruption. This metric defines the organization's tolerance for time offline.
* **RPO (Recovery Point Objective):** The maximum acceptable age of data that can be lost following a service disruption. This metric defines data loss tolerance and dictates backup frequency requirements.

[ Normal Operations ] ──(Backups Run)──> [ Event Disruption ] ──(Downtime Window)──> [ Restored ]
│                                       │                                        │
└───────────── RPO Window ──────────────┴────────────── RTO Window ──────────────┘
(Acceptable Data Loss Age)                 (Acceptable Recovery Time)


### 2. Disaster Recovery Site Classifications
* **Hot Site:** A fully equipped disaster recovery facility with duplicate hardware, real-time data replication, and active network connections. Provides near-instantaneous failover capabilities but has the highest implementation and maintenance costs.
* **Warm Site:** A partially equipped recovery facility that has the necessary network infrastructure and core hardware components installed. It requires data restoration from backups and final software configuration before it can take over production traffic.
* **Cold Site:** A basic physical storage facility that provides power, cooling, and network connectivity, but contains no active computing hardware or server infrastructure. Activating the site requires procuring and shipping hardware, installing systems, and restoring data from backups, resulting in the longest recovery timelines.

#topic/grc #topic/business-continuity #status/hardened

