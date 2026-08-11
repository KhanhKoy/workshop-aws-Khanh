---
title: "Week 2 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---
### Week 2 Objectives:

* Complete the legal data processing pipeline and optimize the index building process.
* Learn about RDS PostgreSQL pgvector, Bedrock Titan Embedding, and write a project proposal.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                       | Start Date | Completion Date | Reference Material                                                                |
| --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | --------------------------------------------------------------------------------- |
| 2   | - Continue completing the legal data processing pipeline.<br />- Improve data reading using streaming/batching to reduce RAM usage.<br />- Optimize metadata and parquet content reading in small batches. | 29/06/2026 | 29/06/2026      |                                                                                   |
| 3   | - Optimize the index building process.<br />- Add a periodic commit mechanism to avoid memory overflow.<br />- Check and handle issues arising when building large datasets.                               | 30/06/2026 | 30/06/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 4   | - Complete chunking logic for legal text.<br />- Adjust chunk size, chunk overlap, and metadata.<br />- Complete EmbeddingService with a Vietnamese embedding model.                                       | 01/07/2026 | 01/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 5   | - Build an index building pipeline from document, chunk, embedding to vector store.<br />- Write script scripts/build_index.py to create vector index.<br />- Test run and verify index build results.     | 02/07/2026 | 02/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |
| 6   | - Learn about Amazon RDS PostgreSQL and the pgvector extension.<br />- Learn about Amazon Bedrock Titan Embedding.<br />- Write a proposal to present project ideas.<br />- Write Week 2 worklog.          | 03/07/2026 | 03/07/2026      | [https://cloudjourney.awsstudygroup.com/](https://cloudjourney.awsstudygroup.com/) |

### Week 2 Achievements:

* The index building pipeline was further completed with the capability to process data in batches.
* Improved memory control capabilities when processing large datasets.
* Completed proposal presenting the ideas and direction of the project.
* Grasped the role of RDS pgvector and Bedrock Titan Embedding in cloud architecture.
