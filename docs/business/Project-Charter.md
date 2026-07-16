### Problem statement
The organization currently operates multiple independent systems that generate large volumes of structured and
semi-structured data. These systems include customer onboarding, account management, payment processing,CRM
and regulatory reporting. Data is fragmented across multiple platforms, making it difficult for business users
to access trusted, timely, and unified information. The organization requires a modern enterprise data platform
on AWS that consolidates enterprise data into a scalable, secure, and governed data lake.
The platform should also enable AI-powered capabilities such as natural language querying, intelligent data
discovery, automated pipeline troubleshooting, and enterprise knowledge retrieval through Agentic AI and
Retrieval-Augmented Generation (RAG).The solution must be cloud-native, secure, scalable, observable,
and cost-optimized while supporting future AI-driven use cases.

# Problem 1
Data exists in multiple silos (CRM,Core Banking,Loan System, Credit Card Platform,Fraud System). No single source of truth.
Also, the data is inconsistent spread across the systems.
# Problem 2
Business users depend heavily on Engineers for data analysis for query execution. Instead, they should have a way to analyze data themselves.
They want dashboards and natural-language access without relying on technical teams.
# Problem 3
If any ETL fails the job stays in failed state unless any engineer debugs and restarts.The business wants AI to assist with diagnosis and recommendations.

# Objective                     |	Success Metric
Centralize enterprise data      |	100% of identified source systems onboarded
Reduce ETL troubleshooting time |	70% reduction in time to resolution
Enable self-service analytics	|    Business users can answer common questions without SQL
Improve data quality            |   Automated validation rules applied to critical datasets
Introduce AI assistance	        |   AI agents assist with troubleshooting and knowledge retrieval
Reduce operational costs	    |   Optimized cloud usage and scalable architecture

### Version 1 : In Scope

# Processing
✅ Batch Processing (S3, AWS Glue, PySpark, Step Functions, Athena)
Note: Streaming (Kafka/Kinesis) will be added in Version 2.


# AWS Architecture
✅ Single AWS Region
Benefits:
Lower cost
Easier deployment
Simpler IAM
Easier Terraform
Good for learning
Note: Later evolve the architecture to Multi-Region Disaster Recovery.

# AI Scope
Enterprise Data Lake
Lakehouse
RAG
Agentic AI
Multi-Agent System
AI-powered ETL troubleshooting
Natural Language SQL
Enterprise Knowledge Assistant

# Cloud
AWS only.
    