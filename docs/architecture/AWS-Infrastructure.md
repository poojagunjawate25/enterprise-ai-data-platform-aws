## Business Requrements:
- Centralize enterprise data.
- Build a scalable Data Lake.
- Process batch data daily.
- Enable SQL analytics.
- Add AI capabilities.
- Minimize operational overhead.
- Keep costs under control.

##  Layer        |         Responsibility
 Consumers      | Users and applications        
 API & Access   | Secure access to the platform 
 AI Services    | RAG and Agentic AI            
 Analytics      | SQL querying and reporting    
 Processing     | ETL and orchestration         
 Data Lake      | Enterprise storage            
 Source Systems | Banking applications          


## Capability     | AWS Service             | Why?                                                     
 Storage        | Amazon S3               | Durable, scalable, cost-effective object storage          
 Metadata       | AWS Glue Data Catalog   | Central metadata repository                               
 Processing     | AWS Glue Jobs (PySpark) | Serverless ETL aligned with batch-first approach      
 Workflow       | AWS Step Functions      | Native orchestration with low operational overhead        
 Analytics      | Amazon Athena           | Serverless SQL over S3/Iceberg                            
 API            | Amazon API Gateway      | Secure entry point for applications                       
 Compute        | Amazon ECS Fargate      | Runs our FastAPI and AI services without managing servers 
 AI             | Amazon Bedrock          | Enterprise-ready access to foundation models              
 Secrets        | AWS Secrets Manager     | Secure storage for credentials and API keys               
 Monitoring     | Amazon CloudWatch       | Logs, metrics, alarms, dashboards                         
 Security       | IAM + KMS               | Identity, access control, and encryption                  
 Infrastructure | Terraform               | Reproducible Infrastructure as Code                       
----------------------------------------------------------------------------------------------------

                                   ┌──────────────────────────────────────────────────────────────┐
                                   │                      Enterprise Users                        │
                                   │--------------------------------------------------------------│
                                   │ • Business Analysts  • Data Engineers  • Data Scientists     │
                                   │ • Compliance Team    • Operations Team • AI Consumers        │
                                   └───────────────────────────────┬──────────────────────────────┘
                                                                   │
                                                            HTTPS / REST
                                                                   │
                                 ┌─────────────────────────────────▼─────────────────────────────────┐
                                 │                    Amazon API Gateway                             │
                                 └─────────────────────────────────┬─────────────────────────────────┘
                                                                   │
                                 ┌─────────────────────────────────▼─────────────────────────────────┐
                                 │                 FastAPI Application (ECS Fargate)                │
                                 │-------------------------------------------------------------------│
                                 │ Authentication │ REST APIs │ AI APIs │ Health APIs               │
                                 └───────────────┬───────────────┬─────────────────┬────────────────┘
                                                 │               │                 │
                                                 │               │                 │
                                    ┌────────────────────▼───────┐  ┌────▼────────────────┐
                                    │    AI Agent Service        │  │   RAG Service       │
                                    └──────────────┬─────────────┘  └──────────┬──────────┘
                                                   │                           │
                                                   └──────────────┬────────────┘
                                                                  │
                                                         Amazon Bedrock
                                                                  │
                                              ┌───────────────────▼───────────────────┐
                                              │        Vector Knowledge Base          │
                                              │             (OpenSearch)
                                              └───────────────────┬───────────────────┘
                                                                  │
                                                         Amazon Athena
                                                                  │
                                                      AWS Glue Data Catalog
                                                                  │
                                                AWS Glue ETL Jobs (PySpark)
                                                                  │
                                                      AWS Step Functions
                                                                  │
      ┌───────────────────────────────────────────────────────────▼────────────────────────────────────────────────────────┐
      │                                      Amazon S3 Enterprise Data Lake                                                │
      │---------------------------------------------------------------------------------------------------------------     │
      │ Landing Zone │ Raw Zone │ Processed Zone │ Curated Zone (Apache Iceberg) │ AI Knowledge │ Archive Zone             │
      └───────────────────────────────────────────────────────────┬────────────────────────────────────────────────────────┘
                                                                  │
         ┌────────────────────────────────────────────────────────┼─────────────────────────────────────────────┐
         │                                                        │                                             │
         ───────▼────────┐   ┌──────────────┐   ┌───────────────┐   ┌────▼──────────┐   ┌──────────────┐   ┌──────────────────┐
         Core Banking    │   │ Loan System  │   │ Credit Cards  │   │ CRM System    │   │ Fraud System │   │ External APIs    │
         ────────────────┘   └──────────────┘   └───────────────┘   └───────────────┘   └──────────────┘   └──────────────────┘


=============================================================================================================
Platform Services (Cross-cutting)
=============================================================================================================

Terraform                → Infrastructure as Code
GitHub Actions           → CI/CD Pipeline
CloudWatch               → Monitoring, Logs & Alerts
IAM                      → Identity & Access Management
AWS KMS                  → Encryption Keys
Secrets Manager          → Secrets & API Keys
Amazon SNS               → Notifications
AWS Backup               → Backup & Recovery