## Scope (Product)

          Enterprise AI Data Platform (Our System)         
                            |                              
  Ingestion  | Processing | Lakehouse | AI | Monitoring 




## HLD

                         +----------------------+
                         |   Business Analysts  |
                         +----------+-----------+
                                    |
                         +----------v-----------+
                         |    AI Assistant      |
                         +----------+-----------+
   input sources                            |                                    consumers
+----------------+        +---------v------------------------------+        +----------------+
| Core Banking   |------->|                in-scope                        |<-------| Data Engineers |
+----------------+        |  Enterprise AI Data Platform           |        +----------------+
+----------------+------->|                                        |<-------+----------------+
| Loan System    |        | - Data Ingestion                       |        | Data Scientists |
+----------------+        | - Data Lake                            |        +----------------+
+----------------+------->| - Lakehouse                            |<-------+----------------+
| CRM            |        | - Analytics                            |        | Compliance Team |
+----------------+        | - AI Services                          |        +----------------+
+----------------+------->|                                        |<-------+----------------+
| Fraud System   |        +----------------------------------------+        | Operations Team |



# System Context Diagram

## Purpose
Describe the scope of the Enterprise AI Data Platform and its interactions with external users and systems.

## External Systems
- Core Banking
- Loan Management
- CRM
- Fraud Detection
- External APIs

## Internal Users
- Data Engineers
- Business Analysts
- Data Scientists
- Compliance Team
- Operations Team

## System Boundary
The Enterprise AI Data Platform is responsible for data ingestion, storage, processing, analytics, AI capabilities, and monitoring. Source systems and end users remain outside the system boundary.


# ADR-002: Define System Boundary

## Status
Accepted

## Decision
The Enterprise AI Data Platform will be treated as an independent platform that consumes data from enterprise systems but does not directly update operational applications.

## Rationale
- Loose coupling
- Better scalability
- Improved security
- Clear ownership boundaries
- Easier onboarding of new source systems

## Consequences
- Data latency is acceptable because Version 1 is batch-based.
- Future streaming integration can be added without redesigning the platform.               