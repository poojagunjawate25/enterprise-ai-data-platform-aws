## Decision:
All source data shall first land in Amazon S3 before any processing. Here S3 becomes immutable landing zone.
Source → S3 → Processing

## Reason:
- Original raw data will be preserved.
- Reprocessing is possible.
- Supports schema evolution.
- Decouple ingestion and processing.

## Alternatives:
Direct Glue processing.
Source → Glue → S3

### AWS High-Level Architecture – Interview Talking Points

## 1. Why S3?

- Acts as the enterprise data lake.
- Stores raw data before any processing.
- Highly durable (11 9's durability).
- Supports lifecycle management and encryption.
- Decouples storage from compute.

## 2. Why AWS Glue?

- Serverless ETL service.
- Native PySpark support.
- Integrates with Glue Data Catalog.
- Suitable for batch processing in Version 1.

## 3. Why Step Functions instead of Airflow?

- Fully managed.
- Tight AWS integration.
- Minimal operational overhead.
- Visual workflow execution.
- Easier for a first production implementation.

## 4. Why Athena?

- Serverless SQL engine.
- Queries data directly in S3.
- No infrastructure management.
- Good fit for ad hoc analytics.

## 5. Why ECS Fargate?

- Runs our FastAPI and AI services.
- No EC2 management.
- Easy scaling.
- Suitable for long-running APIs.


## 6. Why Amazon Bedrock?

- Enterprise-ready managed LLM access.
- Supports multiple foundation models.
- No model hosting required.
- Easier governance compared to self-hosting.


## 7. Why Single Region? (Version 1)

- Lower cost.
- Simpler operations.
- Faster implementation.
- Architecture remains extensible for multi-region.


## 8. Why Batch First? (Version 1)

- Most enterprise banking reporting is batch-oriented.
- Simpler architecture.
- Lower operational complexity.
- Streaming can be introduced without redesigning the platform.