```mermaid
graph TD
    subgraph "Supply Chain Tiers (Data Sources)"
        T3[Tier 3: Raw Materials] -->|IoT/RFID Logs| T2[Tier 2: Components]
        T2 -->|Invoices/Shipments| T1[Tier 1: Assembly]
        T1 -->|Final Product Data| DC[Data Collection Layer]
    end

    subgraph "Core Intelligence Engine"
        DC --> DB[(Graph Database - Neo4j)]
        DB --> AI{AI Fraud Engine}
        AI -->|Pattern Matching| AD[Anomaly Detection]
        AI -->|Provenance Check| BC[Blockchain Ledger]
    end

    subgraph "Output & Action"
        AD --> Alert[Risk Alert System]
        BC --> Cert[Digital Integrity Certificate]
        Alert --> Dash[Management Dashboard]
    end

    style AI fill:#f96,stroke:#333,stroke-width:2px
    style Alert fill:#ff9999,stroke:#333
